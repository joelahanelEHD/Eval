# Module data

Inputs for building mentor scoring-practice modules from the 2025–26
Internship Evaluation validity study. Generated October 15, 2026.

## What is and is not here

This repository is public, so these files hold **only aggregate statistics and
invented examples**.

- No assessor comments, real or de-identified.
- No candidate or assessor names or IDs.
- No row-level ratings.

Every example comment in `comment_patterns.json` was written for training.
A script compared each one with every real comment and confirmed that no
example shares a phrase of six or more words with any real comment, apart from
wording quoted from the public rubric. When you add examples, write them fresh
in the same style. Do not paste or lightly edit real comments.

## Files

### `item_profiles_2025_26.json`

| Section | What it holds |
| --- | --- |
| `meta` | Source, definitions, and status notes |
| `program` | Whole-instrument figures: coach–mentor and self–coach agreement, and comment patterns by rater type |
| `items[]` | One record per item, A–W in instrument order |

Each item record has:

- `coach_mentor_agreement.midterm` / `.final`: rating pairs, exact agreement, within one level, weighted kappa (quadratic), and the share of pairs where the mentor rated higher or lower.
- `final_rating_distribution.coach` / `.mentor`: share of final ratings at each level, and the share marked "no opportunity to observe".
- `comment_patterns`: from all coach and mentor comments on the item (41–111 per item; codebook v1.2). Shares of comments that say what the candidate does, that are evaluation only, that restate the rubric, that name a next step, or that give no level evidence. Among comments with both a signaled level and a score, the share where the score sits above or below the level the words convey. The on-construct share, and items comments were often really about (`often_confused_with`, from the 300-comment process test).

### `comment_patterns.json`

Pattern definitions with their 2025–26 frequency, and four invented example
comments each for items G, P, Q, A, and N. Each example gives the level it
supports (or `null`), a one-line explanation, and a revision tip for the item.

## Definitions

- **Ratings** are rounded down to the four rubric levels (2.5 → Developing, 3.5 → Proficient).
- **Exact agreement** is the share of coach–mentor pairs giving the same level to the same candidate, term, and item.
- **Weighted kappa** corrects agreement for chance; 0 means chance agreement, 1 perfect.
- **Signaled level** is the level a rater's own words convey ("no concerns" reads as Proficient; "an area of great strength" as Exemplary).
- **Score above signal** means the score is higher than the level the comment's words convey.
- **Coding reliability.** Comments were coded by Claude and checked against a human reviewer on two blind samples of 20 (pooled κ .65 and .57, below the .70 standard). Treat comment shares as directional.

## Caveats

- **Comment patterns are from a process test.** The 300 comments were coded by Claude alone, without human double-coding. Use them to design training, not as validity evidence, until the human-coded run is complete.
- **Small numbers.** Item-level comment figures rest on 7–17 comments, and agreement on about 50 candidates per term.
- **Drafts.** Anchor ratings and examples need faculty review before mentors use them.
