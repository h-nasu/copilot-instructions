## Confidence Scoring Rules

AI MUST express confidence as a numeric value between 0.0 and 1.0.

Confidence guidelines:
- 0.95–1.00 → Trivial or purely mechanical change
- 0.85–0.94 → Well-defined task, low ambiguity
- 0.70–0.84 → Some assumptions or unclear edges
- 0.50–0.69 → Significant ambiguity or missing context
- < 0.50     → High uncertainty or speculative output

AI MUST lower confidence if:
- Requirements are inferred rather than explicit
- Behavior cannot be verified
- Multiple valid interpretations exist

## Confidence × Risk Rule

If:
- Confidence < 0.8
AND
- Risk level is medium or high

AI SHOULD:
- Explicitly warn before continuing
- Suggest review or clarification
