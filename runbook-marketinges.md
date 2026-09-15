# Runbook — a marketingesnek

> **Kinek szól:** aki a GEO-kampányt ténylegesen futtatja (ma Beni, később alvállalkozó vagy
> ügyfél-oldali marketinges). Ez a fájl arról szól, **hogyan megy ki a tartalom**, nem arról,
> hogy miről szól. A kész szövegek: [`kampany-2026-10.md`](kampany-2026-10.md).

---

## 0. Az egy mondat, amit nem lehet megkerülni

🔴 **A rendszer soha nem publikál magától. Piszkozatot hoz létre, és élő ember nyomja meg a
publikálást.** Ez Beni szabálya (2026-09-04), kódban kikényszerítve, öt teszt őrzi. Ha valaki
azt kéri, hogy „automatizáljuk végig", a válasz nem, és az ok nem kényelmi: a második szempár
látja a kész posztot úgy, ahogy megjelenik.

Két kapu van, és **mindkettő kell**:

| Kapu | Hol | Mit véd |
|---|---|---|
| 1. | nálunk: a poszt `scheduled` státuszban van **és** ki van töltve, hogy ki hagyta jóvá | a számonkérhetőséget, mert a napló a mi kezünkben van |
| 2. | a Postproxy felületén ember publikál | a második szempárt, és a nyom a szolgáltatónál keletkezik |

---

## 1. Mi működik MA, és mi nem

Ezt olvasd el, mielőtt bármit beütemezel. Mérve 2026-09-05-én.

| Felület | Állapot | Ma hogyan megy ki |
|---|---|---|
| **Facebook Oldal** | ✅ bekötve, a motor él | Piszkozat a motorból, ember publikál a Postproxy felületén |
| **Instagram** | 🔴 **nincs bekötve** | **Kézzel.** Az IG fióknak Business vagy Creator típusúnak kell lennie, Facebook Oldalhoz kötve. Személyes fiók semmilyen hivatalos úton nem érhető el |
| **TikTok** | 🔴 **nincs bekötve** | **Kézzel.** ⚠️ Auditálatlan API-kliensnél minden API-n feltöltött videó kényszerítetten csak a saját fiók számára látható. Ez nem hiba, hanem a TikTok szabálya. Amíg nincs auditált kliens, a TikTok **kézi feltöltés** |
| **LinkedIn** | 🟡 kézi, vagy Make-szcenárió | A `NEXUS - LINKEDIN - POSZTOK` Google Sheet a naptár. A Make-szcenárió aktiválása Beni döntése (a hozzáférési token 60 napig él, kézi megújítás kell) |

**Következmény a mostani kampányra:** a nyolc posztból **három megy a motoron keresztül**
(a Facebook-ág), **öt kézzel**. Ez rendben van, és nem érdemes miatta várni: heti két poszt
kézzel tíz perc.

⚠️ **Ügyfél Facebook- vagy Instagram-fiókjának kezeléséhez** magasabb szintű Meta-hozzáférés
kell, ahhoz igazolt Meta üzleti portfólió, ahhoz cég. A `09` szerint cég novemberig nincs.
**Saját csatornára a mostani szint elég.** Ez a kampány saját csatornára megy.

---

## 2. A négy hét menete

A kampány **heti 2 poszt, 4 héten át, összesen 8**. A pillérek aránya a `03-marketing.md`
4-4-2 sémájából jön, GEO-ra szabva: 3 fájdalom, 3 működés, 2 konverzió.

| Hét | Nap | # | Pillér | Felület | Hogyan megy ki |
|---|---|---|---|---|---|
| 1 | kedd | P1 | Fájdalom | Facebook + Instagram | FB a motoron, IG kézzel |
| 1 | csütörtök | P2 | Működés | TikTok / Reels (videó) | kézzel |
| 2 | kedd | P3 | Fájdalom | LinkedIn | kézzel vagy Sheet |
| 2 | csütörtök | P4 | Működés | Facebook + Instagram | FB a motoron, IG kézzel |
| 3 | kedd | P5 | Fájdalom | TikTok / Reels (videó) | kézzel |
| 3 | csütörtök | P6 | Működés | LinkedIn | kézzel vagy Sheet |
| 4 | kedd | P7 | Konverzió | Facebook + Instagram | FB a motoron, IG kézzel |
| 4 | csütörtök | P8 | Konverzió | TikTok / Reels + LinkedIn | kézzel |

**Miért kedd és csütörtök.** A LinkedIn-ritmus már így fut (`docs/handover_tartalom_2026-09.md`:
HU kedd, EN csütörtök), és két külön nap két külön felületen nem üti egymást.

**Ütközés-ellenőrzés a meglévő naptárral.** A LinkedIn-hónap 4 posztja (`marketing/kreativ/
linkedin-poszt-tervezetek.md`) már be van tervezve keddre. 🔵 **Beni dönti el**, hogy ez a
GEO-kampány mellette fut (heti 3 poszt összesen) vagy utána. Ha mellette: a P3 és a P6
csúszik csütörtökre, és a LinkedIn EN poszt marad el helyette.

---

## 3. A poszt kiküldésének lépései

### 3.1 Ami a motoron megy (Facebook)

1. **Piszkozat.** A poszt szövege bekerül a rendszerbe, `scheduled` státusszal és a tervezett
   időponttal.
2. **Jóváhagyás.** Ember jóváhagyja, és ezzel kitöltődik, hogy ki hagyta jóvá. Enélkül a
   kiküldő nem veszi fel. **Ez nem megkerülhető, és nem is akarjuk megkerülni.**
3. **A kiküldő** ötpercenként megnézi, van-e esedékes, és **piszkozatot** hoz létre a
   Postproxynál. Publikálni nem publikál.
4. **Publikálás.** Ember megnyitja a Postproxy felületét, megnézi a kész posztot úgy, ahogy
   megjelenik, és megnyomja a publikálást.

⚠️ **Ha a poszt nem jelenik meg**, a hiba a négy lépés közül az egyikben van, és ebben a
sorrendben nézd:
- a jóváhagyás tényleg meg van-e (a leggyakoribb ok),
- az időpont a jövőben volt-e a beütemezéskor,
- a kiküldő tényleg fut-e (a Cloudflare Worker naplója megmondja),
- a Postproxy felületén ott van-e a piszkozat. Ha ott van, akkor a lánc működött, csak nem
  nyomta meg senki.

### 3.2 Ami kézzel megy (Instagram, TikTok, LinkedIn)

1. Nyisd meg a [`kampany-2026-10.md`](kampany-2026-10.md) megfelelő posztját.
2. Másold ki a `SZÖVEG` blokkot változtatás nélkül.
3. Videónál: a `FORGATÓKÖNYV` blokk időzítéssel és a képernyőn megjelenő szöveggel dolgozik.
4. Töltsd fel, ellenőrizd a linket a leírásban vagy a profilban, publikáld.
5. Jelöld be a naptárban, hogy kiment.

---

## 4. Formai szabályok, amiket nem lehet átlépni

### 4.1 Kép és videó

| Felület | Méret | Vágás |
|---|---|---|
| TikTok / Reels | 1080 × 1920 | **jobbról 140 px, alulról 350 px levágva.** Semmi fontos ne kerüljön oda |
| Instagram feed | 1080 × 1350 | – |
| Instagram Story | 1080 × 1920 | – |
| Facebook borító | 1640 × 924 | biztonságos terület 1090 × 624, középen |

**Betűtípus: Satoshi, kivétel nélkül.** Ez nem stílus-preferencia, hanem márka-konstans.
**Stock fotó tilos.** Képanyag: `brand/kit/export/`, vagy natív képernyőkép a demóból.

⚠️ A TikTok sablonnak van egy `-safe-zone-guides` nevű változata a segédvonalakkal. **Azt nem
töltjük fel**, csak tervezéshez van.

### 4.2 Szöveg

- **Nincs mondat közi hosszú gondolatjel.** Ez a legfelismerhetőbb gépi-írás jel, és a poszt
  azonnal veszít a hiteléből. A rövid gondolatjel jó, a magyar helyesírás azt használja.
- **A sales-szövegben nincs „AI".** Nevezd meg a motort: ChatGPT, Gemini, Perplexity,
  Copilot. A `kampany-2026-10.md` szövegei már így vannak megírva, **ne írd át őket**.
- **Nincs tükörfordított szembeállítás.** Ahogy egy ember kimondaná hangosan.
- **Statisztika csak forrással.** 🔴 Ha egy szám nincs a `kampany-2026-10.md`-ben, akkor nem
  mértük, és nem is írjuk le. Kitalált szám az első visszaellenőrzésnél elviszi az egész
  kampányt.

### 4.3 Amit a pályázati keret miatt nem lehet leírni

- Nincs ár, nincs „megveheted", nincs fizetési link, nincs kosár.
- Nincs „azonnali projektindítás". A framing: **előjegyzés, novemberi indulásra**.
- Nincs nevesített ügyfél-referencia.
- A szolgáltatás megnevezése **fejlesztés és mérés**, nem tanácsadás.

---

## 5. Mit mérünk a kampányon

Négy szám, hetente egyszer, öt perc:

| Szám | Honnan | Mit jelent |
|---|---|---|
| Elérés és megtekintés posztonként | a felület saját statisztikája | melyik pillér működik: fájdalom, működés vagy konverzió |
| Kattintás a `tribloc.hu`-ra | Cloudflare Web Analytics, süti nélkül | a horog tényleg átvisz-e |
| Önteszt-letöltések | a letöltő űrlap beküldései | ez a kampány valódi eredménye, nem a lájk |
| Válaszmotor felőli forgalom | Cloudflare Web Analytics hivatkozó forrás | `chatgpt.com`, `perplexity.ai`, `gemini.google.com` |

🔴 **A negyedik szám a legfontosabb, és a legritkább.** Ha a kampány alatt akár egyetlen
látogató érkezik válaszmotor felől, az önmagában idézhető, dátumozott adat, amit a következő
poszt és a blogcikk használhat. Írd fel a napját.

**Amit ne mérj:** lájkszám önmagában. A `rutin-heti-tartalom.md` ritmusa 8–12 hét után ad
algoritmikus lendületet, tehát egy hónap után a lájkszám még zajt mér, nem trendet.

---

## 6. A kampány után

1. **A négy szám lejegyezve**, dátummal, a `rutin-heti-tartalom.md` „Eddig kész linkelhető
   anyagok" táblájába vagy mellé.
2. **A legjobban futó poszt** szövegéből lesz a következő blogcikk horga.
3. **Az önteszt letöltői** kapják meg elsőként a novemberi indulás hírét. Ez a lista a
   kampány valódi terméke.
4. 🔵 **Ha a P8 (előjegyzés) alulteljesít**, az nem a szöveg hibája automatikusan: négy hét
   túl rövid egy hideg közönségnél. A `marketing-hormozi-doktrina.md` §5 „Rule of 100"
   szabálya szerint 100 egység után értékelünk, nem 8 után.
