# Chatbot configuration

Both chatbots were built as **custom GPTs** (OpenAI GPT-4o) in a licensed ChatGPT Business workspace, in which interactions are excluded from model training. No model was trained or fine-tuned. Each role was defined entirely by configuration:

| Component | AI Tutor | AI Student |
|---|---|---|
| Instructions field (system prompt) | [`ai-tutor/instructions.md`](ai-tutor/instructions.md) | [`ai-student/instructions.md`](ai-student/instructions.md) |
| Knowledge file (reference guide, incl. rubric and scoring guide) | [`ai-tutor/knowledge.md`](ai-tutor/knowledge.md) | [`ai-student/knowledge.md`](ai-student/knowledge.md) |
| Role | Asks Socratic questions about the group's papers and gives brief formative feedback | Explains the papers as a peer with one intentional higher-level misconception per explanation, which the group must detect and correct |
| Evaluation rubric | Knowledge file §7 (criteria) and §8 (scoring guide) | Knowledge file §9 (criteria) and §10 (scoring guide); score must be below 50% if the group repeatedly accepts flawed explanations |

**Source papers.** Each group selected two papers (one conference, one journal paper) within its simulation domain and uploaded both PDFs to the chat at the start of its session. The papers are not included in this repository.

**Misconceptions (AI Student).** Misconceptions were not pre-written for each paper. The knowledge file (§3–4) defines a typology of twelve higher-level mistake types (e.g., misinterpreting the main contribution, overgeneralising findings, confusing correlation with causation) and lists shallow factual mistakes to avoid. The chatbot generated one mistake of a suitable type for each explanation at run time, based on the uploaded papers.

**Session flow (both roles).** Group check-in → pre-questionnaire → upload of both papers → 6–8 interaction rounds covering both papers (with a comparison round where the papers are comparable) → teaching-back prompt → time checks at ~30 and ~60 minutes → locked self-assessment → final AI evaluation → post-questionnaire → submission of the shared chat link.

**Locked self-assessment.** Before asking the group for its self-assessment, the chatbot committed to its score by displaying a code equal to the score plus 137 (e.g., `[R:219]` for 82%), so the AI score could not be adjusted after seeing the group's self-score.

**Files.** The `.md` files are verbatim conversions of the Word documents that were pasted into (instructions) and uploaded to (knowledge) the custom GPTs. Text is reproduced exactly as used, including some repeated passages. Questionnaire links were placeholders (`[PRE-QUESTIONNAIRE LINK]`) in the published version.
