# And Security Light - változásnapló

## 2.0.0 - 2026-11-25
Teljes körű biztonsági továbbfejlesztés, új felülettel. PHP 7.4.33-tól 8.5-ig fut.
- **Erősebb tűzfal:** SSRF, XXE, Log4Shell (elfedve is), Shellshock, sablon-injektálás, prototípus-szennyezés, parancs-befecskendezés, hibaalapú SQL-injektálás; minden HTTP fejléc, JSON-kulcs és XML-törzs vizsgálata; kódolási trükkök (túlhosszú UTF-8, teljes szélességű és láthatatlan karakterek, 5+ rétegű kódolás) ellen.
- **Ellenállóbb:** korlátos minták (ReDoS ellen), kérésenkénti vizsgálati keret, mezőszám- és törzsméret-korlát, nagy törzs eleje és vége is vizsgált, CSRF-védelem idegen eredetű admin-kérésekre.
- **Kétfaktoros hitelesítés (TOTP):** QR-kód, mentési kódok, visszajátszás és találgatás elleni védelem.
- **CAPTCHA és botvédelem:** csapdamező, időcsapda, saját számtani feladat, Turnstile, hCaptcha, reCAPTCHA v2.
- **Okos zárolás:** fokozódó zárolás, elosztott támadás elleni fiókvédelem, e-mail új eszközről történt belépésről.
- **Fájlvédelem:** a mag és a bővítmények ellenőrzése, változásfigyelés, futtatható fájl a feltöltések közt, karantén, biztonságos Médiatár-feltöltés.
- **HTTP fejlécek:** HSTS, Content-Security-Policy, Permissions-Policy, COOP, CORP - beállíthatóan, alapból kikapcsolva a kockázatosak.
- **Naplózás és riasztás:** admin-tevékenység, támadás-korreláció, e-mail riasztások gyakoriság-korláttal.
- **Új felület:** világos / sötét téma (AJAX-kapcsoló), biztonsági állapot-lista, verzió-ellenőrző a fejlécben.
