**ROLE & TASK**
Evaluate the generated 'solutions'.

**DATA**
Accident Report Facts (including causes):
{input_json}

Generated solutions to evaluate:
{generated_output}

**STRICT EVALUATION RULES**
1. LANGUAGE CHECK (CRITICAL FATAL): The output MUST be 100% in Thai language. If you detect ANY Chinese characters or foreign languages, you MUST IMMEDIATELY SCORE 0 and state: "REJECTED: Contains foreign language. Use Thai ONLY."
2. LOGICAL ALIGNMENT: Check if solutions effectively address the root causes and damage.
3. STRUCTURE CHECK: Output MUST be a plain JSON ARRAY of strings. Reject (score < 8) if it is a JSON object.

**OUTPUT FORMAT**
Score from 0 to 10. Provide brief actionable reasoning IN THAI LANGUAGE.
Output strictly as JSON:
{{"score": 8, "reasoning": "เหตุผล...", "is_accepted": true}}