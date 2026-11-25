# And Security Light - változásnapló

## 2.1.1 - 2026-11-25
Sötét mód hover-javítás, több riasztási címzett, a szöveges beállítások mentése.
- **Javítás:** sötét módban a kurzor alá kerülő elemek (gombok, legördülő listák, aktív fül és szűrő) nem válnak olvashatatlanná.
- **Több címzett:** a riasztási e-mail-címek mezőbe több cím is írható (vesszővel, pontosvesszővel vagy új sorral), és kapcsolóval **minden adminisztrátor** is megkapja a riasztást. Mindenki külön levelet kap, a heti jelentés és a teszt-levél is mindenkihez elmegy.
- **Javítás:** a Beállítások szöveges mezői (CAPTCHA kulcsok, SMTP-kiszolgáló és -jelszó, riasztási címek, egyéni CSP) mostantól tényleg mentődnek. Ha korábban megadtál ilyet, ellenőrizd újra.

## 2.1.0 - 2026-11-25
Biztonsági varázsló, több riasztás, SMTP levélküldés, sötét mód javítások.
- **Biztonsági varázsló:** lépésenként, közérthetően végigvezet a hiányzó védelmeken; minden lépésnél leírja, **mit csinál**, **miért fontos**, **mire hat és mi a hátránya** - egy gombbal bekapcsolható vagy kihagyható.
- **"i" információs ikonok** a Beállítások címsorai mellett; a színük a funkció fontosságát mutatja (piros: kritikus, narancs: fontos, sárga: ajánlott, zöld: opcionális), világos és sötét témán is jól olvashatók.
- **Több e-mail riasztás:** új And Security Light verzió; az új verzió a régi PHP / WordPress miatt nem telepíthető; új WordPress-verzió (és ha újabb PHP kell hozzá); **heti biztonsági jelentés** minden hétfő reggel.
- **SMTP levélküldés (haladó):** ha a WordPress levélküldése nem megy, a bővítmény közvetlenül SMTP-n küld; kérésre a WordPress összes levele is az SMTP-n át megy; teszt-levél; a jelszó titkosítva tárolt.
- **Javítás:** a sötét mód nem vált vissza világosra gyors oldalváltás után.
- **Javítás:** a legördülő listák elemei sötét módban is jól olvashatók.

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
