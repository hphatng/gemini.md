# Examples: Expert AI Coding (Karpathy Style)

Real-world code examples demonstrating the four principles. Use these as a reference for how to handle complex tasks with simplicity and precision.

---

## 1. Think Before Coding (Surface Assumptions)

**User Request:** "Add a feature to export user data"

**❌ WRONG (Silent Assumptions)**
The AI immediately writes a function that exports ALL users to a local JSON file, assuming pagination, privacy, and file format without asking.

**✅ RIGHT (Clarify First)**
"Before implementing, I need to clarify:
1. **Scope**: Export all users or a filtered subset?
2. **Format**: API response, or a downloadable file (CSV/JSON)?
3. **Sensitive Data**: Should we exclude passwords/hashes?
Simplest approach: A paginated JSON API endpoint. Does that work for you?"

---

## 2. Simplicity First (No Speculative Code)

**User Request:** "Add a function to calculate discount"

**❌ WRONG (Over-engineering)**
Creating an `ABC DiscountStrategy` with `PercentageDiscount` and `FixedDiscount` classes and a `DiscountCalculator` factory for a simple one-time task.

**✅ RIGHT (Simple)**
```python
def calculate_discount(amount: float, percent: float) -> float:
    return amount * (percent / 100)
```
*Refactor only when multiple discount types are actually required.*

---

## 3. Surgical Changes (Minimize Diff Noise)

**User Request:** "Fix the bug where empty emails crash the validator"

**❌ WRONG (Drive-by Refactoring)**
Changing the email regex, adding type hints to the whole file, updating docstrings, and reformating whitespace while fixing the bug.

**✅ RIGHT (Surgical)**
```diff
  def validate_user(user_data):
-     if not user_data.get('email'):
+     email = user_data.get('email', '')
+     if not email or not email.strip():
          raise ValueError("Email required")
```
*Only the bug fix is changed. Existing style is preserved.*

---

## 4. Goal-Driven Execution (Verifiable Steps)

**User Request:** "The sorting breaks when there are duplicate scores"

**❌ WRONG (Fixing blindly)**
Immediately changing the sort logic without a test case to confirm the failure.

**✅ RIGHT (Reproduce First)**
1. **Write Reproduction Test**: Create a list with duplicate scores and assert a deterministic order.
2. **Verify Failure**: Run the test to confirm it fails/flaps.
3. **Implement Fix**: Use a stable sort or tie-breaker key.
4. **Verify Success**: Run the test 10 times to ensure it passes consistently.
