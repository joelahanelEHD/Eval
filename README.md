# Mentor Teacher Scoring Practice

Calibration modules that train mentor teachers to rate interns with the
Internship Evaluation (updated 2026).

## Module 1 (pilot)

`modules/scoring-practice.html` is a single self-contained page. Mentors read
a scenario, choose a rating with the item's descriptors in front of them,
optionally note their evidence, then see the anchor rating with:

- the rationale, tied to the descriptor language
- key evidence
- why the rating is not one level higher or lower
- a calibration note where mentors commonly drift
- a sample evidence-based comment for Anthology Portfolio

| Item | Scenario | Context | Evidence type | Anchor |
| --- | --- | --- | --- | --- |
| G. Instructional Dialogue | G.1 Why did the bean grow pale? | Gr 3 science, Internship I final | Vignette | Developing |
| | G.2 Book clubs and question cards | Gr 5 ELA, Internship II final | Mentor notes over time | Proficient |
| | G.3 Two-step equations | Gr 7 math, Internship II midterm | Transcript | Unacceptable |
| | G.4 Can the testimony be trusted? | Gr 10 history, Internship II final | Transcript + context | Exemplary |
| P. Expectations for Student Behavior | P.1 Voice levels and carpet time | Kindergarten, Internship II midterm | Mentor notes over time | Proficient |
| | P.2 Fraction tiles | Gr 4 math, Internship II midterm | Vignette | Unacceptable |
| | P.3 Density lab, day one | Gr 8 science, Internship I final | Vignette | Developing |
| | P.4 Community agreements | Gr 11 English, Internship II final | Artifact + observation | Exemplary |

Items G and P were chosen because mentor–coach agreement on them was no better
than chance in the 2025–26 inter-rater reliability analysis: weighted kappa of
−0.12 to 0.11 for G and −0.01 to 0.09 for P. Exact agreement was 50–52% for G
and 34–44% for P, the lowest of any item. See `data/item_profiles_2025_26.json`.

**Anchor ratings are drafts and need faculty review before mentors use them.**

Ratings are saved only in the viewer's browser. Nothing is collected.

## Adding items and scenarios

All content lives in the `ITEMS` array in the page's script. To add an item,
copy an existing item object and fill in the following fields:

- `code`, `domain`, `name`, `stem`: from the instrument
- `descriptors`: the exact rubric text for `N`, `U`, `D`, `P`, `E`
- `scenarios`: each one has `body` blocks (`p`, `note`, `transcript`, `log`,
  `artifact`), an `anchor` level, `rationale`, `evidence`, `notUp`, `notDown`,
  an optional `caution`, and a sample `comment`

Each new item gets its own tab automatically.

## Data for building modules

`data/` holds inputs for writing new items, scenarios, cautions, and comment
exercises. It contains **aggregate statistics and invented examples only**.
No real assessor comments, names, or candidate records are in this repository.
See `data/README.md` for definitions and caveats.

- `data/item_profiles_2025_26.json`: one record per item (A–W) with
  mentor–coach agreement by term, final-rating distributions, and comment
  patterns (how often comments carry evidence, how often scores sit above the
  evidence, and which items comments get confused with).
- `data/comment_patterns.json`: invented example comments for a
  "Which comment supports this rating?" exercise, for items G, P, Q, A, and N.

Suggested next items, ranked from the 2025–26 data:

| Item | Exact agreement | Weighted kappa (mid / final) | Why |
| --- | --- | --- | --- |
| Q. Behavior Management | 42% | 0.10 / 0.05 | Second-lowest agreement; often confused with P, so it pairs well with the existing P scenarios |
| A. Content Understanding | 50% | 0.01 / −0.05 | Agreement at chance; 30% of comments are evaluation only, and 37% of scores sit above what the comment says |
| N. Student Metacognition | 48% | 0.13 / 0.04 | Low agreement; 57% of comments give no level evidence |
