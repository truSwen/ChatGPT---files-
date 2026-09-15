# Runbook — belső szállítás

> **CASE és Beni használja, ügyfél nem látja.** Ez a fájl mondja meg, hogy a
> `memory/07`-ben árazott két tételt **pontosan hogyan szállítjuk le**, milyen bizonyítékkal,
> és mi az, amit nem szabad rövidre zárni.
>
> Alapelv, ami az egészet vezeti: **minden lépés végén van egy futtatható vagy megnézhető
> bizonyíték.** Ha egy lépésnek nincs bizonyítéka, az a lépés nincs kész, csak elvégezve.
> Ez ugyanaz a szabály, ami a `#123`/`#126` hibanapló-bejegyzésekből jött.

---

## 0. Az eszközök, amikkel dolgozunk

| Eszköz | Mire |
|---|---|
| `node scripts/weboldal-audit.mjs URL` | A `10.1`–`10.8` és `5b.1`–`5b.4` kapuk gépi mérése. `--json` kapcsolóval gépi kimenet |
| `node scripts/weboldal-audit.mjs URL --oldalak /szolgaltatasok,/rolam` | Aloldalak bevonása a szövegmérésbe |
| `docs/geo-meresi-protokoll.md` | A kézi prompt-mérés menete és a napló-tábla formája |
| `memory/rules-geo.md` | A doktrína. Amit nem szabad eladni, és miért |
| `data/entitas-tribloc.json` + `scripts/gen-schema.mjs` | A saját entitás-schemánk mintája. **Ügyfélnél ugyanez a szerkezet**, más adatokkal |
| `?md` query paraméter | Framer-oldalnál a legolcsóbb mérőeszköz: valódi Markdownt ad vissza. Ellenőrzésre ezt használd, ne a nyers HTML-t parse-old |

⚠️ **A `weboldal-audit.mjs` CSAK OLVAS.** GET kéréseket küld, űrlapot nem küld be, semmit nem
módosít. Versenytárson is futtatható, ez nem szürke zóna.

---

## 1. GEO Alapozó Audit és Setup — a szállítás nyolc lépése

Átfutás: **2 hét.** A becsült saját ráfordítás 8–12 óra, ebből a kézi mérés 1,5 óra.

### 1.1 Kérdéskészlet-összeállítás (nap 1, ügyféllel, 20 perc)

Nyolc kérdés, négy típusból kettő-kettő: **ajánláskérés · összehasonlítás · ár · probléma.**
A probléma-típus a legerősebb, mert a valódi vevő ritkán szakmanevet ír be, azt írja be, ami
elromlott.

🔴 **A készlet ezután NEM VÁLTOZIK.** Ha új kérdés kell, az hozzájön `B1`, `B2` jelöléssel, a
régiek maradnak. Egy átírt kérdés elveszíti a historikus összevetést, és akkor a harmadik
hónapban nincs mit mutatni. (`rules-geo.md` §5)

**Bizonyíték:** a kérdéslista az ügyfél írásos jóváhagyásával, dátummal.

### 1.2 Alapmérés, kézzel (nap 1–2, 1,5 óra)

8 kérdés × 4 motor (ChatGPT, Gemini, Perplexity, Copilot) = 32 lekérdezés. Privát ablakban,
bejelentkezve, alapbeállításokkal. Kérdésenként és motoronként négy adat:
megjelent-e név szerint · idézték-e a domainjét · hányadik említés · ki jelent meg helyette
(top 3).

🔴 **Ez a nulladik nap, és a munka ELEJÉN adjuk oda az ügyfélnek**, nem a végén. Ez a
`marketing-hormozi-doktrina.md` „Elhihetőség" tagja: aki az alapmérést a végén mutatja meg,
arra a szót kell adni.

**Bizonyíték:** a kitöltött napló-tábla a `geo-meresi-protokoll.md` §3 formájában, dátummal.

### 1.3 Gépi alapmérés (nap 2, 15 perc)

```bash
node scripts/weboldal-audit.mjs https://AZUGYFELOLDALA.hu --json
```

Mentsd el a JSON-t. **Ez az „előtte" állapot**, és a záró mérésnél ehhez hasonlítunk.

**Bizonyíték:** a JSON kimenet, dátumozott fájlnévvel.

### 1.4 A JS-render vizsgálat (nap 2, 15 perc)

A `10.3` kapu gépileg jelzi, de a diagnózishoz kézzel is nézd meg:

```bash
curl -s https://AZUGYFELOLDALA.hu | grep -c 'ld+json'
```

Majd vedd a kezdőlap egy jellemző mondatát (a láthatóból), és keresd a nyers válaszban.
Ha nincs benne, a robot a kezdőlapból lényegében semmit nem lát.

🔴 **A leggyakoribb félrediagnózis:** a Google Rich Results tesztje **futtatja a
JavaScriptet**, tehát zöldet mutathat olyan schemára, amit a GPTBot soha nem lát.
**A nyers HTTP-válasz a mérvadó, nem a Google tesztelője.** Ez a saját oldalunkon is pont
így volt (`#156` mintája: következtetés mérés helyett).

**Bizonyíték:** a `curl` kimenet és a keresés eredménye, kimásolva.

### 1.5 Az entitás-réteg megépítése (nap 3–6)

Ez a legnagyobb hozamú tétel, és ez a legtöbb munka.

| Elem | Kapu | Mit ellenőrizz a végén |
|---|---|---|
| `Organization` / `LocalBusiness` / `ProfessionalService` JSON-LD | `10.1` | A blokk a **nyers** HTML-ben van, nem futásidőben injektálva |
| `sameAs` tömb a valódi külső profilokkal | `10.2` | Minden URL él, és tényleg az ügyfélé. Halott katalógus-link árt, nem használ |
| NAP-konzisztencia: azonos név, cím, telefon mindenhol | `10.2` háttere | Weboldal, Google Cégprofil, közösségi oldalak, katalógusok: **karakterre azonos** |
| Egyetlen, változatlan egymondatos leírás | `10.2` háttere | `CÉGNÉV – MIT CSINÁL, KINEK, HOL.` Ugyanaz a mondat mindenhol |

🔴 **Framer-alapú ügyfélnél számíts erre a csapdára:** a `setCustomCode` plugin API **csak a
saját snippetjét** tudja kezelni, a meglévő slot-tartalmat nem címezi meg. Ha ráírsz, két
entitás-blokk lesz az oldalon. A cserét a Framer felületén, a meglévő snippet szerkesztésével
kell elvégezni. A saját esetünk teljes leírása: `scripts/gen-schema.mjs` fejléc + Hibanapló `#142`.

**Bizonyíték:** `curl -s URL | grep -c 'sameAs'` és az audit `10.2` sora `PASS`.

### 1.6 Kinyerhetőség: kérdés-válasz szerkezet és jelölés (nap 6–9)

Két külön munka, és ebben a sorrendben:

1. **Tartalom** (`10.6`): a meglévő címsorokat kérdés alakúra írjuk, alattuk a válasz az első
   két-három mondatban. Egy bekezdés, egy állítás. Táblázat és lista, mert azok túlélik a
   darabolást.
2. **Jelölés**: `FAQPage` schema a kérdés-válasz blokkokra, **nyers HTML-ben**.

🔴 **A jelölés csak azt tartalmazhatja, ami az oldalon látszik is.** Rejtett kérdés-válasz
jelölés strukturáltadat-spam, és manuális intézkedést von maga után. Ugyanez az elv zárta ki
a saját `Review`/`AggregateRating` tervünket (`docs/bizonyitek-rendszer.md` K1).

**Bizonyíték:** az audit `10.6` sora `PASS`, és `curl -s URL | grep -c 'FAQPage'` legalább 1.

### 1.7 Crawler-hozzáférés (nap 9, 30 perc)

```bash
curl -s https://AZUGYFELOLDALA.hu/robots.txt
```

Az **idéző** botok (`OAI-SearchBot`, `ChatGPT-User`, `PerplexityBot`, `ClaudeBot`,
`Claude-SearchBot`) nem lehetnek `Disallow: /` alatt. A **tanító** botok (`GPTBot`, `CCBot`,
`Google-Extended`) tiltása **legitim üzleti döntés**, és az ügyfélé, nem a miénk.

⚠️ **Két hely van, nem egy.** A `robots.txt` mellett a tartalomszolgáltató hálózat (jellemzően
Cloudflare) bot-szabályai is blokkolhatnak. A `robots.txt` tiszta lehet úgy is, hogy a
kérés a CDN-en akad el. Ha az audit `PASS`-t ad, de a szerver-napló szerint egyik idéző bot
sem jár az oldalon, ott nézz szét.

**Bizonyíték:** az audit `10.4` sora `PASS`, plusz a bot-szabályok képernyőképe.

### 1.8 Záró mérés és átadás (nap 10–14)

```bash
node scripts/weboldal-audit.mjs https://AZUGYFELOLDALA.hu --json
```

Az „előtte" (1.3) és az „utána" JSON összevetése adja az átadó lapot. **A kézi prompt-mérést
itt NEM ismételjük meg**, mert két hét alatt a motorok nem indexelnek újra, és egy változatlan
eredmény hamis kudarcnak látszana. A prompt-mérés következő futása a retainer első hónapja.

**Az átadó lap tartalma:** a nulladik napi prompt-mérés · az „előtte" és „utána" kapu-tábla ·
mit javítottunk és miért · mi maradt szándékosan úgy, ahogy volt (például tiltott tanító bot) ·
mi a következő lépés, ha retainer nélkül folytatja.

---

## 2. GEO Monitorozás és Optimalizálás — a havi ciklus

Havi ráfordítás: **2,5–3 óra.** Fix nap a hónapban, hogy a mérés összehasonlítható legyen.

| # | Lépés | Idő | Bizonyíték |
|---|---|---|---|
| 1 | A **változatlan** 8 kérdés × 4 motor, privát ablakban | 1,5 ó | Kitöltött napló-sor, dátummal |
| 2 | `node scripts/weboldal-audit.mjs URL --json`, összevetés az előző hónappal | 15 p | A két JSON diffje |
| 3 | Crawler-napló: jártak-e idéző botok, mikor | 20 p | Szerver- vagy CDN-napló kivonat |
| 4 | Referral: `chatgpt.com`, `perplexity.ai`, `gemini.google.com` felől érkezett-e forgalom | 15 p | Webanalitika képernyőkép |
| 5 | Karbantartás: amit a mérés kihozott | 30–60 p | A módosítás visszamérve |
| 6 | **Egyoldalas jelentés** | 20 p | Maga a jelentés, e-mailben |

### 2.1 A jelentés szerkezete, kötötten

Egy oldal, ennél nem több. Négy blokk:

1. **A szám:** hány kérdés-motor párosban jelent meg a márka ebben a hónapban (például
   `3 / 32`), és mennyi volt előző hónapban.
2. **Mi változott:** konkrétan, melyik kérdésnél és melyik motorban.
3. **Mi nem változott, és miért nem baj:** a technikai javítások hetekben, a külső jelenlét
   hónapokban mérhető. Ha nulla a mozgás a második hónapban, azt ki kell mondani, nem
   elkenni.
4. **A következő lépés:** egy dolog, nem öt.

🔴 **A nulla eredményt is ki kell írni.** Egy hónap, amiben nem mozdult semmi, valós adat, és
az ügyfél ezért fizet. Aki minden hónapban „javulást" jelent, az három hónap múlva
hiteltelen, mert az ügyfél a saját forgalmán látja az igazat.

### 2.2 Ami a harmadik hónapban történik

Ez a döntési pont, és előre ki kell mondani az ügyfélnek. Három kimenet van:

| Ha a három hónap azt mutatja | Akkor |
|---|---|
| Elmozdult, a saját oldal munkája hatott | Folytatás, a hangsúly a kinyerhetőségre és a tartalomra |
| Nem mozdult, de a válaszok kizárólag katalógusokból és listacikkekből épülnek | A munka **kifelé** folytatódik (`10.8`), és ezt meg kell mondani. Nem a weboldalon van több teendő |
| Nem mozdult, és a klasszikus keresőben sincs jelenlét | 🔴 **Vissza a `5.x` SEO-higiéniához.** A GEO ráépülő réteg, alapok nélkül nincs mire épüljön |

---

## 3. Két dolog, amit soha ne csinálj ebben az üzletágban

**Ne ígérj megjelenést vagy helyezést.** Sem szóban, sem levélben, sem a hívás hevében. Ez
egyszerre szakmailag hamis (`rules-geo.md` §4) és fogyasztóvédelmi kockázat (`03-marketing.md`
copy-kockázat blokk).

**Ne építs linkhálózatot, és ne vegyél linket.** Sem az ügyfélnek, sem magunknak. Beni
döntése 2026-09-05-én teljes tiltás lett (`05-dontesnaplo.md`), és nem tárgyaljuk újra. A
kiérdemelt off-site jelenlét (`10.8`) az út: katalógus-regisztráció konzisztens `sameAs`-szal,
listacikkek, valódi szakmai jelenlét.

---

## 4. 🔴 A saját oldalunk, mielőtt bárkinek eladjuk

A `rules-weboldal-minoseg.md` §7 szabálya itt dupla súllyal él: **ha GEO-t árulunk, a
`tribloc.hu`-nak át kell mennie a saját `10.x` kapuinkon.** A 2026-09-04-i mérés szerint ma
nem megy át:

| Kapu | Állapot | Teendő |
|---|---|---|
| `10.2` `sameAs` | ✅ **megvan, élesben** (2026-09-05, 1 külső profil: a LinkedIn cégoldal) | – |
| `10.3` schema JS nélkül | 🟡 a főoldali JSON-LD látszik, de a `FAQPage` **csak a `/klimaszerelo`-n van, és futásidőben injektálódik** | `docs/handover_geo_schema_raw_html.md`. Framer-canvas munka, a canvas-zár feloldása után |
| `5b.1` `llms.txt` | 🔴 **HTML-bundle**, nem valódi `text/plain` fájl | Külön tétel |
| `2.1` webanalitika | ✅ Cloudflare Web Analytics, 2026-09-03 óta | – |

🟢 **És ami emiatt mégis versenyelőny:** a 2026-09-05-i mérés szerint **mindkét élő magyar
versenytárs bukja a `2.1`-et**, nincs webanalitikájuk, tehát AI-referral forgalmat nem tudnak
kimutatni a kliensnek. Nekünk van. Ez a különbség a havi jelentés 4. blokkjában érhető tetten,
és ez az, amiért a 60.000 Ft/hó nem üres.

**Sorrend, mielőtt az első fizetős GEO-ajánlat kimegy:** ~~`10.2`~~ ✅ → `5b.1` → `10.3`.
Az `5b.1` a Framer-csomag fizetési falán áll (`static/README.md`, döntés megvan), a `10.3`
canvas-munka.
