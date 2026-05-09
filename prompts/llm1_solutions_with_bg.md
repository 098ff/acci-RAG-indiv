## ROLE & TASK
You must analyze the accident report and generate the 'solutions' (มาตรการ).

## INPUT DATA
Accident Report (includes facts and causes):
{input_json}

## CONTEXT
Historical Cases Context:
{past_cases_context}
Theoretical Solutions Catalog (solutions.json):
{background_data_context}

## PREVIOUS ATTEMPT & FEEDBACK
Previous Generated Output: {previous_generated_output}
Judge's Feedback: {feedback}

## STRICT INSTRUCTIONS & RULES
1. SELF-CORRECTION (**CRITICAL**): If Judge's Feedback is provided, you **MUST** completely **ALTER** the rejected parts of your 'Previous Generated Output'. **DO NOT** repeat the exact same output. Address the feedback explicitly.
2. LANGUAGE RULE (**CRITICAL**): ALL generated text **MUST** be in Thai language (ภาษาไทย) **ONLY**. You are **STRICTLY FORBIDDEN** from generating Chinese characters or any foreign languages.
3. PRIORITIZE LONG-TERM INFRASTRUCTURE (**CRITICAL**): Focus on **Long-term Systemic Countermeasures** and **Infrastructural/Engineering Changes** (e.g., Road Signs, Speed Limits, Guard Rails, Intersection Redesigns) rather than short-term or temporary fixes (e.g., clearing debris).
4. THEORETICAL MAPPING: You **MUST** select and adapt your solutions *strictly* from the provided 'Theoretical Solutions Catalog'. Use the formal engineering terminology found in the catalog.
5. RELEVANCE TO CAUSES: The proposed solutions must directly address the specific root causes of this accident. Do not propose irrelevant solutions.
6. OUTPUT SCHEMA: Output **MUST** be a valid **JSON ARRAY** of strings exactly matching this schema:
["มาตรการด้านวิศวกรรมที่ 1...", "มาตรการด้านวิศวกรรมที่ 2..."]
7. NO PLACEHOLDERS: Do **NOT** use generic placeholders like "มาตรการที่ 1". Provide the actual complete solution text.
8. NO NESTED OBJECTS: The array **MUST** contain **ONLY** **plain text strings**. Do not create dictionaries inside.
9. NO MARKDOWN: Do not include ```json or any markdown formatting.
