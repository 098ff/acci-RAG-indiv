**ROLE & TASK**
Evaluate the generated 'causes'.

**DATA**
Accident Report Facts:
{input_json}

Generated causes to evaluate:
{generated_output}

**STRICT EVALUATION RULES**
1. LANGUAGE CHECK (CRITICAL FATAL): The output MUST be 100% in Thai language. If you detect ANY Chinese characters (e.g., 车辆) or foreign languages, you MUST IMMEDIATELY SCORE 0 and state: "REJECTED: Contains foreign language. Use Thai ONLY."
2. ANTI-HALLUCINATION: Check if causes logically match explicit facts. Reject (score < 8) if there are ANY guesses not explicitly supported by the input.
3. STRUCTURE CHECK: 'items' must be a list of plain strings. Reject (score < 8) if nested objects exist.

**OUTPUT FORMAT**
Score from 0 to 10. Provide brief actionable reasoning IN THAI LANGUAGE.
Output strictly as JSON:
{{"score": 8, "reasoning": "เหตุผล...", "is_accepted": true}}