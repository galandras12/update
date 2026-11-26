# Frissítési adatok

A publikus **galandras12/update** tároló tartalma. Minden bővítmény a saját almappájában
tartja a kiadási adatait (`version.json` + `changelog.md`), a `version.json` pedig
kötelezően megnevezi a bővítményt (`"plugin": "..."`), így nem téveszthetők össze.

| Almappa | Bővítmény | `plugin` azonosító |
|---|---|---|
| [`and-security/`](and-security/) | And Security (teljes verzió, WordPress bővítmény) | `and-security` |
| [`and-security-light/`](and-security-light/) | And Security Light (PHP 7.4+) | `and-security-light` |

Új bővítmény felvétele: új almappa + saját `plugin` azonosító; a már meglévők fájljai
érintetlenek maradnak.
