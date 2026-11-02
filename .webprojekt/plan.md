# Weboldal-generálási terv — Eliza Beauty Salon

## Brand brief összefoglaló

Az Eliza Beauty Salon Sipos Eliza személyes kozmetikája Budapesten. A weboldal a személyre szabott bőrfiatalító és aknékezeléseket, Eliza szakértelmét és a nyugodt, privát vendégélményt mutatja be. Elsődleges célja az időpontkérések növelése; elsődleges CTA-ja az „Időpontot kérek”, másodlagos CTA-ja a „Megnézem a kezeléseket”. A megjelenés az elfogadott `design-system.md` színeit, Quicksand és Montserrat betűit, valamint az eredeti logót használja.

## Koncepció irányok

Mindhárom irány a jóváhagyott arculati szín- és betűrendszerre épül. A különbséget a hero képi kezelése, az oldalszerkezet, a tartalmi sűrűség, a bizonyítékok elhelyezése és a szekcióritmus adja.

1. **Szakértői műterem** (`koncepcio-1-szakertoi-muterem.html`) — osztott hero organikus portrékivágással; finom növényi vonalrajzok; tágas, váltakozó szekciók és korán megjelenő vendégvélemények. A felhasználó által küldött design referencia alapján frissítve.
2. **Csendes bőrtér** (`koncepcio-2-csendes-borter.html`) — széles kezelési fotó után külön szövegsáv; kiegyensúlyozott elrendezés; tömör kezelési csoportok és csomagok.
3. **A bőr útja** (`koncepcio-3-a-bor-utja.html`) — tipográfiai nyitás és képsáv; a négylépéses folyamat vezeti végig az oldalt.

A részletes, géppel olvasható specifikáció a `.webprojekt/iranyok.json` fájlban található.

## Mi készül el ebben a szakaszban

- Statikus HTML-projekt Tailwind CSS-sel.
- Három különböző kezdőoldal-prototípus önálló HTML-fájlként.
- `index.html` koncepció-navigátor, ahonnan mindhárom prototípus megnyitható.
- A már létező Git-repozitórium változatlanul megmarad; nem inicializálunk új repót és nem készítünk automatikus commitot.

A koncepció kiválasztása és finomítása után a kiválasztott irányt kiterjesztjük a briefben szereplő négy főoldalra és a láblécből elérhető adatkezelési tájékoztatóra.

## Hogyan nézd meg a prototípusokat

A projekt felállítása és a prototípusok elkészítése után nyisd meg az `index.html`-t böngészőben, majd válaszd ki valamelyik irányt:

- `koncepcio-1-szakertoi-muterem.html`
- `koncepcio-2-csendes-borter.html`
- `koncepcio-3-a-bor-utja.html`

