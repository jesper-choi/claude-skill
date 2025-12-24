---
name: vibe-coding-bug-fix
description: Bug fix skill optimized for vibe coding. Supports systematic problem analysis, root cause identification, and safe fixes. Keywords: bug, fix, debug, issue, error, problem, defect, hotfix, patch, python, typescript, fastapi, react.
---

# Vibe Coding: Bug Fix

## 🎯 Purpose

Fix bugs **systematically and safely**:
- **Fix the Cause, Not the Symptom**: Identify and address the root cause
- **Reproduce First**: Reproduce the bug first and capture it with a test
- **Prevent Regression**: Prevent the same bug from recurring after the fix
- **Minimal Change**: Modify only the minimum necessary code

---

## 🧠 Core Principles: Vibe Coding for Bug Fixes

### 1. Verify, Don't Assume
```
⛔ NEVER DO:
- Guess the cause based only on logs/error messages
- Attempt to fix without reading the code
- Approach with "this is probably the cause"

✅ ALWAYS DO:
- Try to reproduce the bug first
- Read all related code
- Confirm actual behavior through debugging
- Fix only after identifying the root cause
```

### 2. Capture with Test
```
Bug Fix Order:
1. Reproduce the bug
2. Write a test that reproduces the bug (FAIL)
3. Analyze root cause
4. Fix (test PASS)
5. Verify all existing tests pass
```

### 3. Minimal Change Principle
```
Minimize fix scope:

✅ Good Fix:
- Fix only the bug cause precisely
- No unrelated code changes
- Refactoring in separate PR

❌ Bad Fix:
- "While I'm at it" fix other things
- Unnecessary code cleanup
- Improvements beyond scope
```

---

## 🔍 Bug Fix Workflow

### Step 1: Reproduce the Bug (Required)
```markdown
Reproduction Checklist:
- [ ] Bug reproduction successful
- [ ] Reproduction conditions documented
- [ ] Reproduction steps clearly recorded
```

### Step 2: Gather Information
```markdown
Information to Collect:
- [ ] Error messages/logs
- [ ] Stack traces
- [ ] Input data
- [ ] Environment information
- [ ] Reproduction frequency
```

### Step 3: Root Cause Analysis
```markdown
Analysis Checklist:
- [ ] Read all related code
- [ ] Trace execution flow
- [ ] Debug suspicious points
- [ ] Confirm root cause
```

### Step 4: Capture Bug with Test
```markdown
Test Writing:
- [ ] Write test that reproduces the bug
- [ ] Run test → Confirm FAIL
- [ ] Verify this test accurately captures the bug
```

### Step 5: Fix and Verify
```markdown
Fix Checklist:
- [ ] Modify only minimal code
- [ ] Bug test PASS
- [ ] All existing tests PASS
- [ ] Manual verification complete
```

---

## 🔬 Root Cause Analysis (RCA) Guide

### 5 Whys Technique
```
Bug: User cannot log in

Why 1: Why can't they log in?
→ Authentication token expired

Why 2: Why did the token expire?
→ Token refresh logic didn't execute

Why 3: Why didn't refresh logic execute?
→ Refresh timing calculation was wrong

Why 4: Why was timing calculation wrong?
→ UTC/local time conversion bug

Why 5: Why is there a time conversion bug?
→ Timezone handling missing ← ROOT CAUSE
```

### Debugging Strategies

**Python**:
```python
# Breakpoint
import pdb; pdb.set_trace()

# Or breakpoint() (Python 3.7+)
breakpoint()

# Logging for tracing
import logging
logging.debug(f"value: {value}, type: {type(value)}")
```

**TypeScript/JavaScript**:
```typescript
// Breakpoint
debugger;

// Console logging
console.log('checkpoint', { value, state });

// Conditional logging
if (DEBUG) console.trace('stack trace here');
```

---

## 📏 Bug Fix Checklist

### Before Fix
- [ ] Bug reproduction successful
- [ ] Read all related code
- [ ] Root cause identified
- [ ] Bug capture test written (FAIL)

### During Fix
- [ ] Modifying only minimal code
- [ ] Fix intent is clear
- [ ] No side effects

### After Fix
- [ ] Bug capture test PASS
- [ ] All existing tests 100% PASS
- [ ] Manual verification complete
- [ ] Similar bug possibility reviewed

---

## 🎯 Bug Type Guide

### 1. Logic Bugs
```python
# Problem: Boundary condition error
# ❌ Bug
if count > 10:  # 10 is not included
    process()

# ✅ Fix
if count >= 10:  # 10 included
    process()
```

**Analysis Points**:
- Boundary values
- Off-by-one errors
- Conditional logic

### 2. Null/None Related Bugs
```python
# Problem: Missing None check
# ❌ Bug
def get_name(user):
    return user.name  # Error if user is None

# ✅ Fix
def get_name(user):
    if user is None:
        return None
    return user.name
```

```typescript
// ❌ Bug
const name = user.name;  // user could be undefined

// ✅ Fix
const name = user?.name ?? 'Unknown';
```

### 3. Async Bugs
```python
# Problem: Missing await
# ❌ Bug
async def fetch_data():
    data = api.get_data()  # Missing await
    return process(data)

# ✅ Fix
async def fetch_data():
    data = await api.get_data()
    return process(data)
```

```typescript
// Problem: Race condition
// ❌ Bug
useEffect(() => {
  fetchData().then(setData);  // setState after unmount possible
}, []);

// ✅ Fix
useEffect(() => {
  let cancelled = false;
  fetchData().then(data => {
    if (!cancelled) setData(data);
  });
  return () => { cancelled = true; };
}, []);
```

### 4. Type Related Bugs
```python
# Problem: Type mismatch
# ❌ Bug
def calculate(value):
    return value + 10  # Error if value is str

# ✅ Fix
def calculate(value: int) -> int:
    return int(value) + 10
```

### 5. State Management Bugs
```typescript
// Problem: Direct state mutation
// ❌ Bug
const updateItem = (items, id, value) => {
  const item = items.find(i => i.id === id);
  item.value = value;  // Direct mutation
  setItems(items);
};

// ✅ Fix
const updateItem = (items, id, value) => {
  setItems(items.map(item =>
    item.id === id ? { ...item, value } : item
  ));
};
```

---

## 📋 Bug Fix Plan Template

### Bug Size Guide

| Size | Time | Characteristics |
|------|------|-----------------|
| **Hotfix** | 1-2 hours | Clear cause, single file fix |
| **Standard** | 2-4 hours | Analysis needed, multiple files involved |
| **Complex** | 4-8 hours | Deep analysis required, system impact |

### Phase Structure (for Bug Fixes)

```markdown
### Phase 1: Reproduce & Analyze
- [ ] Reproduce bug
- [ ] Gather information
- [ ] Analyze code
- [ ] Identify root cause

### Phase 2: Test & Fix
- [ ] Write bug capture test (FAIL)
- [ ] Apply minimal fix
- [ ] Confirm test PASS
- [ ] Confirm existing tests PASS

### Phase 3: Verify & Complete
- [ ] Manual verification
- [ ] Similar bug review
- [ ] Documentation
```

---

## ✋ Quality Gate (for Bug Fixes)

### Required Verification Items

**Bug Resolution Confirmation**:
- [ ] **Bug Test PASS**: Bug capture test passes
- [ ] **Manual Confirmation**: Original symptom resolved
- [ ] **Cannot Reproduce**: Bug cannot be reproduced under same conditions

**Regression Prevention**:
- [ ] **All Existing Tests 100% PASS**: No regression
- [ ] **Related Feature Tests**: No side effects

**Fix Quality**:
- [ ] **Minimal Change**: Only necessary parts modified
- [ ] **Clear Fix**: Fix intent is clear
- [ ] **Lint/Format Pass**: Code style maintained

---

## 🛠️ Validation Commands

### Python/FastAPI (uv)
```bash
# Specific bug test
uv run pytest tests/test_bug_fix.py -v

# All tests
uv run pytest --cov=src

# Lint
uv run ruff check .

# Sync dependencies
uv sync
```

### TypeScript/React
```bash
# Specific bug test
npm test -- --testPathPattern="bug-fix"

# All tests
npm test

# Lint
npm run lint
```

---

## ⚠️ Cautions

### Anti-patterns to Avoid

| Anti-pattern | Risk | Alternative |
|--------------|------|-------------|
| Fix by guessing | Causes other bugs | Reproduce & analyze first |
| Fix without tests | Regression risk | Capture with test |
| Excessive fix | Causes new bugs | Minimal change |
| Fix symptom only | Bug recurrence | Fix root cause |

### Ask Yourself Before Fixing

- "Is this really the root cause?"
- "Does this fix affect other areas?"
- "Is there a simpler fix?"
- "Could this bug exist elsewhere?"

---

## 🧠 Codebase Context Awareness

### CRITICAL: Before ANY Implementation

```
⚠️ STOP AND CHECK:

1. □ Have I searched for SIMILAR implementations in this codebase?
2. □ Am I using the SAME patterns as existing code?
3. □ Have I checked HOW this is done elsewhere in the project?
4. □ Am I being CONSISTENT with established conventions?
```

### Common Context Mistakes

| Mistake | Example | Prevention |
|---------|---------|------------|
| **Ignoring existing patterns** | Using `axios` when project uses `fetch` | Search: `grep -r "fetch\|axios" src/` |
| **Inconsistent naming** | `getUserData` when others use `fetchUser` | Check similar functions first |
| **Different error handling** | Throwing when others return `Result` type | Look at adjacent functions |
| **Wrong import paths** | `../utils` when project uses `@/utils` | Copy from existing imports |

### Before Writing Code, Find Answers

```markdown
## Codebase Questions (Answer BEFORE coding)

1. **Similar Feature Exists?**
   → Search: "How is [similar feature] implemented?"
   → File: [path to reference implementation]

2. **Naming Convention?**
   → Variables: camelCase / snake_case?
   → Functions: get/fetch/retrieve?
   → Files: kebab-case / PascalCase?

3. **Error Handling Pattern?**
   → Exceptions / Result type / Error codes?
   → Where is error handling done?

4. **Import Style?**
   → Absolute (@/) or relative (../) paths?
   → Named or default exports?
```

### Remembering Previous Context

```
⚠️ IN LONG SESSIONS, ALWAYS:

1. Re-read what was implemented earlier in this session
2. Check if current change conflicts with previous changes
3. Verify consistency with code written 5+ messages ago
4. Don't repeat a mistake that was already corrected
```

### Consistency Checklist

```markdown
Before completing ANY task:
- [ ] My code follows the SAME pattern as similar existing code
- [ ] My naming matches the project's naming conventions
- [ ] My error handling matches how errors are handled elsewhere
- [ ] My imports use the same style as other files
- [ ] I haven't contradicted anything I implemented earlier
```

---

## 📚 Supporting Files
- [plan-template.md](plan-template.md) - Bug Fix Plan Template
