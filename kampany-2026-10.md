# GEO kampány — 1 hónap, heti 2 poszt, kész szövegek

**Készült:** 2026-09-05 · CASE (Mac) · a TARS-vázlat szerkezetére, hat tartalmi javítással
(`00-BRIEF.md` §6)
**Futtatás:** [`runbook-marketinges.md`](runbook-marketinges.md) · **Formai szabályok:** ugyanott §4

---

## Hogyan használd ezt a fájlt

Minden poszt három blokkból áll:

- **`SZÖVEG`** – ezt másolod ki **változtatás nélkül**. Már át van engedve a copy-szabályokon.
- **`KÉP` / `FORGATÓKÖNYV`** – mi legyen mellette, videónál időzítéssel és képernyő-szöveggel.
- **`MIÉRT`** – melyik Value Equation-tényezőt húzza, és mi a CTA. Belső, nem megy ki.

🔴 **A `SZÖVEG` blokkokban nincs kitalált szám.** Minden állítás vagy saját, dátumozott
mérésből jön, vagy általánosan igaz szakmai tény. Ha át akarsz írni egy mondatot, előbb nézd
meg a `00-BRIEF.md` §5 tiltás-tábláját.

**Ahol nagybetűs szó áll** (`SZAKMA`, `VÁROS`), oda a saját szakmád és városod kerül, jelek és
zárójelek nélkül. A posztokban ezek szándékosan bent maradtak, mert a poszt maga arra kéri az
olvasót, hogy a sajátját írja be.

---

## 1. hét · kedd · P1 · Fájdalom · Facebook + Instagram

### SZÖVEG

```
Van egy teszt, ami három percig tart, és sokakat kellemetlenül szokott érinteni.

Nyisd meg a saját weboldalad, és másolj ki belőle egy mondatot. Ne a menüből,
hanem a bemutatkozó szövegből. Utána nyomd meg a Ctrl és az U billentyűt
(Macen a Cmd, az Option és az U-t). Megnyílik egy fül, tele kóddal. Nyomj
Ctrl+F-et, és keresd meg benne azt a mondatot.

Ha nincs benne, akkor a weboldalad tartalma a ChatGPT, a Gemini és a
Perplexity robotjai számára nem létezik. Nem azért, mert rossz az oldal.
Azért, mert ezek a robotok többnyire nem futtatnak JavaScriptet, a modern
oldalépítők viszont pont abból rajzolják ki a szöveget.

Ez ma az egyik leggyakoribb ok, amiért egy rendben lévő weboldal kimarad az
AI-keresők válaszaiból. És majdnem senki nem tud róla, mert a böngészőben
minden szépen látszik.

Összeraktunk egy tíz pontos öntesztet. Fél óra, böngésző kell hozzá, más
semmi, és nem kell hozzá fejlesztő. A második pont pontosan ez a teszt.

tribloc.hu
```

### KÉP

Két képernyőkép egymás mellett, felirat nélkül a képen (a szöveg viszi):
bal oldalon egy rendes weboldal a böngészőben, jobb oldalon ugyanaz forráskód-nézetben, a
keresőmezőben `0 találat`. Satoshi, akcent `#7E61B8` a keretben. **Stock fotó nincs.**

### MIÉRT

Value Equation: **időigény** (3 perc) és **erőfeszítés** (nem kell fejlesztő). A horog nem
ígéret, hanem egy elvégezhető cselekvés, ami magától fáj, ha elbukik.
CTA: az önteszt. Pillér: fájdalom.

---

## 1. hét · csütörtök · P2 · Működés · TikTok / Reels

### FORGATÓKÖNYV

Formátum 1080 × 1920. 🔴 **Jobbról 140 px, alulról 350 px levágva**, oda semmi fontos nem
kerülhet. Teljes hossz: 32–38 másodperc. Képernyőfelvétel, Beni hangja rá.

| Idő | Kép | Képernyőn megjelenő szöveg |
|---|---|---|
| 0:00–0:03 | Beni arca, közeli. Egy mondat, vágás nélkül | `Megmutatom, mit lát a ChatGPT` |
| 0:03–0:08 | Vágás egy weboldalra a böngészőben, normál nézet | `Ezt látod te` |
| 0:08–0:16 | `Ctrl+U`, megnyílik a forráskód. Görgetés | `Ezt látja a robot` |
| 0:16–0:26 | `Ctrl+F`, a főcím beírása, `0 találat` villan | `0 találat` |
| 0:26–0:32 | Vissza Benire | `10 pontos önteszt · linkelve` |

**Szöveg alámondásra (ezt olvasd fel):**

```
Ez itt egy teljesen rendben lévő weboldal. Így látod te a böngészőben.

Most megnyomom a Ctrl és az U billentyűt. Ez a forráskód, és nagyjából ezt
látja az a robot, amelyik a ChatGPT-nek gyűjt.

Rákeresek a főcímre, ami az előbb ott volt a képernyőn. Nulla találat.
Tehát a robot számára ez az oldal gyakorlatilag üres.

Ez nem ritka hiba, hanem a modern oldalépítők alapértelmezése. És addig nem
derül ki, amíg valaki meg nem nézi. A linken van egy tíz pontos önteszt,
harminc perc, fejlesztő nélkül.
```

### CAPTION

```
Három perc, és kiderül, hogy a weboldalad látszik-e egyáltalán a ChatGPT,
a Gemini és a Perplexity robotjai számára. Az önteszt a linken.
#weboldal #vallalkozas #chatgpt #kisvallalkozas
```

### MIÉRT

Value Equation: **elhihetőség** (nem állítás, hanem megmutatás) és **erőfeszítés**.
Ez a legerősebb formátum a kampányban, mert a bizonyíték maga a képernyő.
Pillér: működés. CTA: profil-link.

---

## 2. hét · kedd · P3 · Fájdalom · LinkedIn

### SZÖVEG

```
Szeptember 3-án megkérdeztük a ChatGPT-t, hogy kik foglalkoznak
Magyarországon azzal, hogy egy cég megjelenjen a válaszaiban.

Öt magyar szolgáltatót nevezett meg, forrásmegjelöléssel.

Két nappal később gépileg megnéztük mind az ötöt. Az egyik megnevezett
domain mögött nincs működő weboldal: nincs érvényes biztonsági
tanúsítványa, és minden útvonala a tárhelyszolgáltató üres hibaoldalát
adja vissza. Egy robot ott tartalmat nem lát.

Nem a céget minősítem. A jelenséget.

A generatív válasz nem auditált lista. A modell egy nevet a korábban
begyűjtött adataiból is elő tud venni, akkor is, ha az oldal ma már nem
él. Ezért nem elég egyszer megnézni, hogy benne vagyunk-e.

Ugyanezt a nyolc kérdést lefuttattuk sima Google-keresőben is. Ott
tizenöt fölötti névsor jött ki, és a ChatGPT által idézett két legerősebb
szereplő közülük egyre sem volt rajta.

Vagyis a két találati halmaz nem ugyanaz. Aki a klasszikus keresőben erős,
attól még nem idézik, és fordítva.

Ebből két dolog következik a gyakorlatra:

1. Mérni kell, ismételten és dátumozva, nem egyszer.
2. A klasszikus keresőoptimalizálás nem ellentéte ennek a munkának, hanem
   az előfeltétele. A nagy motorok többnyire a meglévő keresők
   találataiból dolgoznak. Aki ott nincs ott, azt a modell be sem gyűjti.

Aki azt mondja, hogy a SEO már nem kell, az vagy félreérti, vagy
félrevezet.

A méréseink dátumozva vannak, és a módszer nyilvános. Kérdezzetek
nyugodtan.
```

### KÉP

Egy egyszerű táblázat-kép: a bal oszlopban „ChatGPT által idézve", a jobb oszlopban „Google
találati lista", és a kettő között egyetlen közös elem sincs bejelölve. Satoshi, sötét alap,
akcent kiemelés. Alternatíva: nincs kép, a LinkedIn a hosszú szöveget jól viszi.

### MIÉRT

Value Equation: **elhihetőség**, tiszta formában. Eredeti kutatás, amit senki más nem tud
idézni, mert nem az övé. Ez a poszt egyben a `10.7` kapu (idézhető konkrétum) gyakorlata a
saját tartalmunkon. Pillér: fájdalom. CTA szándékosan nincs, csak a mérés.

🔴 **Névvel szégyenítés nincs benne, és ne is kerüljön bele.** A tanulság a jelenség, nem a cég.

---

## 2. hét · csütörtök · P4 · Működés · Facebook + Instagram

### SZÖVEG

```
Van egy fájl a weboldalad gyökerében, amit soha nem nyitottál meg, és ami
el tudja tüntetni a céged a ChatGPT válaszaiból.

Írd be a böngésződbe a saját domained után, hogy /robots.txt. Például:
ateoldalad.hu/robots.txt

Egy rövid szöveges fájlt fogsz látni. Ebben mondod meg a robotoknak, hova
mehetnek be.

Itt jön a rész, amit a legtöbben összekevernek. Két teljesen különböző
robotcsalád van:

Tanító robotok: GPTBot, CCBot, Google-Extended. Ezek a modell tanításához
gyűjtenek. Ha nem akarod, hogy a szövegeidből tanuljanak, nyugodtan tiltsd
őket. Ez teljesen legitim döntés, és nem érinti a láthatóságodat.

Idéző robotok: OAI-SearchBot, ChatGPT-User, PerplexityBot, ClaudeBot. Ezek
akkor kérik le az oldalad, amikor a motor épp válaszol valakinek. Ha ezeket
tiltod, kizárod magad a válaszokból.

A baj az, hogy sokan az elsőt akarták, és a másodikat is letiltották.
Gyakran nem is ők, hanem a tárhelyszolgáltató vagy a biztonsági
szolgáltatás alapértelmezése.

Keress rá Ctrl+F-fel a négy idéző robot nevére. Ha valamelyik alatt ott áll
a Disallow: / sor, akkor megvan, miért nem jelensz meg sehol.

Ha a fájl nem is létezik, az jó hír: akkor nem tiltasz semmit.

Ez a tíz pontos öntesztünk ötödik pontja. A többi a linken.

tribloc.hu
```

### KÉP

Egy `robots.txt` részlet képként, kiemelve a `Disallow: /` sor egy idéző bot alatt, mellette
piros jelölés. Monospace betű a kódrészhez, minden más Satoshi.

### MIÉRT

Value Equation: **elhihetőség** (konkrét, ellenőrizhető mechanizmus) és **időigény**
(2 perc megnézni). Ez a poszt tanít valamit, amit a legtöbb versenytárs nem magyaráz el,
mert az ő terméküknek nem része.
Pillér: működés. CTA: az önteszt.

---

## 3. hét · kedd · P5 · Fájdalom · TikTok / Reels

### FORGATÓKÖNYV

1080 × 1920, jobbról 140 px és alulról 350 px levágva. Hossz: 28–34 másodperc.
Képernyőfelvétel telefonról vagy gépről, Beni hangja rá. **Ez a legmegosztásra
alkalmasabb formátum: kihívás, nem hirdetés.**

| Idő | Kép | Képernyőn megjelenő szöveg |
|---|---|---|
| 0:00–0:04 | Beni, közeli, egy mondat | `Csináld meg most, 30 másodperc` |
| 0:04–0:12 | Képernyő: megnyílik a ChatGPT, begépelt kérdés | `Ki a legjobb SZAKMA VÁROSBAN?` |
| 0:12–0:22 | A válasz megjelenik, görgetés a nevekhez | `Benne vagy?` |
| 0:22–0:28 | Vissza Benire | `Ha nem, ez a 3 leggyakoribb ok` |
| 0:28–0:34 | Három szó egymás után, gyors vágással | `1 láthatatlan kód · 2 tiltott robot · 3 nincs cégadat` |

**Szöveg alámondásra:**

```
Ezt csináld meg most, harminc másodperc.

Nyisd meg a ChatGPT-t, és kérdezd meg, hogy ki a legjobb a te szakmádban a
te városodban. Ahogy egy vevőd kérdezné, ne szakmai szavakkal.

Nézd meg a választ. Benne van a neved?

Ha nincs, annak három szokásos oka van. Vagy a weboldalad tartalmát nem
látja a robot, mert csak a böngésződben rajzolódik ki. Vagy egy sor a
beállításokban kitiltja azokat a robotokat, akiktől a megjelenést várnád.
Vagy nincs a kódban géppel olvasható cégadat, és a modell nem tudja
összekötni a rólad szóló említéseket.

Mind a hármat meg tudod nézni magad. A linken van hozzá egy tíz pontos
lista, harminc perc.
```

### CAPTION

```
Kérdezd meg a ChatGPT-t, ki a legjobb a te szakmádban a városodban. Ha nem
te jössz ki, a három leggyakoribb okot itt végig lehet nézni.
#vallalkozas #chatgpt #marketing #kisvallalkozas
```

### MIÉRT

Value Equation: **vágyott eredmény** (ott legyen a neved) és **időigény** (30 másodperc).
Kihívás-formátum, mert a néző azonnal el tudja végezni, és az eredmény személyes.
Pillér: fájdalom. CTA: profil-link.

---

## 3. hét · csütörtök · P6 · Működés · LinkedIn

### SZÖVEG

```
A legnagyobb hozamú munka az AI-láthatóságon nem tartalom, hanem egy
harmincperces technikai lépés, amit szinte senki nem csinál meg.

Úgy hívják, hogy entitás-feloldás. A lényege egy kérdés, amit a modellnek
el kell tudnia dönteni:

„Ez a sok különböző említés vajon ugyanarról a cégről szól?"

A weboldal, a Google Cégprofil, a Facebook-oldal, a LinkedIn cégoldal, a
szakmai katalógusok. Ha ezek nincsenek géppel összekötve, akkor a modell
számára nem egy cég van, hanem öt homályos folt. És a bizonytalan
említést a motor inkább nem mondja ki.

Három dolog kell hozzá, és egyik sem nagy munka:

1. Géppel olvasható cégadat a weboldal kódjában. A szakmai neve JSON-LD,
   és annyit mond ki, hogy ez egy vállalkozás, ez a neve, ez a címe, ezt
   csinálja.
2. Egy sameAs nevű felsorolás ugyanabban a blokkban, benne a valódi külső
   profilok címével. Ez köti össze őket.
3. Karakterre azonos név, cím és telefonszám mindenhol. Nem
   nagyjából-azonos.

Plusz egy negyedik, ami ingyen van: egyetlen, változatlan egymondatos
leírás, ilyen szerkezetben. Cégnév, mit csinál, kinek, hol. Ugyanaz a
mondat a weboldalon, a Cégprofilban, a közösségi oldalakon.

Az ismétlés az, ami összeköti az entitást. A variálás az, ami szétszedi.

Egy buktató, amibe magam is belefutottam: a Google saját tesztelője
futtatja a JavaScriptet, tehát zöldet mutathat olyan adatra, amit a
ChatGPT robotja soha nem lát. A nyers HTTP-válasz a mérvadó, nem a
tesztelő felülete.

Ellenőrzés harminc másodperc: nyisd meg a forráskódot, és keress rá arra,
hogy sameAs. Ha nulla találat, megvan a következő feladat.
```

### KÉP

Egy egyszerű ábra: középen a cégnév, körülötte öt doboz (weboldal, Cégprofil, Facebook,
LinkedIn, katalógus), és a `sameAs` a nyilak neve. Bal oldalon ugyanez nyilak nélkül,
szétesve. Satoshi, sötét alap, akcent nyilak.

### MIÉRT

Value Equation: **elhihetőség** (technikai mélység, saját tapasztalattal) és **erőfeszítés**
(30 másodperc az ellenőrzés). A LinkedIn-közönség ezt a mélységet díjazza, és ez a poszt
hozza a tech-hitelességet, amiből később az ügyfél-bizalom lesz.
Pillér: működés. CTA szándékosan nincs.

---

## 4. hét · kedd · P7 · Konverzió · Facebook + Instagram

### SZÖVEG

```
Összeraktuk egy dokumentumba az egészet, és ingyen letölthető.

A Láthatatlan Weboldal Teszt. Tíz ellenőrzés, harminc perc, és a végén
tudni fogod, hogy a ChatGPT, a Gemini és a Perplexity lát-e egyáltalán
valamit a weboldaladból.

Ami benne van:

Megjelensz-e ma egyáltalán a válaszokban, és ki jelenik meg helyetted.
Látszik-e a weboldalad JavaScript nélkül. Van-e géppel olvasható cégadat a
kódban. Össze van-e kötve az entitásod. Nem tiltod-e ki véletlenül azokat a
robotokat, akiktől a megjelenést várod. Kérdés alakú címsorok. Egységes név
és cím mindenhol. Idézhető konkrétum. És hogy kit idéz a motor helyetted.

Mindegyiknél oda van írva, hány perc, pontosan mit kell csinálnod, mit
jelent az eredmény, és mi a teendő, ha elbuktad.

Böngésző kell hozzá, más semmi. Fejlesztő nem kell. A végén van egy pontozó
tábla és egy módszer, amivel havonta vissza tudod mérni magad.

Egy dolgot érdemes tudni előre: amikor mi lefuttattuk ezt a tíz pontot a
saját weboldalunkon, kettőn elbuktunk. Bent hagytuk a dokumentumban, mert
az egész arról szól, hogy méréssel dolgozz, ne érzésre.

Ingyenes, és szabadon továbbadható.

tribloc.hu
```

### KÉP

A munkafüzet borítója, ahogy a nyomtatott változat kinéz: fejléc, cím, és a tíz ellenőrzés
címe listaként a percszámokkal. Ez maga a value stack képben. Satoshi, brand-paletta.

### MIÉRT

Value Equation: mind a négy tényező szerepel a szövegben. **Vágyott eredmény** (tudni fogod),
**elhihetőség** (a saját bukás beismerése), **időigény** (30 perc, percszámok),
**erőfeszítés** (böngésző, fejlesztő nem kell).
Pillér: konverzió. CTA: letöltés. A value stack felsorolás Hormozi §1.3.

🔴 **Az önbevallásos mondat kiküldés előtt visszamérendő** (`../ai-lathatosagi-onteszt/TEENDOK.md`
G1). Ha addigra javítottuk a két kaput, a mondatot át kell írni a javított állapotra, nem
kivenni.

---

## 4. hét · csütörtök · P8 · Konverzió · TikTok / Reels + LinkedIn

### FORGATÓKÖNYV (TikTok / Reels)

1080 × 1920, jobbról 140 px és alulról 350 px levágva. Hossz: 26–32 másodperc.
Beni arca végig, egy vágással. **Ez az egyetlen poszt, ami magunkról szól, ezért rövid.**

| Idő | Kép | Képernyőn megjelenő szöveg |
|---|---|---|
| 0:00–0:05 | Beni, közeli | `Novemberben indulunk` |
| 0:05–0:16 | Ugyanaz, közben rövid vágóképek a forráskód-nézetre | `Mérés · javítás · újramérés` |
| 0:16–0:24 | Vissza Benire | `Előjegyzés, nem vásárlás` |
| 0:24–0:32 | Zárókép: Tribloc szimbólum | `Rendszereket építünk, nem weboldalakat.` |

**Szöveg alámondásra:**

```
Novemberben indulunk, és az egyik dolog, amit csinálni fogunk, ez lesz.

Megmérjük, hogy a ChatGPT, a Gemini, a Perplexity és a Copilot válaszaiban
megjelensz-e a saját kategóriádban. Kijavítjuk azt, ami géppel láthatatlan
a weboldaladon. Utána havonta újramérjük, és kapsz róla egy oldalt.

Nem tanácsot adunk arról, hogy mit kellene csinálni. Elvégezzük, és
megmutatjuk a mért különbséget.

Amit nem ígérünk: garantált helyezést egyik motorban sem. A válasz nem
determinisztikus, és aki mást mond, azzal vigyázz.

Addig előjegyzés van, nem értékesítés. A linken az ingyenes önteszt, és
ott lehet feliratkozni.
```

### SZÖVEG (LinkedIn, ugyanaz a nap)

```
Négy hete írok arról, hogy mit lát a weboldaladból az a robot, amelyik a
ChatGPT-nek gyűjt. Lezárom egy mondattal arról, hogy mi ebből a munka.

Mérés, technikai javítás, újramérés. Ebben a sorrendben.

A mérés nyolc kérdés négy motoron, kézzel, dátumozva. Ez a nulladik nap, és
a munka elején adjuk oda, nem a végén. Aki az alapmérést a végén mutatja
meg, arra a szót kell adni.

A javítás nagyrészt technikai: géppel olvasható tartalom, cégadat a kódban,
összekötött profilok, kérdés-válasz szerkezet, és a robotok átengedése.
Nem szövegírás.

Az újramérés havonta, ugyanazzal a nyolc kérdéssel, változatlanul. Egy
átírt kérdés elveszíti az összehasonlítási alapot.

Három dolgot nem ígérünk, és ezt jobb előre kimondani:

Nem ígérünk megjelenést vagy helyezést. A generatív válasz nem
determinisztikus, motoronként és naponta eltér.

Nem cseréljük le a keresőoptimalizálást. A motorok többnyire a klasszikus
keresők találataiból dolgoznak, tehát ez ráépülő réteg, nem utód.

Nem ígérünk azonnali eredményt. A technikai javítások hetekben, a külső
jelenlét hónapokban mérhető.

Novemberben indulunk. Addig előjegyzés van.

Aki addig el akar kezdeni valamit egyedül: a profilomban van egy tíz
pontos önteszt, ingyenes, harminc perc, fejlesztő nélkül.
```

### MIÉRT

Value Equation: **elhihetőség**, a szűkítésen keresztül. A doktrína §1.4: amit nem vállalunk,
azt is mondjuk ki, mert a szűkítés növeli az elhihetőséget és a prémium-érzetet.
Pillér: konverzió. CTA: előjegyzés.

🔴 **Pályázati keret:** „előjegyzés, nem értékesítés" szó szerint benne van mindkét
változatban. Ár nincs, fizetési link nincs, nevesített ügyfél nincs.

---

## Ellenőrzőlista, mielőtt bármelyik poszt kimegy

```
[ ] Nincs benne mondat közi hosszú gondolatjel
[ ] A sales-mondatokban a motor NEVE áll, nem az „AI" mint önálló szó
[ ] Nincs benne szám, ami nem a saját, dátumozott mérésünkből jön
[ ] Nincs benne megjelenés- vagy helyezés-ígéret
[ ] Nincs benne ár, kosár, fizetési link, „megveheted"
[ ] Nincs benne nevesített ügyfél-referencia
[ ] Videónál: jobbról 140 px, alulról 350 px szabadon hagyva
[ ] Betűtípus Satoshi, stock fotó nincs
[ ] P7 előtt: a §6.5 önbevallás visszamérve (TEENDOK.md G1)
```

---

## Fizetett ág

Ez a fájl az ORGANIKUS hónap. A fizetett Meta-kampány terve külön:
[`kampany-meta-fizetett.md`](kampany-meta-fizetett.md) — az AI Kompatibilitás Teszt köré,
a webapp élesedése után indítható.
