
# Human Evaluation Setup

- Two LLMs generated responses for 50 source sentences, resulting in a total of 100 responses (50 responses per model).
- All responses were non-serially randomized prior to evaluation to minimize potential ordering and presentation biases.
- The evaluation workload was divided into two separate Google Forms (Part 1 and Part 2) for improved evaluator convenience and manageability.
- Each Google Form contained 50 evaluation tasks.
- During human evaluation, each page of the Google Form presented one and only one evaluation task, enabling focused assessment and reducing cognitive load for evaluators.

## Evaluation Guidelines

&gt; As an expert Odia (ଓଡ଼ିଆ) linguist and grammarian specializing in spelling, script, and grammatical evaluation, you will act as an evaluator for this Odia GEC (Grammatical Error Correction) study.

### Background (For your reference)

Each Odia sentence has been annotated for errors under exactly one of these five categories, applied in priority order:

1. **Script Normalization** — Unicode-level errors: nukta misplacement, incorrect virama, vowel sign decomposition, ZWNJ/ZWJ issues, unintended ligatures.
2. **Spelling & Typographical Errors** — Correct encoding but wrong characters: short/long vowel confusion, phonetically similar consonant substitution, missing/extra chars, wrong word boundaries.
3. **Grammatical Errors** — Morphosyntactic issues: wrong verb tense/inflection, agreement errors, wrong case markers, word order, faulty copular constructions, missing punctuation.
4. **Code-Mixing / Wrong Language** — Roman-script words, non-Odia numerals, other Indic script characters, unnecessary loanwords.
5. **Correct Sentence / No Errors** — No errors present.

### Annotation rules already applied

- Each sentence contains at most one error; only the primary erroneous span is marked.
- Span selection covers only the minimal necessary unit.
- If no error exists: the span is empty, the description states "no error," and the corrected sentence matches the source.
- Priority rule: If a span fits multiple categories, only the highest-priority category is assigned.

### Your Task — Evaluation Only

You will be presented with a source sentence and a submitted annotation response containing five fields: Has Errors, Error Span, Annotated Category, Description, and Corrected Sentence.

Your job is to judge the quality of that submitted annotation using the four criteria below. You do not have to re-annotate the sentence yourself — evaluate only what was submitted based on the established rules above.

---

#### C1 — Error Exists [0 or 1]

- **1**: The submitted "Has Errors" flag correctly reflects whether an error is present.
- **0**: Incorrect.

#### C2 — Span + Description [0, 1, or 2]

- **2**: Exact span AND fully correct explanation (identifies the error, why it is wrong, and the correct form).
- **1**: Partial span and/or incomplete explanation.
- **0**: Wrong span or irrelevant explanation.  
  *Note: If no error exists, the span must be empty and the description must state no error exists.*

#### C3 — Error Category [0 or 1]

- **1**: The submitted category is correct. If no error exists, it must be "Correct Sentence / No Errors."
- **0**: Incorrect.

#### C4 — Corrected Sentence [0, 1, or 2]

- **2**: Fully correct, fluent, and introduces no new errors.
- **1**: Mostly correct with minor issues.
- **0**: Incorrect, introduces new errors, or changes meaning.  
  *Note: If no error exists, this must match the source sentence exactly.*

---

### Submission Instructions

For each evaluation, please select the appropriate scores in the Google Form.
