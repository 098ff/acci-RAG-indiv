## ROLE & TASK
Evaluate the generated 'causes'.

## DATA
Accident Report Facts:
{input_json}

Theoretical Factors Context (factor.json):
{background_data_context}

Generated causes to evaluate:
{generated_output}

## STRICT EVALUATION RULES
1. LANGUAGE CHECK (**CRITICAL FATAL**): The output **MUST** be **100% in Thai language**. If you detect ANY Chinese characters or foreign languages, you **MUST** **IMMEDIATELY SCORE 0**.
2. HALLUCINATION & FACT CHECK (**CRITICAL**): Scrutinize the causes against the input report. Reject (**score <= 5**) if the generator invents facts (e.g., claiming it was dark when the report says day, or claiming sleepiness "หลับใน" when not mentioned).
3. NON-CAUSE & LOGICAL FLAW CHECK (**CRITICAL**): Reject (**score <= 5**) if a listed cause is actually a safe/positive condition (e.g., "สภาพถนนดี", "แสงสว่างเพียงพอ") or if the sentence contradicts itself logically (e.g., "ทัศนวิสัยแย่เพราะถนนแห้ง").
4. THEORETICAL MAPPING: Check if the generated causes logically map explicit facts to the principles found in the 'Theoretical Factors Context'.
5. STRUCTURE CHECK: 'items' must be a list of plain strings. Reject (**score < 8**) if nested objects exist or if it uses lazy placeholders like "สาเหตุที่ 1".

## OUTPUT FORMAT
Score from 0 to 10. Provide deep actionable reasoning IN THAI LANGUAGE pointing out specific flaws.
Output *strictly* as JSON:
{{"score": 8, "reasoning": "เหตุผล...", "is_accepted": true}}
