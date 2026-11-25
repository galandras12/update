# And Security Light - frissítési adatok

A publikus **galandras12/update** tároló `and-security-light/` almappájába töltendő két fájl:

- `version.json` - a legfrissebb verzió gépi adatai; a `"plugin": "and-security-light"` mező kötelező;
- `changelog.md` - a verziónkénti újdonságok (`## 2.0.0 - 2026-11-25` fejlécű szakaszok).

A bővítmény ezeket olvassa (csak olvas, nem telepít): a fejlécben a verziószámra kattintva
látszik az újdonság, és új verziónál jelzés jelenik meg. A `download_url` mező elhagyható: ha
nincs megadva, a Letöltés gomb nem látszik. Csak HTTPS és GitHub-hosztok fogadhatók el.
