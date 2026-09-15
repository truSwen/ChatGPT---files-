# Fizetett Meta-kampány — az AI Kompatibilitás Teszt köré

> **Állapot: TERV, nem indítható.** Egyetlen blokkolója van, és az nem jogi: **a webapp
> még nem létezik**, tehát nincs hova vinni a forgalmat. Amint a `/onteszt` teszt-motorja
> él a Workeren, ez indulhat.
> Testvérfájl, organikus: [`kampany-2026-10.md`](kampany-2026-10.md) · a copy-szabályok:
> `CLAUDE.md` §3 · a keret: [`../../../memory/marketing-hormozi-doktrina.md`](../../../memory/marketing-hormozi-doktrina.md)

---

## 1. A pályázati keret: nem blokkoló, de a szövegben látszania kell

Beni döntése, 2026-09-07: **a hirdetés nem tiltott.** A `09` kizáró oka a regisztrált
vállalkozói státusz a támogatási kérelem napján, nem a marketing-aktivitás. Ma kizárólag
ingyenes dolgot kínálunk: **ingyenes teszt, ingyenes anyag, béta program, előjegyzés.**

Amit ezért a hirdetés és a landoló oldal **nem tartalmazhat**: ár, „megrendelem", kosár,
bankkártya, számlázás, konkrét szerződéskötési határidő, nevesített kész ügyfélrendszer.
Amit **tartalmazhat**: ingyenes teszt, ingyenes anyag, béta, előjegyzés novemberi indulásra.

---

## 2. A kreatív szabálya: nevesített motor, nem kategória

🔴 **A hirdetésben `ChatGPT` álljon, ne „AI keresők".** Egy konkrét, mindenki által ismert
név jobban kattint, mint egy kategória. A Gemini és a Perplexity magában a tesztben úgyis
benne van, tehát nem hazudunk, csak a legismertebb nevet tesszük előre.

A landoló oldal (a webapp) főcíme viszont maradhat kategóriás („Látják az AI keresők a
weboldaladat?"), mert ott már a teljes ígéretet kell lefednie. A hirdetés dolga a kattintás,
a landolóé a beváltás.

### Három induló változat

| # | Horog | Törzs | CTA |
|---|---|---|---|
| A1 | **Látja a ChatGPT a weboldaladat?** | 7 pontos gépi teszt. Beírod a címed, és 60 másodpercen belül tudod. Regisztráció és e-mail cím nélkül. | Teszt indítása |
| A2 | **A vevőd már nem keres. Kérdez.** | „Ki a legjobb klímaszerelő a XIII. kerületben?" A válaszban vagy benne van a neved, vagy nincs. Nézd meg 60 másodperc alatt. | Megnézem |
| A3 | **A weboldalad többsége a robotoknak nem létezik.** | Az idéző robotok nem futtatnak JavaScriptet. Ami csak a böngészőben rajzolódik ki, azt nem látják. 7 gépi ellenőrzés, 60 másodperc. | Lefuttatom |

`A1` a fő. `A2` a fájdalom-ág, `A3` a technikai ág. Mindhárom ugyanarra a landolóra megy.

---

## 3. A tölcsér, végponttól végpontig

```
Meta hirdetés  →  webapp (AI Kompatibilitás Teszt)  →  pontszám INGYEN, e-mail nélkül
                                                     →  „kérem a részletes anyagot"
                                                     →  e-mail + KÉT GOMB
                                                     →  PDF letöltés (+ opcionálisan hírlevél)
                                                     →  béta / előjegyzés
```

A két gomb kanonikus szövege (Beni, 2026-09-07): lila **„Letöltöm, és kérem a havi mérést"**,
fehér **„Csak a letöltés"**, a fehér is látható gomb legyen, ne link. Alatta értékajánlat,
**nem bűntudatkeltés**: a confirm-shaming elvetve, indoklás a `06` / e szál naplójában.

---

## 4. Amit a költés ELŐTT be kell kötni

Enélkül a pénz tanulás nélkül ég el:

1. **Konverziós esemény** a webappon: „teszt lefutott" és külön „e-mail megadva". Meta Pixel
   vagy Conversions API. A Meta enélkül nem tud optimalizálni, csak kattintásra.
2. **Webanalitika a landolón**, hogy a nem-Meta forgalom is elváljon.
3. **Egy lefutott organikus hét**, hogy legyen mihez hasonlítani a fizetett számot.

## 5. Célzás és költés

- **Célzás:** HU, 28-58, „small business owners" viselkedés. A magyar szakma-szintű célzás
  gyenge, ezért inkább **szélesen indul**, és a konverziós eseményre optimalizál.
- **Induló keret:** napi 3-5 ezer Ft, 7 nap, **egy** hirdetéskészlet, a három kreatív benne.
  Ez tanulási keret, nem skálázás.
- **Skálázás küszöbe:** heti 50 konverzió alatt a Meta tanulási fázisban marad, addig a
  költségvetés emelése nem javít semmit. Ez a szám dönt, nem az érzés.
- **Kiértékelés:** költség / lefutott teszt, és külön költség / megadott e-mail. A kettő
  aránya mondja meg, a landoló vagy az ajánlat gyenge-e.

---

## 6. Ami tilos

- Fizetett vendégposzt és linkvásárlás: **soha** (`rutin-heti-tartalom.md`).
- Backlink más saját oldalról: **teljes tiltás** (`05-dontesnaplo.md`, 2026-09-05).
- Mért szám a kreatívban visszamérés nélkül. A **60 másodperc** addig nem mehet ki, amíg
  Workerben nem futott le és nem mértük.
