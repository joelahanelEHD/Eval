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

Items G and P were chosen because exact mentor–coach agreement on them was
near zero in the 2026 inter-rater reliability analysis.

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
