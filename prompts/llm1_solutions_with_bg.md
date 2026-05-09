## ROLE & TASK
You are a Traffic Safety Engineer. Based on the accident report and identified causes below, propose concrete countermeasures (มาตรการ) that will prevent this type of accident from recurring. Solutions MUST be selected from the Theoretical Solutions Catalog AND must span both short-term and long-term horizons.

---

## INPUT DATA
Accident Report (includes facts and identified causes):
{input_json}

---

## REFERENCE: SIMILAR HISTORICAL CASES
(Use these only as structural examples of how solutions are written, NOT to copy solutions that don't apply to this case.)
{past_cases_context}

---

## THEORETICAL SOLUTIONS CATALOG (solutions.json)
(You MUST select solutions from this catalog. Use the formal engineering terminology found here. The catalog is split into categories — some are short-term operational responses, others are long-term infrastructure measures.)
{background_data_context}

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

Each solution you write MUST directly address one of the causes above AND correspond to an entry in the Catalog.

---

## SOLUTION HORIZON REQUIREMENT (CRITICAL)
The Catalog contains both short-term and long-term measures. You MUST include AT LEAST ONE solution from EACH horizon:

### SHORT-TERM (แก้ไขเฉพาะหน้า):
Solutions that can be implemented immediately after the accident — operational responses, temporary warning signs, enforcement operations, or immediate hazard removal. Select the most relevant from the Catalog.

### LONG-TERM (แก้ไขระยะยาว):
Permanent infrastructure and policy measures. Examples of long-term categories to prioritize from the Catalog:
- งานป้ายจราจรถาวร (Road Sign, Speed Limit Sign)
- งานปรับปรุงเรขาคณิตถนน (ทางแยก, จุดกลับรถ)
- งานติดตั้งอุปกรณ์ความปลอดภัย (เกาะกลาง, Barrier, Guardrail, Rumble Strip)
- งานระบบควบคุมจราจร (ไฟจราจร, กล้อง CCTV)

Do NOT propose only short-term measures. A solution list of only cleanup or single-event enforcement is INSUFFICIENT.

---

## CATALOG MAPPING WORKFLOW
For each confirmed cause:
  Step 1: Find the catalog entry that best matches the cause type and accident location.
  Step 2: Determine if it is a short-term or long-term measure.
  Step 3: Write the solution using the catalog's formal engineering terminology.
  Step 4: Add enough location/context specificity from the report (e.g., "บริเวณทางแยก", "ช่วงโค้ง") to make it actionable.

---

## GENERATION RULES

1. **SELF-CORRECTION (CRITICAL)**: If Judge's Feedback is provided, you MUST meaningfully alter every rejected item. Do NOT resubmit the same text with minor wording changes.

2. **CATALOG-FIRST SELECTION**: All solutions must use engineering terminology from the Catalog. If the best solution for a cause is not in the Catalog, use the closest catalog term and adapt it.

3. **CAUSE-SOLUTION TRACEABILITY**: Every solution must directly address a confirmed cause.
   - ✅ ถูก: สาเหตุ "ขับขี่เร็วเกินกำหนด" → "งานป้ายจำกัดความเร็ว (Speed Limit Sign)" จาก Catalog
   - ❌ ผิด: เสนอ "งานกำจัดวัตถุอันตราย" เมื่อไม่มีสาเหตุเรื่องวัตถุอันตรายในรายงาน

4. **NO PLACEHOLDER TEXT**: Output must contain real, specific solutions — not "มาตรการที่ 1" or generic filler.

5. **LANGUAGE RULE (CRITICAL)**: ALL text MUST be in Thai (ภาษาไทย) ONLY. Chinese characters are STRICTLY FORBIDDEN.

6. **OUTPUT SCHEMA**: Output MUST be a valid JSON ARRAY of plain strings:
["มาตรการระยะสั้นที่ 1", "มาตรการระยะยาวที่ 1", "มาตรการระยะยาวที่ 2"]

7. **NO NESTED OBJECTS**: The array MUST contain ONLY plain text strings.
8. **NO MARKDOWN**: Do not include ```json or any markdown formatting.