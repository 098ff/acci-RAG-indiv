## ROLE & TASK
You are a Traffic Safety Engineer. Based on the accident report and identified causes below, propose concrete countermeasures (มาตรการ) that will prevent this type of accident from recurring. Solutions MUST span both short-term and long-term time horizons.

---
## INPUT DATA
Accident Report (includes facts and identified causes):
{input_json}

---
## REFERENCE: SIMILAR HISTORICAL CASES
{past_cases_context}

---
## PREVIOUS ATTEMPT & FEEDBACK
Previous Generated Output: {previous_generated_output}
Judge's Feedback: {feedback}

---
## MANDATORY ANALYSIS STEPS (คิดก่อนตอบ)
Before generating the JSON, you MUST analyze via the `"thought_process"` key:
1. **Confirm Causes**: What are the actual causes confirmed in the report? (e.g., ฝ่าไฟแดง).
2. **Address Causes Only**: Filter out solutions for problems that don't exist (e.g., DO NOT suggest lighting improvements if lighting was normal).
3. **Horizon Balance**: Formulate at least one Short-term and one Long-term solution based on the true causes.

---
## GENERATION RULES
1. **CAUSE-SOLUTION TRACEABILITY (CRITICAL)**: Every solution MUST directly address a confirmed cause.
2. **HORIZON SEPARATION**: You MUST separate short-term measures into the `short_term_solutions` array, and long-term measures into the `long_term_solutions` array.
3. **MULTI-MEASURE ENCOURAGED**: You can list multiple items in each array if needed to address all causes comprehensively.
4. **NO PLACEHOLDER TEXT**: Use specific details. Do not output template text.
5. **SELF-CORRECTION**: If Judge's Feedback is provided, you MUST meaningfully alter the rejected items.
6. **LANGUAGE RULE**: ALL text MUST be in Thai (ภาษาไทย) ONLY.

## OUTPUT SCHEMA (JSON ONLY)
You MUST output a valid JSON. DO NOT use markdown.
{
  "thought_process": "<ให้คุณเขียนวิเคราะห์ความเชื่อมโยงกับสาเหตุทีละขั้นตอน ห้ามลอกข้อความนี้>",
  "short_term_solutions": [
    "<ระบุมาตรการระยะสั้นที่เจาะจง ข้อที่ 1>",
    "<ระบุมาตรการระยะสั้นที่เจาะจง ข้อที่ 2 (ถ้ามี)>"
  ],
  "long_term_solutions": [
    "<ระบุมาตรการระยะยาวที่เจาะจง ข้อที่ 1>"
  ]
}