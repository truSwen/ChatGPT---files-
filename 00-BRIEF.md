# BRIEF — GEO mint önálló üzletág

**Készült:** 2026-09-05 · CASE (Mac), `nexus-core-geo` session · Beni döntése alapján
**Kanonikus ár és szállítási tartalom:** [`memory/07-ajanlat-arazas-garancia.md`](../../../memory/07-ajanlat-arazas-garancia.md)
„GEO: ÖNÁLLÓ ÜZLETÁG, KÜLÖN ÁRSOR" szakasz. **Ez a fájl nem duplikálja az árakat**, csak
hivatkozik rájuk, hogy ne sodródjanak el.
**Szakmai szabály:** [`memory/rules-geo.md`](../../../memory/rules-geo.md) ·
**Marketing-keret:** [`memory/marketing-hormozi-doktrina.md`](../../../memory/marketing-hormozi-doktrina.md)

---

## 0. A csomag négy fájlja, és hogy melyiket kinek add oda

| Fájl | Kinek | Mire |
|---|---|---|
| `00-BRIEF.md` (ez) | **belső** | A pozicionálás, a Value Equation, az ajánlat-stack, a tilalmak |
| [`runbook-ugyfel.md`](runbook-ugyfel.md) | **az ügyfélnek**, ajánlat mellé | Mit kap, mikor, és neki mi a dolga. Kifelé adható dokumentum |
| [`runbook-marketinges.md`](runbook-marketinges.md) | **aki a kampányt futtatja** | Naptár, ütemezés, a Social Motor mai korlátai, mérés, hiba-elhárítás |
| [`runbook-belso.md`](runbook-belso.md) | **CASE / Beni, szállításkor** | A 200e-es Setup és a 60e/hó lépésről lépésre, kapu-kódokkal és bizonyítékkal |
| [`kampany-2026-10.md`](kampany-2026-10.md) | **aki posztol** | 8 kész poszt-szöveg, 4 hét, heti 2. Kimásolható |

---

## 1. A pozicionálás egy mondatban

> **A GEO nem tanácsadás és nem szövegírás. Mérés, technikai javítás, majd újramérés.**

Ez a mondat három dolgot old meg egyszerre, és mindhárom kötött:

1. **Elhatárol a versenytárstól.** A piac egy része „AI-optimalizált szöveget" ad el mérés
   nélkül. Aki mér, az más kategória.
2. **Megfelel a pályázati keretnek.** A `09` szerint a tanácsadás nem támogatott
   tevékenység, a fejlesztés igen. A megnevezésünk ezért mindenhol **fejlesztés és mérés**.
3. **Igaz.** A `weboldal-audit.mjs` `10.x` kapui és a `geo-meresi-protokoll.md` kérdéskészlete
   nem marketing-fogalmak, hanem futtatható eszközök.

---

## 2. A Hormozi Value Equation (kötelező, doktrína §0)

| Tényező | Ahogy ez az üzletág kezeli | Hol jelenik meg |
|---|---|---|
| **Vágyott eredmény** | „Amikor a vevőd megkérdezi a ChatGPT-t a szakmádról a városodban, a te neved is ott van a válaszban." Konkrét jelenet, nem elvont láthatóság | Minden poszt horgában, az ügyfél-runbook 1. oldalán |
| **Elhihetőség** | Dátumozott alapmérés a munka **elején**, havi mért jelentés utána. Előtte-utána adat, nem ígéret. Plusz: a saját oldalunk ugyanazon a tíz kapun megy át | `runbook-belso.md` bizonyíték-oszlop, `kampany` P3 poszt |
| **Időigény** | Setup 2 hét. A havi mérés a **mi** időnk. Az ingyenes önteszt 30 perc | Cím, kártyaszöveg, P1 és P7 poszt |
| **Erőfeszítés** | Az ügyfélnek 1 hozzáférés-átadás és 1 jóváhagyás a dolga. Fejlesztőt nem kell keresnie | `runbook-ugyfel.md` §3, minden CTA |

🔴 **A doktrína megjegyzése, ami itt a legfontosabb:** a versenytársak csak a vágyott
eredményen dolgoznak. **Az időigény és az erőfeszítés kimondása ingyen van**, és egy elfoglalt
szakembernél ez a két legerősebb tag. Ezért van minden anyagon percszám.

---

## 3. Az ajánlat-stack (doktrína §1, value stack)

Az ügyfél felé **így bontjuk**, ebben a sorrendben. Nem óradíj, nem „SEO csomag":

| Elem | Mit ér önmagában | Miért van benne |
|---|---|---|
| Dátumozott alapmérés, 8 kérdés × 4 motor | Enélkül a végén semmi nem bizonyítható | Ez a „nulladik nap" |
| Nyers HTTP-nézet: mit lát a nem renderelő robot | A leggyakoribb néma hiba feltárása | `10.3` kapu |
| Statikus HTML fallback réteg | A tartalom géppel olvashatóvá válik | `10.3` kapu |
| Entitás-schema + `sameAs` | A sok említésből egy cég lesz | `10.1`, `10.2` – a legnagyobb hozam |
| Kérdés-válasz szerkezet + `FAQPage` | Passzus-szintű kinyerhetőség | `10.6` |
| Crawler-hozzáférés rendezése | Kizárt robotok visszaengedése | `10.4` |
| `llms.txt` | 30 perc, ártalmatlan | `5b.1` – **kiegészítő, nem a lényeg** |
| Havi mérés + egyoldalas jelentés | A bizonyíték, ami a döntést megalapozza | A retainer maga |

🔴 **Amit ki kell mondani az ajánlatban, mert a szűkítés növeli az elhihetőséget** (doktrína §1.4):
nem vállalunk garantált helyezést, nem cseréljük le a keresőoptimalizálást, és nem adjuk el az
`llms.txt`-t fő eszközként.

---

## 4. A három kar (doktrína §5)

Minden növekedési javaslatnak meg kell jelölnie, melyik kart húzza:

| Kar | Hogyan húzza ez az üzletág |
|---|---|
| **Több lead** | Az ingyenes önteszt (`../ai-lathatosagi-onteszt/`) új, alsó belépőt nyit olyanoknak, akiknek már van weboldala, tehát a teljes rendszerépítés nem érdekli őket. Ez a `weboldal-audit` `9.4` kapuja: „van-e alsó belépő-ajánlat minden ártudatossági szinten" |
| **Magasabb konverzió** | A dátumozott alapmérés a konkrét fájdalmat mutatja meg számmal, nem érzésre. Aki látja, hogy nulla motorban jelenik meg, az nem „gondolkodik rajta" |
| **Magasabb ár / gyakoriság** | A retainer visszatérő bevétel, és a meglévő TRIBLOC MAX ügyfélnek is eladható **külön** ársorként, mert nem része a csomagnak |

---

## 5. 🔴 Amit ez az üzletág SOHA nem állít

Ez a lista kötelező minden anyagra: poszt, ajánlat, hívás, weboldal.

| Tilos | Miért | Helyette |
|---|---|---|
| „Garantáljuk, hogy megjelensz a ChatGPT válaszában" | Nem determinisztikus. Ugyanaz, mint a garantált Google 1. hely. GVH-kockázat is | „Garantáljuk, hogy méréssel megmutatjuk, hol állsz, és mi változott" |
| „A SEO halott / már nem kell" | `rules-geo.md` §0: aki ezt mondja, félreérti vagy félrevezet. A motorok a klasszikus keresők találataiból dolgoznak | „A GEO ráépülő réteg. Ha a keresőben nem vagy ott, a modell be sem gyűjt" |
| „A magyar weboldalak X%-a láthatatlan" | **Nincs ilyen mérésünk.** Kitalált szám az első visszaellenőrzésnél elviszi az egészet | A saját, dátumozott mérésünk: az 5 megnevezett szolgáltatóból 1-nek nincs élő oldala (2026-09-05) |
| „A Tribloc rendszerei alapból GEO-optimalizáltak" | 🔴 **Ma nem igaz.** A saját oldalunk 2026-09-04-én bukta a `10.2`-t és a `10.3`-at, az `llms.txt`-nk pedig HTML-bundle (`5b.1` FAIL) | „Ugyanazt a tíz ellenőrzést futtatjuk magunkon is, és kiírjuk az eredményt" |
| Nevesített ügyfél-referencia | `09`: novemberig nincs nevesíthető ügyfél | Saját mért adat és élő demó |
| Ár, kosár, „megveheted" a pre-launch anyagokon | `09`: a webshop-üzemeltetés nevesítetten tiltott, és semmi nem mutathat működő cégre a kérelemig | „Előjegyzési ár · novemberi indulásra" |

---

## 6. 🟡 A TARS-vázlat átvizsgálása (2026-09-05, CASE)

Beni átadta a TARS által készített kampány-vázlatot ellenőrzésre. **A szerkezete jó és
megtartottuk** (4 hét, heti 2 poszt, fájdalom/működés/konverzió arány, felület-elosztás).
Hat tartalmi javítás kellett, mindegyik a fenti §5 tiltásaiba ütközött:

| # | A vázlatban | A gond | Amit helyette írtunk |
|---|---|---|---|
| J1 | „a ChatGPT vak a magyar weboldalak **70%-ára**" | 🔴 **Kitalált szám.** Nincs ilyen mérésünk, és forrás sincs hozzá | A saját, dátumozott piacmérésünk (P3 poszt) |
| J2 | „**A hagyományos SEO halott.** A GEO a jelen" | 🔴 Szemben áll a `rules-geo.md` §0-val: a GEO ráépülő réteg, nem utód | „A GEO nem a SEO helyett van, hanem rá" |
| J3 | „**Miért ne fizess SEO szakértőnek** 2026-ban?" | Ugyanaz a hiba, plusz egy egész szakma leszólása nem a mi hangunk | „Amit a SEO-szakértőd nem néz meg, és három perc alatt te is látod" |
| J4 | „A Tribloc rendszerei **alapból** GEO-ra optimalizált statikus HTML-t és LLMS.txt-t használnak" | 🔴 **Ma nem igaz** (l. §5). Egy visszaellenőrizhető valótlan állítás a legdrágább dolog egy GEO-kampányban | Az önbevallás: ugyanazt mérjük magunkon, és kiírjuk |
| J5 | „Az első hónap üzemeltetése a tesztelőknek **ingyenes**" | Nincs jóváhagyva a `07`-ben, és a `09` pre-launch keretében kereskedelmi elköteleződésnek látszik | 🔵 Kivéve. Ha Beni akarja, a `07`-be kell felvenni előbb |
| J6 | „ki a legjobb **[a te szakmád]** a városodban" | `CLAUDE.md` §5.2: szögletes zárójeles helykitöltő ügyfélszövegben | Nagybetűs szó, jelek nélkül: `SZAKMA`, `VÁROS` |

**Amit a vázlatból változtatás nélkül átvettünk:** a 4 hetes ív, a heti 2 poszt, a
fájdalom → működés → konverzió sorrend, a felület-elosztás logikája, és a TikTok
hook–test–CTA szerkezet.

---

## 7. Kapcsolódó anyagok

- **Ingyenes belépő:** [`../ai-lathatosagi-onteszt/`](../ai-lathatosagi-onteszt/)
- **Blogklaszter (3 cikk):** [`docs/handover_tartalom_2026-09.md`](../../../docs/handover_tartalom_2026-09.md) §2.1
- **Piacmérés:** [`docs/versenytars-geo-piac-2026-09-03.md`](../../../docs/versenytars-geo-piac-2026-09-03.md) §5
- **Mérési protokoll:** [`docs/geo-meresi-protokoll.md`](../../../docs/geo-meresi-protokoll.md)
- **Heti tartalom-ritmus:** [`memory/rutin-heti-tartalom.md`](../../../memory/rutin-heti-tartalom.md)
- **Social Motor architektúra:** [`docs/architektura-social-motor.md`](../../../docs/architektura-social-motor.md)
