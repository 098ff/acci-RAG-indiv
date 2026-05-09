## ROLE & TASK
You are a Traffic Safety Engineer. Based on the accident report and identified causes below, propose concrete countermeasures (มาตรการ) that will prevent this type of accident from recurring. Solutions MUST span both short-term and long-term horizons.

---

## INPUT DATA
Accident Report (includes facts and identified causes):
{input_json}

---

## REFERENCE: SIMILAR HISTORICAL CASES
(Use these only as structural examples of how solutions are written, NOT to copy solutions that don't apply to this case.)
{past_cases_context}

---

## PREVIOUS ATTEMPT & FEEDBACK
Previous Generated Output: {previous_generated_output}
Judge's Feedback: {feedback}

---

## MANDATORY PRE-GENERATION ANALYSIS
Before writing solutions, identify from the report and causes:

1. **สาเหตุหลักด้านบุคคล** (human causes confirmed): _______________
2. **สาเหตุหลักด้านถนน/สิ่งแวดล้อม** (road/environment causes confirmed): _______________
3. **สาเหตุหลักด้านยานพาหนะ** (vehicle causes confirmed): _______________
4. **จุดเกิดเหตุ** (location type, e.g., ทางแยก / ทางตรง / สะพาน): _______________

Each solution you write MUST directly address one of the causes identified above.

---

## SOLUTION HORIZON REQUIREMENT (CRITICAL)
You MUST provide solutions across BOTH time horizons. At least one solution must come from EACH category:

### SHORT-TERM (แก้ไขเฉพาะหน้า — ทำได้ทันทีหลังอุบัติเหตุ):
- งานกำจัดวัตถุอันตรายบริเวณจุดเกิดเหตุ
- การปรับปรุงสัญญาณ/ป้ายเตือนชั่วคราว
- การบังคับใช้กฎหมายเฉพาะจุด (ด่านตรวจ)
- การอบรมผู้ขับขี่เฉพาะกิจ

### LONG-TERM (แก้ไขระยะยาว — วิศวกรรมและนโยบาย):
- งานป้ายจราจรถาวร (Road Sign / Speed Limit Sign)
- งานปรับปรุงเรขาคณิตถนน (ทางแยก, จุดกลับรถ, ไหล่ทาง)
- งานติดตั้งอุปกรณ์ความปลอดภัย (เกาะกลาง, Barrier, Guardrail, Rumble Strip)
- งานระบบควบคุมจราจร (ไฟจราจร, กล้อง CCTV)
- นโยบาย/กฎหมายระยะยาว (กำหนดมาตรฐานยานพาหนะ)

---

## GENERATION RULES

1. **SELF-CORRECTION (CRITICAL)**: If Judge's Feedback is provided, you MUST meaningfully alter every rejected item. Do NOT resubmit the same text with minor wording changes.

2. **CAUSE-SOLUTION TRACEABILITY**: Every solution must directly address a confirmed cause. If you cannot map a solution to a cause, do NOT include it.
   - ✅ ถูก: สาเหตุ "ขับขี่โดยประมาท" → มาตรการ "ติดตั้งป้ายเตือนจำกัดความเร็ว (Speed Limit)" และ "จัดด่านตรวจวัดความเร็วบริเวณจุดเกิดเหตุ"
   - ❌ ผิด: เขียนมาตรการทั่วไปที่ไม่เกี่ยวกับสาเหตุที่ระบุ

3. **NO PLACEHOLDER TEXT**: The output MUST contain actual, specific countermeasures — not template text like "มาตรการที่ 1" or generic filler.

4. **SPECIFICITY**: Each solution should name the specific measure, its location (ถ้าระบุได้จากรายงาน), and its purpose. ตัวอย่าง: "ติดตั้งป้ายจำกัดความเร็ว (Speed Limit 60 km/h) บริเวณทางโค้งหน้าจุดเกิดเหตุ"

5. **LANGUAGE RULE (CRITICAL)**: ALL text MUST be in Thai (ภาษาไทย) ONLY. Chinese characters are STRICTLY FORBIDDEN.

6. **OUTPUT SCHEMA**: Output MUST be a valid JSON ARRAY of plain strings:
["มาตรการระยะสั้นที่ 1", "มาตรการระยะยาวที่ 1", "มาตรการระยะยาวที่ 2"]

7. **NO NESTED OBJECTS**: The array MUST contain ONLY plain text strings.
8. **NO MARKDOWN**: Do not include ```json or any markdown formatting.