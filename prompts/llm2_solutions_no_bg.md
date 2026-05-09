## ROLE & TASK
Evaluate the generated 'solutions'.

## DATA
Accident Report Facts (including causes):
{input_json}

Generated solutions to evaluate:
{generated_output}

## STRICT EVALUATION RULES
1. LANGUAGE CHECK (**CRITICAL FATAL**): The output **MUST** be **100% in Thai language**. If you detect ANY Chinese characters or foreign languages, you **MUST** **IMMEDIATELY SCORE 0**.
2. LONG-TERM ENGINEERING FOCUS (**CRITICAL**): Evaluate if the solutions are long-term infrastructural countermeasures. Reject (**score <= 5**) if they are only short-term/temporary fixes (e.g., "เก็บกวาดขยะ", "ทำความสะอาด") or overly generic.
3. RELEVANCE CHECK: Reject (**score <= 6**) if the solutions do not directly mitigate the specific circumstances and root causes of the accident described in the report.
4. TERMINOLOGY CHECK: Ensure solutions use formal traffic engineering terminology.
5. STRUCTURE & PLACEHOLDER CHECK: Output **MUST** be a plain **JSON ARRAY** of strings. Reject (**score <= 4**) if it is a JSON object/dictionary, or if it contains lazy placeholders exactly like "มาตรการที่ 1" or "มาตรการที่ 2".

## OUTPUT FORMAT
Score from 0 to 10. Provide deep actionable reasoning IN THAI LANGUAGE pointing out specific flaws.
Output *strictly* as JSON:
{{"score": 8, "reasoning": "เหตุผล...", "is_accepted": true}}
