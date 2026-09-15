# Runbook — az ügyfélnek

> **Ez a dokumentum kifelé adható.** Az ajánlat mellé megy, vagy önállóan, ha valaki azt kérdezi,
> hogy „és pontosan mi történik". Nincs benne belső hivatkozás, nincs benne szakzsargon
> magyarázat nélkül.
>
> 🔴 **Kiküldés előtt:** az árak a `memory/07`-ből valók, a menetrend a `09`-ből. Ha bármelyik
> változott, ez a fájl elavult. A `07` a kanonikus.

---

## Mit csinálunk, egy mondatban

**Megmérjük, hogy a ChatGPT, a Gemini, a Perplexity és a Copilot válaszaiban megjelensz-e a
saját kategóriádban, kijavítjuk azt, ami géppel láthatatlan a weboldaladon, majd havonta
újramérjük.**

Nem tanácsot adunk arról, hogy mit kellene csinálni. Elvégezzük, és megmutatjuk a mért
különbséget.

---

## 1. Miért számít ez most

Egy vevőd egy része már nem a találati listán keres, hanem kérdez. Beírja, hogy „ki a legjobb
klímaszerelő a XIII. kerületben", és a kapott három-négy nevet elhiszi. Aki nincs a válaszban,
az nem a tizedik helyen van, hanem sehol, mert a válasz nem sorol fel tíz céget.

Amit a legtöbben nem tudnak: **a válaszmotorok robotjai többnyire nem futtatnak
JavaScriptet.** Ha a weboldalad tartalma csak a böngészőben rajzolódik ki, akkor számukra
üres. Ez nem azt jelenti, hogy rossz a weboldalad. Azt jelenti, hogy egy másik közönségnek
nem olvasható.

---

## 2. A két szolgáltatás

### 2.1 GEO Alapozó Audit és Setup

Egyszeri munka, körülbelül **két hét** átfutással.

| Lépés | Mit csinálunk | Mit kapsz a végén |
|---|---|---|
| 1. Alapmérés | Összeállítunk 8 kérdést, ahogy a vevőd kérdezné, és lefuttatjuk mind a négy motoron | Egy dátumozott lap: melyik motorban jelensz meg, melyikben nem, és ki jelenik meg helyetted |
| 2. Gépi átvizsgálás | Megnézzük, mit lát a weboldaladból az a robot, amelyik nem futtat JavaScriptet | Egy lista arról, mi hiányzik, és mindegyiknél az, hogy miért számít |
| 3. Javítás | A kulcstartalom géppel olvashatóvá tétele, cégadat-jelölés a kódban, a külső profiljaid összekötése, kérdés-válasz szerkezet és jelölés | Élesített weboldal, visszamért állapottal |
| 4. Robotok átengedése | Ellenőrizzük, nem tiltod-e ki véletlenül azokat a robotokat, akiktől a megjelenést várod | A javított beállítás, és annak leírása, mi maradt szándékosan tiltva |
| 5. Záró mérés | A gépi ellenőrzés újra lefut | Egy előtte-utána lap, dátumokkal |

**Ár:** l. az ajánlatot. Fix összeg, nem óradíj.

### 2.2 GEO Monitorozás és Optimalizálás

Havidíjas, **minimum három hónap**.

Ez nem árazási feltétel, hanem szakmai. Az alapmérés a nulladik hónap, az első
összehasonlítható adat a harmadik. Egy hónapra nem adjuk el, mert a végén nem tudnánk mit
mutatni.

| Havonta | Mit csinálunk |
|---|---|
| Mérés | Ugyanaz a nyolc kérdés, változatlanul, mind a négy motoron. Kézzel, dátumozva |
| Karbantartás | Amit a mérés kihoz: hiányzó kérdés-válasz blokk, elavult cégadat, szétcsúszott elérhetőség |
| Robot-forgalom | Megnézzük, jártak-e nálad a válaszmotorok robotjai, és mikor |
| Forgalom-kimutatás | Érkezett-e látogató a `chatgpt.com`, a `perplexity.ai` vagy a `gemini.google.com` felől |
| Jelentés | **Egy oldal**, dátumozva: mi változott, mi nem, mi a következő lépés |

---

## 3. Neked mi a dolgod

Ez a rész azért van itt, mert ez szokott a kérdés lenni. **Összesen két dolog:**

1. **Hozzáférés a weboldalad szerkesztéséhez** (vagy a fejlesztőd elérhetősége). Ha nem tudod,
   hol van, segítünk kideríteni.
2. **Egy jóváhagyás** arra a nyolc kérdésre, amit mérni fogunk. Húsz perc, mert te tudod, hogy
   a vevőd hogyan kérdez.

Ennyi. A mérés a mi időnk, a javítás a mi munkánk, a jelentés a te postafiókodba érkezik.

**Ami nem kell:** nem kell fejlesztőt keresned, nem kell szoftvert venned, nem kell új
weboldal. Az esetek nagy részében a meglévőn dolgozunk.

---

## 4. Amit garantálunk, és amit nem

**Amit garantálunk:**
- A mérés minden hónapban lefut, és megkapod írásban, dátummal.
- Az alapmérést a munka **elején** kapod meg, nem a végén. Így a végén nem csak a szavunkra
  kell hagyatkoznod.
- Minden javítás visszamérve kerül át, nem „elvégeztük" alapon.

**Amit nem garantálunk, és aki garantál, azzal vigyázz:**
- **Nem ígérünk megjelenést vagy helyezést egyetlen válaszmotorban sem.** A válasz nem
  determinisztikus: motoronként, felhasználónként és naponta eltér. Aki garantált első helyet
  ígér egy AI-válaszban, ugyanazt ígéri, mint aki garantált első Google-helyet.
- **Nem cseréljük le a keresőoptimalizálást.** A motorok többnyire a klasszikus keresők
  találataiból dolgoznak. Ha ott nem vagy ott, a modell be sem gyűjt. Ez ráépülő réteg.
- **Nem ígérünk azonnali eredményt.** A technikai javítások hetek alatt jönnek át, a tartalmi
  és a külső jelenlét hónapokban mérhető.

---

## 5. Gyakori kérdések

**Kell hozzá új weboldal?**
Az esetek nagy részében nem. Egyetlen eset van, amikor igen: ha a weboldalad teljes tartalma
kliensoldali szkriptből jön, és a platform, amin épült, nem tud szerveroldali renderelést.
Ezt az első héten megmondjuk, és akkor te döntesz.

**Mennyi idő alatt látszik meg valami?**
Nincs rá garantált idő. Amit tudunk: a technikai javítások hetekben, a tartalmi és külső
jelenlét hónapokban mérhető. Ezért van a három hónapos minimum, és ezért mérünk havonta.

**Miért kézzel mértek, és nem automatával?**
Mert a motorok nem adnak megbízható gépi felületet ehhez, a kimásolásuk pedig a feltételeikbe
ütközik. Aki azt mondja, hogy nála ez teljesen automatizált, attól kérdezd meg, hogyan.

**Mi történik, ha három hónap múlva nem mozdult semmi?**
Megkapod a három hónap mérését, és leülünk átnézni, mit mutat. Ha az látszik, hogy a
kategóriádban a válaszok kizárólag katalógusokból és listacikkekből épülnek, akkor a munka
kifelé folytatódik, nem a weboldaladon. Ezt előre megmondjuk, nem utólag.

**Mi az az `llms.txt`, amit mások emlegetnek?**
Egy 2024-es javaslat egy fájlra, ami géppel olvasható összefoglalót ad a tartalmadról.
Kirakjuk, harminc perc, ártalmatlan. **De egyetlen nagy motor sem erősítette meg
nyilvánosan, hogy használja.** Aki ezt adja el a szolgáltatás fő eszközeként, az túlárazza.

---

## 6. Ha most szeretnél elkezdeni valamit, ingyen

Van egy tíz pontos önteszt, amit **fél óra alatt magad is lefuttatsz** a weboldaladon.
Böngésző kell hozzá, más semmi, és nem kell fejlesztő. A végén tudni fogod, hogy géppel
látszol-e egyáltalán.

**`tribloc.hu`**

---

*Novemberben indulunk. Addig előjegyzés van, nem értékesítés.*
*Tribloc. Rendszereket építünk, nem weboldalakat.*
