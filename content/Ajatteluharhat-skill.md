---
name: Bias
description: Use this skill when the user asks to analyze a source link or pasted source for thinking errors, cognitive biases, weak inferences, claims, interpretations, and alternative explanations; when the user asks to learn from saved bias-analysis reports and suggest wiki improvements; when the user asks to lint/evaluate the local thinking-error wiki for problems, contradictions, unclear items, duplication, or maintenance needs; or when the user asks to create Finnish adult-learning exercises/examples for recognizing cognitive biases. The skill reads the local Wiki vault, saves analysis reports to Soveltaminen, saves improvement and linting reports to Muutostarpeet, saves exercise pages to Harjoituksia, updates the relevant overview pages, and preserves Obsidian/Quartz compatibility.
---

# Bias

## Purpose

Analyze referenced source content against the local thinking-error wiki, produce Markdown reports, and maintain improvement/linting reports for the wiki.

When source content is Finnish, use Finnish section titles and labels throughout the report.

## Vault Conventions

Use the thinking-error wiki in the current knowledge base:

- `Wiki/Index.md`
- `Wiki/Ajatteluharhat kategorioittain.md` for category-grouped thinking-error links
- `Wiki/Soveltaminen.md` for links to source-specific analysis reports
- `Wiki/Muutostarpeet.md` for links to learning, improvement, and linting reports
- `Wiki/Harjoituksia.md` for links to exercise pages
- `Wiki/*.md`, excluding protected admin pages
- `Wiki/Soveltaminen/` for source-specific application/analysis reports
- `Wiki/Muutostarpeet/` for learning, improvement, and linting reports
- `Wiki/Harjoituksia/` for Finnish adult-learning example/exercise pages

If `Wiki/.obsidian` exists, `Wiki/` is the Obsidian vault root. Do not save Obsidian-linkable artifacts to sibling folders outside the vault.

Legacy compatibility:

- Read old `Wiki/Output/` reports only if `Wiki/Soveltaminen/` does not exist or if old content must be migrated.
- Read old `Wiki/Output learning/` reports only if `Wiki/Muutostarpeet/` does not exist or if old content must be migrated.
- Write generated artifacts only to their workflow folder: `Soveltaminen`, `Muutostarpeet`, or `Harjoituksia`.

Index rules:

- `Wiki/Index.md` is manually maintained by the human admin and should display as `Aloitus`.
- Preserve the exact first content line `INFO: [[Sivustosta]].` if it is present in `Wiki/Index.md`. Never remove, rewrite, move, duplicate, or automatically append generated workflow links to it.
- Add generated links only to the matching overview page: `Soveltaminen.md`, `Muutostarpeet.md`, or `Harjoituksia.md`.
- Keep `Ajatteluharhat kategorioittain.md` as the category-grouped bias index.

Protected admin pages:

- `Wiki/Opettaja-skill.md` and `Wiki/Sivusto-skill.md` are fully maintained by the human admin.
- Never read, inspect, edit, rewrite, translate, reformat, lint-fix, normalize links in, append links to, use as source context, or otherwise touch these two files.
- Exclude these two files from all workflows, generated-output targets, report evidence, and bulk maintenance operations over `Wiki/*.md`.

## Source Analysis Workflow

Use this workflow when the user asks to analyze a referenced source link or pasted source.

1. Inspect the source.
   - Extract the main article/content.
   - Ignore navigation, ads, cookie banners, recommendations, comments, and unrelated boilerplate.
   - Capture source title, author/publisher when available, URL, access date, and language.
   - If the page is inaccessible, ask for source text or a saved copy.
2. Load the thinking-error wiki.
   - Read `Wiki/Ajatteluharhat kategorioittain.md` first.
   - Load only relevant bias pages needed for the assessment.
   - Prefer specific wiki pages over broad category names.
3. Extract analytical units.
   - Separate **väitteet**, **päätelmät**, and **tulkinnat**.
   - Keep each unit concise and preserve enough context for fair assessment.
4. Assess each unit.
   - Identify possible thinking errors, if any.
   - Include confidence from 0.00 to 1.00.
   - Explain why the thinking error may apply and why it may not apply.
   - Provide alternative explanations that do not require assuming the identified error.
   - Assess reasoning in the text, not the author.
5. Save the report.
   - Create one new subfolder in `Wiki/Soveltaminen/` for each referenced source.
   - Save the Markdown report there.
   - Save cleaned source text and raw HTML/source capture there when available.
   - Use safe names:
     - folder: `YYYY-MM-DD-source-title`
     - report: `arvio.md`
     - text: `source.txt`
     - HTML: `source.html`
   - Never overwrite existing artifacts silently; append `-2`, `-3`, etc.
6. Update `Wiki/Soveltaminen.md`.
   - Create `Wiki/Soveltaminen.md` if needed.
   - Add one vault-local Obsidian wikilink to the saved report, omitting `.md`, for example:
     - `[[Soveltaminen/YYYY-MM-DD-source-title/arvio|Readable report title]]`
   - Avoid duplicate links.

## Muutostarpeet Workflow

Use this workflow when the user asks to learn from existing analysis reports, improve the wiki from prior assessments, identify patterns across reports, or produce suggestions for the thinking-error wiki.

All Muutostarpeet suggestion reports must be written only in Finnish, regardless of the language used in the user request or individual prior reports.

1. Determine the vault root.
   - If `Wiki/.obsidian` exists, use `Wiki/`.
   - Otherwise, use the current working directory.
2. Read analysis reports from `Soveltaminen/`.
   - Recursively inspect Markdown reports under `Soveltaminen/`.
   - Prefer files named `arvio.md`; read legacy files named `bias-assessment-*.md` if present.
   - Include other Markdown files only if they are clearly analysis outputs.
   - Ignore raw HTML, extracted source text, JSON fetch summaries, media, and boilerplate.
3. Read `Wiki/Ajatteluharhat kategorioittain.md`, `Wiki/Soveltaminen.md`, and only the wiki pages needed to judge report patterns.
4. Synthesize exactly 10 concrete suggestions for improving files in `Wiki/`.
   - Identify the target wiki page or index section.
   - Explain the evidence pattern from the reports.
   - Propose a specific improvement.
   - Include priority or expected impact.
   - Keep suggestions actionable but do not apply them.
5. Create `Muutostarpeet/` inside the vault root if needed.
6. Save the suggestions report as Markdown:
   - File: `kehitysehdotukset-YYYY-MM-DD.md`
   - If a file exists, append `-2`, `-3`, etc.
7. Update `Wiki/Muutostarpeet.md`.
   - Create `Wiki/Muutostarpeet.md` if needed.
   - Add one vault-local wikilink to the exact report, omitting `.md`, for example:
     - `[[Muutostarpeet/kehitysehdotukset-YYYY-MM-DD|Kehitysehdotukset YYYY-MM-DD]]`
   - Avoid duplicate links.
8. Tell the user the saved report path and that no wiki content pages were modified.

## Arviointi Linting Workflow

Use this workflow when the user asks to lint, review, evaluate, audit, quality-check, find contradictions, find unclear items, or identify problems in the wiki content itself.

1. Determine the vault root.
   - If `Wiki/.obsidian` exists, use `Wiki/`.
   - Otherwise, use the current working directory.
2. Read wiki content Markdown files.
   - Include `Index.md`, `Sivustosta.md`, `Ajatteluharhat kategorioittain.md`, and top-level thinking-error pages.
   - Exclude all files inside `Soveltaminen/`, `Muutostarpeet/`, and `Harjoituksia/`.
   - Exclude legacy `Output/` and `Output learning/` if they still exist.
   - Exclude protected admin pages `Opettaja-skill.md` and `Sivusto-skill.md`; do not read, inspect, or modify them.
   - Exclude `.obsidian/`, `Learning log/`, raw source captures, media, and non-Markdown files.
3. Analyze the wiki for quality problems.
   - Look for contradictions between definitions, examples, false-positive notes, categories, and related-error links.
   - Look for unclear wording, missing distinctions, duplicate concepts, broken or misleading links, inconsistent Finnish/English display names, stale paths, and structural inconsistencies.
   - Distinguish real problems from acceptable overlap between related thinking errors.
   - Do not modify wiki content pages.
4. Write a Finnish linting report titled `Arviointi`.
   - Create `Muutostarpeet/` if needed.
   - Save as `arviointi-YYYY-MM-DD.md`; append `-2`, `-3`, etc. if needed.
   - Use Finnish only.
5. Update `Wiki/Muutostarpeet.md`.
   - Create `Wiki/Muutostarpeet.md` if needed.
   - Add one link to the report, for example:
     - `[[Muutostarpeet/arviointi-YYYY-MM-DD|Arviointi YYYY-MM-DD]]`
   - Avoid duplicate links.
6. Tell the user the saved report path and that no wiki content pages were modified.

## Examples Workflow

Use this workflow when the user asks to create examples, exercises, practice cases, quizzes, or training material for recognizing cognitive biases or thinking errors.

All exercise pages must be written only in Finnish. Use an adult-learning difficulty level: realistic, nuanced, and specific enough that the answer is not obvious from a single keyword, but still solvable from the wiki.

1. Determine the vault root.
   - If `Wiki/.obsidian` exists, use `Wiki/`.
   - Otherwise, use the current working directory.
2. Read the wiki and prior examples.
   - Read `Wiki/Ajatteluharhat kategorioittain.md` first.
   - Read relevant top-level thinking-error pages from `Wiki/*.md`.
   - Do not read, inspect, or modify protected admin pages `Opettaja-skill.md` and `Sivusto-skill.md`.
   - Read Markdown analysis reports under `Soveltaminen/` for realistic source patterns and application examples.
   - Read all existing Markdown pages under `Harjoituksia/` if the folder exists.
   - Use prior `Harjoituksia` pages to avoid repeating examples, situations, answer biases, and distinctive wording.
3. Create exactly 8 new examples.
   - Each example must primarily demonstrate one cognitive bias from the wiki.
   - Prefer 8 different biases unless the user asks for a narrower theme.
   - Make examples concrete and adult-oriented: work, health, media, finance, organizations, decisions, expert judgment, or everyday reasoning.
   - Do not reveal the answer or bias name in the example text.
   - Avoid copying or lightly paraphrasing existing examples from `Harjoituksia/` or `Soveltaminen/`.
4. Put all examples first and all answers at the end of the same page.
   - The first section contains only the numbered examples.
   - The answer section comes after all examples.
   - Each answer names the cognitive bias using an Obsidian link to the wiki page and gives a concise justification.
5. Create `Harjoituksia/` inside the vault root if needed.
6. Save the exercise page as Markdown:
   - File: `harjoitukset-YYYY-MM-DD.md`
   - If a file exists, append `-2`, `-3`, etc.
7. Update `Wiki/Harjoituksia.md`.
   - Create `Wiki/Harjoituksia.md` if needed.
   - Add one vault-local wikilink to the exact page, omitting `.md`, for example:
     - `[[Harjoituksia/harjoitukset-YYYY-MM-DD|Harjoitukset YYYY-MM-DD]]`
   - Avoid duplicate links.
8. Tell the user the saved exercise page path.

## Examples Page Format

Use this structure for exercise pages:

```markdown
# Harjoitukset: ajatusvirheiden tunnistaminen

## Esimerkit

1. {Tilannekuvaus. Älä nimeä ajatusvirhettä tässä.}

2. {Tilannekuvaus.}

3. {Tilannekuvaus.}

4. {Tilannekuvaus.}

5. {Tilannekuvaus.}

6. {Tilannekuvaus.}

7. {Tilannekuvaus.}

8. {Tilannekuvaus.}

## Vastaukset ja perustelut

1. **Ajatusvirhe:** [[Wiki page name|Suomenkielinen nimi]]
   **Perustelu:** {Miksi juuri tämä ajatusvirhe on paras tulkinta. Mainitse tarvittaessa, miksi läheinen ajatusvirhe ei ole ensisijainen.}

2. **Ajatusvirhe:** [[Wiki page name|Suomenkielinen nimi]]
   **Perustelu:** ...
```

## Muutostarpeet Report Format

Use this structure for improvement reports:

```markdown
# Wikin parannusehdotukset ajatusvirhearvioiden perusteella

## Tiivistelmä

{Lyhyt yhteenveto aiempien arviointiraporttien toistuvista kuvioista.}

## 10 ehdotusta

| # | Kohde wikin tiedosto | Näyttö raporteista | Ehdotettu parannus | Prioriteetti |
|---:|---|---|---|---|
| 1 | [[43 Kehystys]] | ... | ... | Korkea |

## Huomiot ja rajaukset

- Nämä ovat vain ehdotuksia; wikin sisältösivuja ei muutettu.
- Ehdotukset perustuvat olemassa oleviin Soveltaminen-raportteihin ja voivat tarvita ihmisen tarkistuksen ennen toteuttamista.
```

## Arviointi Report Format

Use this structure for linting reports:

```markdown
# Arviointi

**Arvioidut tiedostot:** {count}
**Rajatut kansiot:** `Soveltaminen`, `Muutostarpeet`
**Luotu:** {YYYY-MM-DD}

## Tiivistelmä

{Lyhyt kokonaisarvio wikin kunnosta ja tärkeimmistä havainnoista.}

## Havainnot

| # | Kohde | Ongelmatyyppi | Havainto | Ehdotettu korjaus | Vakavuus |
|---:|---|---|---|---|---|
| 1 | [[43 Kehystys]] | Epäselvyys | ... | ... | Keskitaso |

## Ristiriidat ja päällekkäisyydet

{Mahdolliset käsitteelliset ristiriidat, päällekkäisyydet tai rajatapaukset.}

## Huomiot ja rajaukset

- Tämä on arviointiraportti; wikin sisältösivuja ei muutettu.
- Havainnot tarvitsevat ihmisen tarkistuksen ennen toteuttamista.
```

## Source Analysis Report Format

Use this structure for Finnish output:

```markdown
# Ajatusvirhearvio: {Source title}

**Lähde:** {URL}
**Tekijä / julkaisija:** {value or "Tuntematon"}
**Luettu:** {YYYY-MM-DD}
**Kieli:** {language}

## Tiivistelmä

{Short summary of the source and strongest reasoning risks.}

## Poimitut väitteet, päätelmät ja tulkinnat

| ID | Tyyppi | Poimittu yksikkö | Konteksti |
|---|---|---|---|
| C1 | Väite | ... | ... |
| I1 | Päätelmä | ... | ... |
| T1 | Tulkinta | ... | ... |

## Ajatusvirhearvio

### {ID}: {Short label}

**Tyyppi:** {Väite / Päätelmä / Tulkinta}

**Poimittu yksikkö:** ...

**Mahdolliset ajatusvirheet:**

| Ajatusvirhe | Luottamus | Miksi se voi soveltua | Miksi se ei välttämättä sovellu |
|---|---:|---|---|
| [[Wiki page name]] | 0.72 | ... | ... |

**Vaihtoehtoiset selitykset:**
- ...

**Arvio:** ...

## Kokonaiskuvio

{Repeated thinking-error patterns across the source.}

## Huomiot ja rajaukset

- Tämä arvio koskee tekstissä näkyviä päättely- ja esitystapoja, ei kirjoittajan aikomuksia tai luonnetta.
- Luottamuspisteet kuvaavat sopivuutta ajatusvirhewikiin ja käytettävissä olevaan kontekstiin.
```

## Assessment Guidance

- A claim can be true and still be presented through a thinking error.
- A weakly supported claim is not automatically a bias; identify the reasoning pattern.
- Prefer cautious language when confidence is below 0.70.
- If a unit is well-supported, say so and mark that no clear thinking error is identified.
- Distinguish missing evidence in the article from evidence that may exist elsewhere.
- Use Obsidian links to relevant wiki pages when saving inside the vault.
