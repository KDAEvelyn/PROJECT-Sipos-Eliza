# Eliza Beauty Salon — design system

Ez a dokumentum az Eliza Beauty Salon weboldalának **közös vizuális és tartalmi forrása**. Minden új oldal, komponens, űrlap és reszponzív állapot ezt a rendszert kövesse. A cél, hogy a felület minden pontján ugyanaz a márkakarakter jelenjen meg.

## Forrás és prioritás

Ez a specifikáció az `arculati-tabla.html` és az `arculati-tabla.css` alapján készült. A korábbi `eliza-alapanyag/design-system.md` fájlt `.disabled` kiterjesztéssel inaktívvá tettük; az nem része a weboldal tervezési rendszerének. **Eltérés esetén ez a gyökérmappában lévő fájl és az arculati tábla az irányadó.** Ne keverd össze a két palettát vagy tipográfiai rendszert.

Ha a rendszer később módosul, először ezt a dokumentumot és az arculati táblát frissítsd, majd a weboldal minden felületén vezesd át a változást.

## Márkakarakter

Az Eliza Beauty Salon személyre szabott, szakértő kozmetikai gondoskodást kínál. A megjelenés ezt a három érzetet közvetítse:

- **Nyugodt és gondoskodó:** tágas elrendezés, puha rózsás felületek, természetes ritmus.
- **Szakértő és megbízható:** tiszta hierarchia, jól olvasható szöveg, határozott bordó címek.
- **Nőies és barátságos:** lágy formák és kerekded címbetű, túlzó díszítés nélkül.

Kerülendő a harsány, csillogó vagy giccses rózsaszín hatás, az erős színátmenet, a zsúfoltság, a rideg technológiai megjelenés és az indokolatlanul sok dekoráció.

## Formanyelv és visszatérő motívum

- A fotók kaphatnak szabálytalan, organikus kivágást. A formák legyenek aszimmetrikusak és természetesek; ne ismételj minden képnél ugyanazt a kapszula-, kör- vagy boltívformát.
- A fehér felületek domináljanak, a halvány rózsaszín szakaszok tagolják az oldalt. A mély bordó használható egy-egy kontrasztos folyamat- vagy időpontkérő szakaszban, valamint a láblécben; ne váljon az oldal alapfelületévé.
- Visszatérő díszítőmotívumként használhatók finom, vékony növényi vonalrajzok. Kis kontraszttal, a tartalomtól távol és csak néhány szakaszban jelenjenek meg.
- A szolgáltatásokhoz használj egységes, vékony vonalú illusztratív ikonokat. Az ikonok kis méretűek, jelentést hordozók legyenek.
- Az organikus képformák és növényi vonalak a saját arculati terv vizuális elemei; ne váljanak minden felületet beborító mintává.

## Színrendszer

| Token | Szín | Hex | Használat |
|---|---|---|---|
| `rose` | Rózsás púder | `#D59999` | Elsődleges CTA, hangsúlyos link, kis márkaakcentus |
| `burgundy` | Mély bordó | `#3C0B1D` | Főcímek, fontos kiemelések, sötét felületek |
| `blush` | Halvány rózsaszín | `#F7EBEB` | Szekcióháttér, puha kiemelő felület |
| `text` | Grafitszürke | `#62636A` | Törzsszöveg, hosszabb leírások |
| `neutral` | Semleges szürke | `#828282` | Másodlagos információ, metaadat, visszafogott felirat |
| `border` | Finom szegély | `#DBDBDF` | Vékony elválasztók, kártya- és mezőkeretek |
| `white` | Tiszta fehér | `#FFFFFF` | Kártyák és tiszta tartalmi felületek |
| `page` | Meleg törtfehér | `#FCF9F8` | Fő oldalháttér |
| `canvas` | Világos szürkésbézs | `#EEE9E7` | Arculati tábla külső vászna; a weboldalon nem kötelező háttér |

### Színhasználati szabályok

- A `rose` az interakciók és CTA-k legfontosabb színe. Nagy, tömör felületen csak akkor használható, ha a fehér felirat olvashatósága megfelelő.
- A `burgundy` biztosítja a kontrasztos címsorokat és a márka mélységét. Sötét felületen fehér vagy világos szöveget használj.
- A `blush` felváltva alkalmazható a `white` és `page` felületekkel a tartalmi szakaszok ritmusának kialakítására.
- A `text` legyen az alapértelmezett hosszú szövegek színe; a `neutral` csak másodlagos információra való.
- A `border` maradjon finom, ne váljon dekoratív rácsrendszerré.
- Új színt csak indokolt állapothoz (például hiba vagy siker visszajelzéshez) adj hozzá, és dokumentáld.
- A kész felületen ellenőrizd a szöveg és háttér kontrasztját; a színpárok kontrasztértéke nincs automatikusan garantálva.

### CSS-változók

```css
:root {
  --color-rose: #D59999;
  --color-burgundy: #3C0B1D;
  --color-blush: #F7EBEB;
  --color-text: #62636A;
  --color-neutral: #828282;
  --color-border: #DBDBDF;
  --color-white: #FFFFFF;
  --color-page: #FCF9F8;
  --font-body: "Montserrat", Arial, sans-serif;
  --font-display: "Quicksand", "Montserrat", sans-serif;
}
```

## Tipográfia

A rendszer két betűcsaládot használ. Mindkettő támogatja a magyar ékezetes karaktereket; beágyazott használatkor az ő/ű karakterek megjelenését is ellenőrizd.

- **Quicksand:** H1–H3 címsorok és rövid, karakteres márkaüzenetek. Alapértelmezett vastagság: 600.
- **Montserrat:** törzsszöveg, navigáció, címkék, űrlapok és gombok.
- **Fallback:** Quicksand után Montserrat, majd általános sans-serif; Montserrat után Arial, majd sans-serif.

| Szerep | Betűcsalád / súly | Méret és sormagasság | Megjegyzés |
|---|---|---|---|
| H1 / oldal főcíme | Quicksand 600 | `clamp(42px, 5.2vw, 64px)` / 1.08 | Minden oldalon azonos skála |
| H2 / szekciócím | Quicksand 600 | `clamp(30px, 3.6vw, 44px)` / 1.15 | Minden szekcióban azonos skála |
| H3 / alcím, kártyacím | Quicksand 600 | 21px / 1.3 | Kártyákban és tartalmi blokkokban egységes |
| Lead / kiemelt bevezető | Montserrat 400 | 18px / 1.7 | Hero és fontos szekcióbevezetők |
| Törzsszöveg | Montserrat 400 | 16px / 1.7 | Minden normál leíró szöveg |
| Gomb, navigáció, mezőcímke | Montserrat 600 | 14px / 1.4 | Interaktív elemek egységes mérete |
| Kicker, meta, apró betű | Montserrat 400–700 | 12px / 1.5 | Kiegészítő információ; lényegi szöveget ne tegyél ide |

### Méretskála-tokenek

```css
:root {
  --type-h1: clamp(42px, 5.2vw, 64px);
  --type-h2: clamp(30px, 3.6vw, 44px);
  --type-h3: 21px;
  --type-lead: 18px;
  --type-body: 16px;
  --type-control: 14px;
  --type-small: 12px;
}
```

Ezek a tokenek a főoldalon és minden aloldalon ugyanazt jelentik. Ne adj egyedi betűméretet komponenshez: ha új szerep kell, előbb bővítsd ezt a skálát, és vezesd át minden oldalon.
Az élő méretskála a `typografia.css` fájlban van. A főoldalak és aloldalak ezt a közös fájlt töltsék be; ne tarts fenn külön tipográfiai értékeket az egyes oldalak CSS-ében.
Kivétel csak a valóban adatjellegű kiemelés lehet: árak, statisztikai számok és a folyamat lépésszámai. Ezek méretét ne használd normál címsorhoz vagy leíró szöveghez.

A címsorok legyenek jól tagoltak, de ne használj túl sok méretet egy nézetben. A törzsszöveg olvashatósága fontosabb a dekoratív tördelésnél. A nagybetűs megjelenés csak rövid gombfeliratnál vagy kis metaelemnél indokolt; hosszú szöveget ne szedj csupa nagybetűvel.

## Elrendezés és térközök

- A tartalom kapjon bőséges függőleges levegőt; a szekciók legyenek jól elkülönülő blokkok.
- A központi tartalom maximális szélességét a teljes weboldal terve rögzítse; az arculati tábla széles, 1440 px-es vászonra készült.
- Az arculati tábla desktopon 90 px belső oldalsó térközt, közepes nézetben 48 px-et, mobilon 22 px-et használ. Weboldalon ezeket a tartalom szélességéhez és viewporthoz igazítsd.
- A rácsoknál használj következetes oszlopközöket és igazításokat. A kártyák ne legyenek egymáshoz szorítva.
- Váltsd a `page`, `white` és `blush` háttereket, hogy a hosszú oldal jól követhető legyen.
- Mobilon az összetett, többoszlopos blokkok egy oszlopba rendeződjenek; a szöveg ne szoruljon keskeny oszlopokba.

## Komponensek

### Gombok és linkek

- **Elsődleges CTA:** rózsás púder (`rose`) háttér, fehér felirat, kapszulaforma, közepes belső térköz. Hover/fókusz állapotban legyen észrevehető, hozzáférhető visszajelzés.
- A gomb szövege legyen rövid és konkrét (például „Időpontot kérek”). Nyíl ikon hozzáadható, ha segíti a következő lépés értelmezését.
- A fő CTA kiemelkedhet, de ne versenyezzen vele egyszerre több egyforma erősségű gomb.
- A szöveges link legyen megkülönböztethető a környező szövegtől, ne csak szín alapján.

### Kártyák és felületek

- Használj fehér vagy halvány rózsaszín felületet, vékony `border` szegélyt és visszafogott sarkokat.
- Az árnyék legyen ritka és nagyon finom; a rétegzettséget elsősorban térközzel és háttérváltással jelezd.
- Egy kártyán belül a cím, rövid leírás és művelet hierarchiája legyen egyértelmű.

### Űrlapok

- A mezők címkéje legyen látható és közérthető; a placeholder ne helyettesítse a címkét.
- Használj világos felületet, finom szegélyt és jól látható fókuszállapotot.
- A hibát szövegesen is nevezd meg; a szín önmagában nem elég.
- A beküldés után egyértelmű siker- vagy hiba-visszajelzés szükséges.

### Ikonok és díszítőelemek

- Válassz egységes, vékony vonalas ikonkészletet. Az ikonok vizuális súlya maradjon visszafogott.
- Ikont csak akkor adj hozzá, ha jelentést közvetít vagy segíti a kezelést.
- A vékony növényi vonalrajz a dokumentált visszatérő motívum része; használd ritkán, a tartalom támogatására. Kerüld a sűrű virágmintát, csillogást és a túlzott ornamentikát.

## Képek és vizuális tartalom

- A fotók természetes, lágy fényűek legyenek; a bőrtónusok és a valós bőrtextúra maradjanak hitelesek.
- Előnyös a tiszta, világos, meleg környezet, krémes és púderes tónusokkal.
- A fotó mutasson valódi kezelési helyzetet, szakértelmet vagy nyugodt szalonélményt; kerüld a túlretusált, művi stock hatást.
- A képarány és vágás legyen következetes a hasonló komponensek között. A fontos arcok és kezelési részletek mobilon se vágódjanak le.
- Minden informatív kép kapjon érdemi magyar alt szöveget; dekoratív képnél használj üres alt attribútumot.

## Logóhasználat

A végleges logóforrások a `eliza-alapanyag/logo-palettahoz-igazitva/` mappában vannak:

- `logo.svg` — színes logó világos felületre.
- `logo-feher.svg` — fehér logó sötét felületre.
- `favicon.svg` — böngészőikon.

Mindig az eredeti SVG-t használd, tartsd meg az oldalarányt, ne színezd át és ne torzítsd. A logó körül legyen elegendő üres tér. Világos háttéren a színes, sötét háttéren a fehér változatot használd. A favicon méretben is maradjon tiszta és felismerhető.

## Interakció és hozzáférhetőség

- Minden interaktív elem legyen billentyűzettel elérhető, látható fókuszállapottal.
- A gombok és linkek érintési célja mobilon legyen kényelmes.
- Tartsd meg a szemantikus címsor-hierarchiát, és használj valódi gombot művelethez, valódi linket navigációhoz.
- Animáció csak finom és céltudatos legyen; ha `prefers-reduced-motion` aktív, csökkentsd vagy kapcsold ki.
- Ne közvetítsd az állapotot kizárólag színnel, és ellenőrizd a szövegkontrasztot a tényleges háttéren.

## Tartalmi hang

A weboldal magyar nyelven, közvetlenül és megnyugtatóan szóljon a látogatóhoz. Legyen szakértő, de ne kioktató; személyes, de ne túl bizalmaskodó. A szöveg a vendég igényeire és a kezelés érthető előnyeire fókuszáljon. Kerüld a túlzó, bizonyítatlan ígéreteket és a szakszavak magyarázat nélküli halmozását. A kész ügyfélszövegeket a `eliza-alapanyag/szovegek.md` tartalmazza; ahol ezek lefedik a tartalmat, azokat használd elsődlegesen.

## Ellenőrzőlista új felülethez

1. A paletta a dokumentált színtokeneket használja, új szín csak indokolt állapothoz került be.
2. A címsorok Quicksand, a felület- és törzsszövegek Montserrat betűvel készültek.
3. A fő CTA egyértelműen kiemelkedik, szövege konkrét.
4. A rózsás felületek és a bordó címek egyensúlyban vannak; az oldal nem túlzsúfolt.
5. A logó megfelelő változata szerepel, aránytorzulás nélkül.
6. A mobilnézet olvasható, a rácsok és űrlapok keskeny képernyőn is használhatók.
7. A képeknek van megfelelő alt szövegük, a fókuszállapotok láthatók, a kontraszt ellenőrzött.
8. A szöveg hangja illeszkedik a nyugodt, szakértő és személyes márkához.

