# JobFinder (Windows 10/11)

Helyi program: a profession.hu és kiválasztható cégek karrieroldalai → a keresésednek megfelelő állások, a CV-dhez illesztve,
motivációs levelekkel és jelentkezés-követéssel. Minden adat (CV-k, találatok, jelentkezések) a saját gépeden marad.

## Telepítés
1. Töltsd le a `JobFinder-Setup-X.exe` telepítőt a kiadási oldalról, és futtasd. (Windows SmartScreen: *További információ → Futtatás mindenképp*.)
2. A varázslóban kiválaszthatod a parancsikont, az indítást a Windowsszal, a böngészőmotort (a JavaScriptes cégoldalakhoz ajánlott) és a napi automatikus keresést.
3. Indítás: asztali parancsikon → http://127.0.0.1:8766

## Első lépések
1. **Beállítások › Keresési profil**: pozíciók, tapasztalati szint, város (Budapestnél kerületek), kizárások. Vagy tölts fel CV-t a **CV-k** fülön: a program a CV-ből kikövetkezteti a pozíciókat (AI-kulccsal pontosabban).
2. **Beállítások › Cégek**: kapcsold be a cégeket, amelyeknek a karrieroldalát nézze, vagy add hozzá a sajátodat.
3. **profession_jobs**, **ceg_jobs** vagy **Mindkettő** gombbal indíthatod a keresést.

## Visszajelzés és találatminőség
- Minden állásnál 👍 / 👎: a „nem releváns” állás a Korábbiak közé kerül. Ezekből tanulunk a következő verziókban.
- „⏳ valószínűleg állandóan nyitott”: hónapok óta kint lévő, vagy sokadszorra újrahirdetett irodai és szakértői állások jelzése (Beállítások › Keresési profil: elrejthető). A vendéglátás, kereskedelem, logisztika stb. munkaköröket ez nem érinti, ott a folyamatos toborzás természetes.
- Jobb felső **Visszajelzés** gomb: hiba vagy ötlet küldése diagnosztikai adatokkal (a küldés előtt látod és szerkesztheted; CV, név, e-mail és API-kulcs nincs benne).
- Béta-tesztelőknek: `docs/BETA_UTMUTATO.md` és `docs/BETA_ELLENORZOLISTA.md`.

## Frissítés
A program indításkor és félóránként megnézi az interneten, van-e új verzió, és jelzi (alapértelmezett). Egy kattintással telepíthető, az adatok megmaradnak, a telepítés előtt mentés készül (`data\backups`). Beállítások › Frissítések: jelzés / automatikus / kikapcsolt; haladó: helyi mappa vagy saját forrás.

## Eltávolítás
Windows **Beállítások › Alkalmazások › Telepített alkalmazások › JobFinder › Eltávolítás** (vagy Start menü › JobFinder eltávolítása).
Az eltávolító megkérdezi, törölje-e a mentett adatokat (CV-k, találatok, jelentkezések, beállítások, API-kulcs). Az ütemezett napi keresést is törli. A böngészőmotort (`%LOCALAPPDATA%\ms-playwright`) más programok is használhatják, ezt nem törli.

## Korlátok
- A profession.hu-nak nincs nyilvános API-ja; a program az oldalt olvassa, tartja a robots.txt-t, késleltet. Mérsékelten használd (napi 1–2×), és nézd meg az oldalak felhasználási feltételeit.
- A kerületszűrő a hirdetés helyéből (irányítószám, „XIII. kerület”) dolgozik; ha egy hirdetésből nem derül ki, megtartja.
- A cégoldalak változnak; ha egy oldal nem olvasható, a **Cégek állapota** fülön látod.
- A program a kereséshez nem kér előfizetést; az AI-funkciók (CV-elemzés, levelek) opcionális Anthropic API-kulccsal pontosabbak, ez külön, használatalapon számlázódik.

## Fejlesztőknek
Lásd `docs/KIADAS.md` (kiadás menete, build) és `docs/JOGI_ES_TERMEK_MEGJEGYZESEK.md`.
