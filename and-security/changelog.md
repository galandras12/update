# And Security - változásnapló

## 1.8.5 - 2026-11-23
Az update tároló több bővítményt is kiszolgálhat: az And Security adatai külön almappában és kifejezett azonosítóval érkeznek.
- **Saját almappa:** az adatok címe `update/main/and-security/` lett.
- **Bővítmény-azonosító:** a `version.json` `"plugin": "and-security"` mezője kötelező; más bővítmény fájlját a verzió-ellenőrző elutasítja.

## 1.8.4 - 2026-11-23
A letöltés gomb csak akkor jelenik meg, ha az új verzióhoz van letöltési hivatkozás.
- **Letöltés csak hivatkozással:** a "Letöltés" gomb és a telepítési útmutató csak akkor látszik, ha a `version.json` tartalmaz `download_url` mezőt.

## 1.8.3 - 2026-11-23
Verzió-ellenőrző és újdonságok a fejlécben.
- **Új verzió jelzése:** a bővítmény naponta kétszer megnézi ezt a tárolót, és a fejlécben a verziószám mellett jelzi, ha újabb kiadás van.
- **Újdonságok:** a verziószámra kattintva lenyílik egy panel az új verzió változásnaplójával és a letöltési hivatkozással.
- **Biztonságos:** csak olvas, nem telepít és nem küld webhelyadatot; a letöltést te indítod.
- **E-mail értesítés** verziónként egyszer (kikapcsolható), és az "Ellenőrzés most" gomb.

## 1.8.2 - 2026-11-23
Modern, látványos kinézet minden kiküldött levélnek.
- **Egységes levélsablon:** súlyosság-jelvény és szín, adatkártya, gomb, sötét mód, mobilbarát elrendezés.
- **Kétfaktoros kód** nagy, külön dobozokban; levélminták a Beállítások › Értesítések oldalon.

## 1.8.1 - 2026-11-20
Biztonsági audit és javítás - **azonnali frissítés ajánlott**.
- **2FA-megkerülés javítva:** a jelszavas belépéskor kiadott munkamenet a második lépés előtt megsemmisül.
- **WAF-megkerülések javítva** (`?action=mesterjelszo_verify`, hamis `h2f_pending_token` süti); IP-hamisítás helyi proxy mögött.
- **TOTP-kulcsok titkosítása** az adatbázisban, TOTP-visszajátszás és párhuzamos találgatás elleni védelem.
- **Fájlfeltöltés és kártevő-keresés** megerősítve, 20+ új WAF-szabály.

## 1.8.0 - 2026-11-20
Beépült a Hitelesítő+ (kétfaktoros hitelesítés).
- **Automatikus átállás** a különálló Hitelesítő+ bővítményről: a kulcsok, mentési kódok és passkey-ek változatlanul működnek.
- **Passkey, hitelesítő alkalmazás, e-mail kód és mentési kódok**, szerepkör alapú kötelezővé tétellel.
