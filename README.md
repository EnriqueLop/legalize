# Legalize

**Legislation as code.** Every law as a Markdown file. Every reform as a Git commit.

Legalize turns official legislation into version-controlled, machine-readable data. Browse, search, diff, and build on structured legal data from 20 countries.

**[legalize.dev](https://legalize.dev)** — Browse laws, see diffs, search across legislation.

## Countries

| Country | Repo | Laws | Source | Status |
|---------|------|------|--------|--------|
| 🇵🇹 Portugal | [legalize-pt](https://github.com/legalize-dev/legalize-pt) | 109,347 | [DRE](https://dre.pt/) | ✅ Live |
| 🇮🇹 Italy | [legalize-it](https://github.com/legalize-dev/legalize-it) | 86,496 | [Normattiva](https://www.normattiva.it/) | ✅ Live |
| 🇺🇸 United States | [legalize-us](https://github.com/legalize-dev/legalize-us) | 59,765 | [OLRC](https://uscode.house.gov/) | ✅ Live |
| 🇵🇱 Poland | [legalize-pl](https://github.com/legalize-dev/legalize-pl) | 34,115 | [Sejm ELI](https://api.sejm.gov.pl/eli) | ✅ Live |
| 🇦🇹 Austria | [legalize-at](https://github.com/legalize-dev/legalize-at) | 21,825 | [RIS](https://www.ris.bka.gv.at/) | ✅ Live |
| 🇳🇱 Netherlands | [legalize-nl](https://github.com/legalize-dev/legalize-nl) | 20,390 | [BWB](https://wetten.overheid.nl/) | ✅ Live |
| 🇨🇿 Czech Republic | [legalize-cz](https://github.com/legalize-dev/legalize-cz) | 18,337 | [e-Sbírka](https://e-sbirka.gov.cz/) | ✅ Live |
| 🇧🇪 Belgium | [legalize-be](https://github.com/legalize-dev/legalize-be) | 17,742 | [Justel](https://www.ejustice.just.fgov.be/) | ✅ Live |
| 🇱🇻 Latvia | [legalize-lv](https://github.com/legalize-dev/legalize-lv) | 15,005 | [likumi.lv](https://likumi.lv/) | ✅ Live |
| 🇱🇹 Lithuania | [legalize-lt](https://github.com/legalize-dev/legalize-lt) | 14,945 | [TAR](https://www.e-tar.lt/) | ✅ Live |
| 🇪🇸 Spain | [legalize-es](https://github.com/legalize-dev/legalize-es) | 12,235 | [BOE](https://www.boe.es/) | ✅ Live |
| 🇺🇾 Uruguay | [legalize-uy](https://github.com/legalize-dev/legalize-uy) | 10,155 | [IMPO](https://www.impo.com.uy/) | ✅ Live |
| 🇸🇪 Sweden | [legalize-se](https://github.com/legalize-dev/legalize-se) | 8,939 | [Riksdagen](https://data.riksdagen.se/) | ✅ Live |
| 🇬🇷 Greece | [legalize-gr](https://github.com/legalize-dev/legalize-gr) | 6,803 | [ΕΤ](https://search.et.gr/) | ✅ Live |
| 🇨🇱 Chile | [legalize-cl](https://github.com/legalize-dev/legalize-cl) | 6,401 | [BCN](https://www.leychile.cl/) | ✅ Live |
| 🇩🇪 Germany | [legalize-de](https://github.com/legalize-dev/legalize-de) | 5,729 | [GII](https://www.gesetze-im-internet.de/) | ✅ Live |
| 🇦🇩 Andorra | [legalize-ad](https://github.com/legalize-dev/legalize-ad) | 3,537 | [BOPA](https://www.bopa.ad/) | ✅ Live |
| 🇦🇷 Argentina | [legalize-ar](https://github.com/legalize-dev/legalize-ar) | 1,909 | [InfoLEG](https://servicios.infoleg.gob.ar/) | ✅ Live |
| 🇪🇪 Estonia | [legalize-ee](https://github.com/legalize-dev/legalize-ee) | 1,597 | [Riigi Teataja](https://www.riigiteataja.ee/) | ✅ Live |
| 🇫🇷 France | [legalize-fr](https://github.com/legalize-dev/legalize-fr) | 83 codes | [Légifrance](https://www.legifrance.gouv.fr/) | ✅ Live |
| 🇰🇷 South Korea | [legalize-kr](https://github.com/9bow/legalize-kr) | 5,575 | [law.go.kr](https://open.law.go.kr) | ✅ Community |
| 🇺🇦 Ukraine | [legalize-ua](https://github.com/legalize-dev/legalize-ua) | — | [Rada](https://zakon.rada.gov.ua/) | 🚧 Pipeline ready |
| 🇮🇪 Ireland | [legalize-ie](https://github.com/legalize-dev/legalize-ie) | — | [ISB](https://www.irishstatutebook.ie/) | 🚧 Pipeline ready |
| 🇫🇮 Finland | — | — | [Finlex](https://www.finlex.fi/) | 🔜 Help wanted |
| 🇧🇷 Brazil | — | — | [LeXML](https://www.lexml.gov.br/) | 🔜 Help wanted |

**Want to add your country?** See the [step-by-step guide](https://github.com/legalize-dev/legalize-pipeline/blob/main/ADDING_A_COUNTRY.md).

## How it works

Each law is a Markdown file with YAML frontmatter. When a reform is published, the file is updated and committed with the official publication date.

Standard Git tools become legal research tools:

```bash
# Clone Spanish legislation
git clone https://github.com/legalize-dev/legalize-es.git

# What does Article 135 of the Constitution say today?
grep -A 10 "Artículo 135" es/BOE-A-1978-31229.md

# When did it change?
git log --oneline -- es/BOE-A-1978-31229.md

# Show the exact diff of the 2011 fiscal stability reform
git diff 6660bcf^..6660bcf -- es/BOE-A-1978-31229.md
```

## Repos

| Repo | What |
|------|------|
| **[legalize](https://github.com/legalize-dev/legalize)** | This repo. Index, docs, overview. |
| **[legalize-pipeline](https://github.com/legalize-dev/legalize-pipeline)** | The engine. Fetches, parses, and commits legislation for 20+ countries. |
| **[legalize-pt](https://github.com/legalize-dev/legalize-pt)** | Portuguese laws (109,347 norms). |
| **[legalize-it](https://github.com/legalize-dev/legalize-it)** | Italian laws (86,496 norms). |
| **[legalize-us](https://github.com/legalize-dev/legalize-us)** | United States Code (59,765 sections). |
| **[legalize-pl](https://github.com/legalize-dev/legalize-pl)** | Polish laws (34,115 acts). |
| **[legalize-at](https://github.com/legalize-dev/legalize-at)** | Austrian laws (21,825 norms). |
| **[legalize-nl](https://github.com/legalize-dev/legalize-nl)** | Dutch laws (20,390 norms). |
| **[legalize-cz](https://github.com/legalize-dev/legalize-cz)** | Czech laws (18,337 norms). |
| **[legalize-be](https://github.com/legalize-dev/legalize-be)** | Belgian laws (17,742 norms). |
| **[legalize-lv](https://github.com/legalize-dev/legalize-lv)** | Latvian laws (15,005 norms). |
| **[legalize-lt](https://github.com/legalize-dev/legalize-lt)** | Lithuanian laws (14,945 norms). |
| **[legalize-es](https://github.com/legalize-dev/legalize-es)** | Spanish laws (12,235 norms + 17 autonomous communities). |
| **[legalize-uy](https://github.com/legalize-dev/legalize-uy)** | Uruguayan laws (10,155 norms). |
| **[legalize-se](https://github.com/legalize-dev/legalize-se)** | Swedish statutes (8,939 laws). |
| **[legalize-gr](https://github.com/legalize-dev/legalize-gr)** | Greek laws (6,803 ΦΕΚ). |
| **[legalize-cl](https://github.com/legalize-dev/legalize-cl)** | Chilean laws (6,401 norms). |
| **[legalize-de](https://github.com/legalize-dev/legalize-de)** | German laws (5,729 laws). |
| **[legalize-ad](https://github.com/legalize-dev/legalize-ad)** | Andorran laws (3,537 norms). |
| **[legalize-ar](https://github.com/legalize-dev/legalize-ar)** | Argentine laws (1,909 norms). |
| **[legalize-ee](https://github.com/legalize-dev/legalize-ee)** | Estonian laws (1,597 norms). |
| **[legalize-fr](https://github.com/legalize-dev/legalize-fr)** | French codes (83 codes). |
| **[legalize-kr](https://github.com/9bow/legalize-kr)** | South Korean laws (5,575 laws). Community contribution by [@9bow](https://github.com/9bow). |

## Why

Legal texts are amended constantly, but tracking changes is hard. Official sources publish consolidated versions with no way to compare. Commercial providers charge hundreds per month for version history.

Legalize is open legal infrastructure:

- **For developers** — structured, versioned legal data with a REST API
- **For researchers and journalists** — explore the evolution of legislation with git
- **For citizens** — see how the laws that affect you have changed

## Contributing

The main contribution is adding a new country. Read the [format spec](SPEC.md) for the minimal contract, then follow the [step-by-step guide](https://github.com/legalize-dev/legalize-pipeline/blob/main/ADDING_A_COUNTRY.md).

You can use the shared [legalize-pipeline](https://github.com/legalize-dev/legalize-pipeline) or build your own pipeline — as long as the output follows the spec. South Korea was built with an independent pipeline and it works great.

Found an error in a law text? Open an issue in the relevant country repo with the law name, article, and the official source showing the correct version.

## Support

Legalize is open source and free. If you want to help fund hosting and development:

- [Open Collective](https://opencollective.com/legalize)
- [Buy me a coffee](https://buymeacoffee.com/elopcast)

## License

Legislative content: public domain (sourced from official government publications).
Repository structure, metadata, and tooling: [MIT](LICENSE).

---

Created by [Enrique Lopez](https://enriquelopez.eu) · [legalize.dev](https://legalize.dev)
