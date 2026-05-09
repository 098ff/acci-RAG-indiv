## ROLE & TASK
You must analyze the accident report and generate the root 'causes' (สาเหตุ).

## INPUT DATA
Accident Report:
{input_json}

## CONTEXT
Historical Cases Context:
{past_cases_context}
Theoretical Factors Context (factor.json):
{background_data_context}

## PREVIOUS ATTEMPT & FEEDBACK
Previous Generated Output: {previous_generated_output}
Judge's Feedback: {feedback}

## STRICT INSTRUCTIONS & RULES
1. SELF-CORRECTION (**CRITICAL**): If Judge's Feedback is provided, you **MUST** completely **ALTER** the rejected parts of your 'Previous Generated Output'. **DO NOT** repeat the exact same output. Address the feedback explicitly.
2. LANGUAGE RULE (**CRITICAL**): ALL generated text **MUST** be in Thai language (ภาษาไทย) **ONLY**. You are **STRICTLY FORBIDDEN** from generating Chinese characters (e.g., 车辆, 导致) or any foreign languages.
3. ANTI-HALLUCINATION & FACT-BASED (**CRITICAL**): Base your causes **ONLY** on explicit facts found in the report. **DO NOT** infer, guess, or invent details (e.g., do NOT assume "หลับใน" if it only says "ขับขี่โดยประมาท", do NOT say it was "มืด" if the report says it was daytime or well-lit).
4. LOGICAL CONSISTENCY (**CRITICAL**): Every cause must logically contribute to the accident. Do not list positive/safe states (e.g., "แสงสว่างเพียงพอ" or "ทัศนวิสัยดี") as a cause of the accident. Do not combine conflicting statements (e.g., "ทัศนวิสัยไม่ดีเนื่องจากสภาพผิวทางแห้ง").
5. THEORETICAL MAPPING: Use the 'Theoretical Factors Context' to map these facts into professional engineering terms.
6. CATEGORIZATION: Ensure correct mapping into "บุคคล", "ยานพาหนะ", and "ถนนและสิ่งแวดล้อม".
7. OUTPUT SCHEMA: Output **MUST** be valid JSON exactly matching this schema:
{{"main_cause_group": "พฤติกรรมผู้ขับขี่และสภาพแวดล้อม", "cause_list": [{{"group": "บุคคล", "items": ["สาเหตุที่ 1"]}}, {{"group": "ยานพาหนะ", "items": []}}, {{"group": "ถนนและสิ่งแวดล้อม", "items": ["สาเหตุที่ 1"]}}]}}
8. NO NESTED OBJECTS: The 'items' array **MUST** contain **ONLY** **plain text strings**.
9. NO MARKDOWN: Do not include ```json or any markdown formatting.
