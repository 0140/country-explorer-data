# Country Explorer data

The country data used by the Country Explorer app. The app downloads
[`countries.json`](countries.json) from this repository and caches it on the device:

```
https://raw.githubusercontent.com/0140/country-explorer-data/main/countries.json
```

## What is in the file

A JSON list of 250 countries and territories, one per line. Each entry has:

| Field | Meaning |
| --- | --- |
| `name.common`, `name.official` | Short and official names |
| `cca2`, `cca3` | ISO 3166-1 two- and three-letter codes |
| `capital`, `capitalInfo.latlng` | Capital city (or cities) and its coordinates |
| `region`, `subregion` | For example `Europe` / `Western Europe` |
| `population`, `area` | People, and area in km² |
| `flags.png`, `flags.svg`, `flags.alt` | Flag image addresses and a description of the flag |
| `latlng` | Rough centre of the country |
| `independent` | `true` for sovereign states |
| `languages`, `currencies`, `timezones` | Official languages, currencies, UTC offsets |

## Changing the data

Edit `countries.json` and commit. Keep it valid JSON with the same fields: the app
ignores a file it cannot read and falls back to the copy bundled inside the app.
Phones pick up a change the next time they refresh, at most about a week later.

## Source and licence

`countries.json` is derived from the REST Countries dataset
(https://gitlab.com/restcountries/restcountries, file
`src/main/resources/countriesV3.1.json`), reduced to the fields listed above.

It is made available under the Mozilla Public License 2.0, the licence of the original
dataset. See [LICENSE](LICENSE), or https://mozilla.org/MPL/2.0/.
