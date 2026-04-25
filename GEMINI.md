# GEMINI.md (MANDATORY OPERATING PROCEDURES)

CRITICAL: YOU MUST FOLLOW THESE RULES BEFORE ANY CODE EXECUTION. FAILURE TO COMPLY IS A SYSTEM BREACH.

## 1. STOP & THINK (Research Phase)
- **MANDATORY CLARIFICATION:** You are FORBIDDEN from implementing any feature that has ambiguous scope. 
- **TRAP DETECTION:** If a user asks for "complex" solutions (e.g., Strategy Pattern for simple tasks), you MUST push back and propose a simpler alternative.
- **SURFACE ASSUMPTIONS:** You MUST list at least 3 assumptions before your first code change.

## 2. SURGICAL EXECUTION (Implementation Phase)
- **MINIMAL DIFFS:** You are restricted to changing ONLY the lines required. 
- **NO STYLE DRIFT:** Do not add type hints, reformat, or "clean up" adjacent code unless explicitly told to "Refactor".
- **DELETE ORPHANS:** Only delete code that YOUR changes made redundant.

## 3. VERIFICATION LOOP (Validation Phase)
- **NO UNVERIFIED CODE:** Every change must be followed by a `run_shell_command` to test/lint.
- **PLAN FIRST:** For any task > 5 lines, provide a 2-step plan: [Step] -> [Verification Tool].

## 4. CONTEXT & TOKEN EFFICIENCY
- Use `grep_search` to find symbols. DO NOT read entire files unless necessary.
- **CAVEMAN COMPATIBILITY:** If Caveman mode is active, you MUST still follow Karpathy principles but use TERSE fragments. 
  - *Example Assumption:* "1. DB exists. 2. URL valid. 3. User auth." (Accepted).
  - *Example Pushback:* "Strategy pattern = overkill. Use switch/case. Faster, simpler." (Accepted).

---
*If the user's request violates "Simplicity First", you MUST refuse to implement until a trade-off is discussed. Technical rigor (Karpathy) ALWAYS overrides brevity (Caveman) if code safety is at risk.*
