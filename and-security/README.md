# And Security - frissítési adatok

Ezek az **And Security** nevű WordPress bővítmény (teljes verzió) kiadási adatai.
A publikus **https://github.com/galandras12/update** tárolóban minden bővítmény
a saját almappájába kerül, így később más bővítmények fájljai is megférnek egymás
mellett. Az And Security mappája: **`and-security/`**.

## Hova töltsd fel

A főtároló `update/and-security/` mappájának tartalmát a publikus tároló
`main` ágán az **`and-security/`** almappába kell feltölteni, így a végső szerkezet:

```
galandras12/update  (main)
└── and-security/
    ├── version.json
    ├── changelog.md
    └── README.md        (opcionális)
```

A bővítmény innen olvassa:

* `https://raw.githubusercontent.com/galandras12/update/main/and-security/version.json`
* `https://raw.githubusercontent.com/galandras12/update/main/and-security/changelog.md`

A mappa a főtárolóban azért van, hogy kiadáskor ugyanazzal a commit-tal frissüljön,
mint a bővítmény - a kiadás után a fájlokat kell felmásolni a publikus tárolóba.

## Azonosítás

A `version.json` **`"plugin": "and-security"`** mezője kötelező. Ha hiányzik vagy más
érték áll benne (például egy másik bővítmény fájlja került a helyére), a bővítmény
elutasítja, és a panelben jelzi az okot. A `"name"` mező csak emberi azonosításra való.
A `changelog.md` első sora is megnevezi a bővítményt (`# And Security - változásnapló`).

## `version.json`

| Mező | Jelentés |
|---|---|
| `plugin` | **Kötelező, értéke: `and-security`.** A bővítmény-azonosító; enélkül a fájl nem fogadható el. |
| `name` | Opcionális, emberi azonosításra: `And Security`. |
| `version` | A legfrissebb kiadás (`x.y.z`). Ha nagyobb a telepítettnél, a bővítmény jelzi. |
| `released` | Kiadás dátuma (`ÉÉÉÉ-HH-NN`). |
| `min_php`, `min_wp` | Minimális PHP / WordPress (a panel figyelmeztet, ha a webhely régebbi). |
| `severity` | `normal`, vagy `security` (piros jelzés, a levél is "biztonsági frissítés"). |
| `download_url` | **Opcionális.** A ZIP letöltési címe; ha nincs megadva, a panelben nem jelenik meg a "Letöltés" gomb és a telepítési útmutató.  **Csak HTTPS és github.com / githubusercontent.com** fogadható el. |
| `info_url` | Opcionális: további információ (ugyanez a korlát). |
| `summary` | Egy rövid mondat az új verzióról (a panelben és az e-mailben látszik). |

## `changelog.md`

Szakaszok `## x.y.z - ÉÉÉÉ-HH-NN` fejléccel (a kötőjel lehet "–" is), alattuk egy
opcionális bevezető sor és `- ` felsorolás. Legfeljebb 20 szakaszt és szakaszonként 30
elemet olvas be. A szövegben `**félkövér**` és `` `kód` `` használható, minden más
szövegként jelenik meg (HTML nem).

A verziószámra kattintva a **telepítettnél újabb** szakaszok látszanak (az újdonságok);
ha nincs újabb, a telepített verzió saját szakasza.

## Kiadás menete

1. A bővítmény új ZIP-je a `releases/` mappában (a `download_url` erre mutat, vagy töltsd
   fel a ZIP-et máshová, és ott add meg).
2. `version.json`: `version`, `released`, `summary` frissítése; `download_url` csak akkor, ha a ZIP letölthető (enélkül nincs letöltés gomb).
3. `changelog.md`: új szakasz **az elejére**.
4. A fájlok feltöltése a publikus `galandras12/update` tároló `and-security/` almappájába.

A bővítmény ezután legfeljebb 12 órán belül jelzi az új verziót; az
**Ellenőrzés most** gomb azonnal lekéri.

## Hiba esetén

Ha a fájl hibás (érvénytelen JSON, rossz verzióformátum, nem engedélyezett hoszt), a
bővítmény nem jelez semmit, a panelben a hiba okát mutatja, és egy óra múlva próbálja
újra. A hiba soha nem akasztja meg az admin felületet.
