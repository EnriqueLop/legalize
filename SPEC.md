# Legalize Format Spec v0.2

Minimal contract for all country repos. Each country's legal system is different — this spec defines what MUST be consistent, and what each country decides for itself.

## Mandatory (all countries)

### YAML frontmatter

Every law file must have these 8 fields:

```yaml
---
title: "Full official title of the law"
identifier: "OFFICIAL-ID-123"
country: "xx"
rank: "law_type"
publication_date: "YYYY-MM-DD"
last_updated: "YYYY-MM-DD"
status: "in_force"
source: "https://official-source-url"
---
```

| Field              | Description                       | Format                                                                     |
| :----------------- | :-------------------------------- | :------------------------------------------------------------------------- |
| `title`            | Full official title               | String                                                                     |
| `identifier`       | Official ID from the source       | String (unique per country)                                                |
| `country`          | ISO 3166-1 alpha-2 country code   | `es`, `fr`, `se`, `kr`, `de`, `uk`, ...                                    |
| `rank`             | Type of legal text                | Free-form string, country-specific                                         |
| `publication_date` | Original publication date         | ISO 8601 date                                                              |
| `last_updated`     | Date of the latest reform included | ISO 8601 date                                                              |
| `status`           | Legal status                      | `in_force`, `repealed`, `partially_repealed`, `annulled`, or `expired`     |
| `source`           | URL to the official source        | Valid URL                                                                  |

Additional fields are welcome. Korea adds law sub-types, Spain adds `jurisdiction` for autonomous communities, the UK adds `type_code` and `document_main_type`, France may add code structure metadata. These are country-specific extensions.

### Commit format

```
[type] Title — articles affected

Source-Id: REFORM-ID
Source-Date: YYYY-MM-DD
Norm-Id: LAW-ID
```

Types: `[bootstrap]`, `[reform]`, `[new]`, `[repeal]`, `[correction]`, `[fix-pipeline]`

The commit's author date must be the real publication date of the reform, not the date the commit was created.

### Git identity

- **Author:** whoever runs the pipeline (from `git config user.name` / `user.email`)
- **Committer:** `Legalize <legalize@legalize.dev>` (or the pipeline's configured identity)

### Repository

One repo per country: `legalize-{code}` (e.g., `legalize-es`, `legalize-kr`, `legalize-de`).

Community contributions may live under the contributor's GitHub account (e.g., `9bow/legalize-kr`) and be listed in the hub.

## Flexible (per country)

Each country decides and documents in its own README:

- **Directory structure.** Spain uses flat `es/{id}.md`. Korea groups related laws `kr/{name}/`. France has one file per code `fr/{id}.md`. All valid.
- **What is a "law"?** Each legal system defines its own unit. Spain: individual law (BOE ID). France: consolidated code. Korea: act + decree + ordinance grouped. Sweden: individual statute (SFS number).
- **Rank values.** Free-form string. Spain: `ley`, `constitucion`, `real_decreto`. France: `code`, `loi`, `ordonnance`. Sweden: `lag`, `balk`, `forordning`. Korea: `법률`, `대통령령`, `부령`. UK: `public-general-act`, `statutory-instrument`.
- **Additional frontmatter fields.** Add whatever is useful for your legal system.
- **Language.** Each country's content is in its original language. Code, commit types, and trailer keys are in English.

## Versioning

This spec is v0.2. It will evolve as more countries join. Breaking changes will be announced in the hub repo. The `early-stage` notice in each country repo reflects this.

### Changelog

- **v0.2** — Frontmatter keys, status values, and commit types switched from Spanish to English to match the pipeline (see [legalize-pipeline#52](https://github.com/legalize-dev/legalize-pipeline/pull/52)). Added `annulled`, `expired` status values and `[fix-pipeline]` commit type. Existing commits in country repos retain their original labels (immutable git history).
- **v0.1** — Initial spec.
