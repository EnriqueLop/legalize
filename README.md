# Legalize

**Legislation as code.** Every law as a Markdown file. Every reform as a Git commit.

Legalize turns official legislation into version-controlled, machine-readable data. Browse the law, `git log` its history, `git diff` any reform — see exactly what changed, when, and why.

## Countries

| Country | Repo | Laws | Status |
|---------|------|------|--------|
| Spain | [legalize-es](https://github.com/EnriqueLop/legalize-es) | 8,600+ | Available |
| France | legalize-fr | — | Coming soon |
| United Kingdom | legalize-uk | — | Coming soon |
| Germany | legalize-de | — | Coming soon |

## How it works

Each law is a Markdown file with YAML frontmatter. When a reform is published, the file is updated and committed with the official publication date. The commit message includes the reform identifier and a link to the source.

**Standard Git tools become legal research tools:**

```bash
# Clone Spanish legislation
git clone https://github.com/EnriqueLop/legalize-es.git

# What does Article 135 of the Constitution say today?
grep -A 10 "Artículo 135" spain/BOE-A-1978-31229.md

# When did it change?
git log --oneline -- spain/BOE-A-1978-31229.md

# Show the exact diff of the 2011 fiscal stability reform
git diff 6660bcf^..6660bcf -- spain/BOE-A-1978-31229.md
```

## File format

Each file starts with YAML frontmatter:

```yaml
---
titulo: "Constitución Española"
identificador: "BOE-A-1978-31229"
pais: "es"
rango: "constitucion"
fecha_publicacion: "1978-12-29"
ultima_actualizacion: "2024-02-17"
estado: "vigente"
fuente: "https://www.boe.es/eli/es/c/1978/12/27/(1)"
---
```

The body is the full text of the law in Markdown.

## Why

Legal texts are amended constantly, but tracking those changes is surprisingly hard. Official sources publish consolidated versions with no easy way to compare them. Commercial providers charge hundreds of euros per month for access to version history.

Legalize is **open legal infrastructure**:

- **For developers** — build legal tools on structured, versioned data
- **For researchers & journalists** — explore the evolution of legislation with standard tools
- **For citizens** — see how the laws that affect you have changed over time

## API

Looking for programmatic access? The Legalize API is coming soon at [legalize.dev](https://legalize.dev) — search, filter, compare versions, and get notified when laws change.

## Data sources

All content is sourced from official government publications and linked back to the original. The legislative text is public domain. These repositories add structure, version control, and metadata — not original content.

Legalize uses the bulletin processing engine from [BoletinClaro.es](https://boletinclaro.es), a platform that makes Spain's official bulletins accessible and understandable.

## Contributing

Found an error in a consolidated text? A missing reform? Open an issue in the relevant country repo with the law name, article number, and the official source showing the correct version.

## Author

Created by [Enrique Lopez](https://enriquelopez.eu).

## License

Legislative content: public domain (sourced from official government publications).

Repository structure, metadata, and tooling: [MIT](LICENSE).

---

A project by [Enrique Lopez](https://enriquelopez.eu) · Powered by [BoletinClaro.es](https://boletinclaro.es) · [legalize.dev](https://legalize.dev)
