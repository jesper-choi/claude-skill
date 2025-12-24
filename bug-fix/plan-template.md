# Bug Fix Plan: [Bug Title]

**Status**: 🔄 In Progress
**Reported**: YYYY-MM-DD
**Started**: YYYY-MM-DD
**Fixed**: YYYY-MM-DD
**Severity**: 🔴 Critical | 🟠 High | 🟡 Medium | 🟢 Low

---

## ⚠️ CRITICAL: Bug Fix Principles

> **🧠 Core**: Verify, don't assume. Fix the cause, not the symptom.

### Mandatory Requirements
1. 🔍 **Reproduce First**: Reproduce the bug first
2. 🧪 **Capture with Test**: Capture the bug with a test
3. 🎯 **Root Cause**: Fix the cause, not the symptom
4. ✂️ **Minimal Change**: Modify only the minimum necessary
5. ✅ **Prevent Regression**: Maintain 100% existing tests

### Fix Procedure
1. Reproduce Bug → 2. Gather Info → 3. Root Cause Analysis → 4. Write Test → 5. Fix → 6. Verify

⛔ **NO fixing attempts without reproduction**
⛔ **NO completing fix without tests**

---

## 🐛 Bug Description

### Symptom (What)
[Problem phenomenon experienced by user]

### Reproduction Steps (How to Reproduce)
1. [Step 1]
2. [Step 2]
3. [Step 3]
4. Result: [Actual result]

### Expected Behavior
[How it should work correctly]

### Actual Behavior
[Current incorrect behavior]

### Impact Scope
- **Affected Users**: [Scope]
- **Affected Features**: [Feature list]
- **Frequency**: [Always/Sometimes/Specific conditions]

---

## 📊 Collected Information

### Error Information
```
[Error message]
```

### Stack Trace
```
[Stack trace]
```

### Related Logs
```
[Related logs]
```

### Environment Information
| Item | Value |
|------|-------|
| Environment | Dev/Staging/Production |
| Browser/Client | [Info] |
| OS | [Info] |
| Version | [Info] |

### Input Data
```
[Input data that triggered the bug]
```

---

## 🔍 Code Analysis

### Analyzed Files
| File Path | Analysis Content | Relevance |
|-----------|------------------|-----------|
| `path/to/file1` | [Analysis content] | 🔴 Directly related |
| `path/to/file2` | [Analysis content] | 🟡 Indirectly related |

### Execution Flow Trace
```
1. [Starting point]
   ↓
2. [Intermediate step]
   ↓
3. [Problem point] ← Bug occurs here
   ↓
4. [Symptom manifestation]
```

### Suspicious Points
| Location | Reason for Suspicion | Verification Result |
|----------|---------------------|---------------------|
| `file:line` | [Why suspicious] | ✅ Cause / ❌ Not cause |

---

## 🎯 Root Cause Analysis (RCA)

### 5 Whys Analysis
```
Bug Symptom: [Symptom]

Why 1: Why does [symptom] occur?
→ [Answer 1]

Why 2: Why [Answer 1]?
→ [Answer 2]

Why 3: Why [Answer 2]?
→ [Answer 3]

Why 4: Why [Answer 3]?
→ [Answer 4]

Why 5: Why [Answer 4]?
→ [Root Cause] ← ROOT CAUSE
```

### Root Cause (Confirmed)
```
[Clear explanation of root cause]

Problem Code:
[Problematic code snippet]

Why It's a Problem:
[Reason why it's problematic]
```

### Fix Direction
```
[How to fix]

Fixed Code:
[Fixed code snippet]

Why This Is the Solution:
[Why this fix solves the problem]
```

---

## 🧪 Test Strategy

### Bug Capture Test
```python
# tests/test_bug_[issue_number].py

def test_bug_[description]():
    """
    Bug: [Bug description]
    Root Cause: [Root cause]
    """
    # Arrange: Set up bug reproduction conditions
    [setup code]
    
    # Act: Trigger bug-inducing action
    [action code]
    
    # Assert: Verify correct behavior
    [assertion code]
```

### Test Plan
- [ ] **Bug Capture Test**: Test that exactly reproduces this bug
- [ ] **Boundary Condition Test**: Similar boundary condition tests
- [ ] **Regression Test**: All existing tests pass

---

## 🚀 Fix Implementation

### Phase 1: Reproduce & Analyze
**Goal**: Reproduce bug and identify root cause
**Status**: ⏳ Pending | 🔄 In Progress | ✅ Complete

#### Tasks
- [ ] **Task 1.1**: Reproduce bug
  - Reproduction success: ⏳
  - Reproduction conditions: [Conditions]

- [ ] **Task 1.2**: Gather information
  - Error message: ⏳
  - Stack trace: ⏳
  - Related logs: ⏳

- [ ] **Task 1.3**: Code analysis
  - Analyzed files: [File list]
  - Execution flow trace: ⏳

- [ ] **Task 1.4**: Confirm root cause
  - Root cause: [Cause]
  - Confidence: High/Medium/Low

#### ✋ Phase 1 Gate
- [ ] Bug reproduction successful
- [ ] Root cause confirmed
- [ ] Fix direction decided

---

### Phase 2: Test & Fix
**Goal**: Capture bug with test then fix
**Status**: ⏳ Pending | 🔄 In Progress | ✅ Complete

#### Tasks
- [ ] **Task 2.1**: Write bug capture test
  - File: `tests/[path]/test_bug_[name].py`
  - Expected: Test FAIL (reproduces bug)

- [ ] **Task 2.2**: Run test → Confirm FAIL
  ```bash
  [Test execution command]
  ```
  - Result: ⏳ FAIL confirmed

- [ ] **Task 2.3**: Apply minimal fix
  - File: `[File to modify]`
  - Change content: [Change description]
  - Lines changed: [Minimize]

- [ ] **Task 2.4**: Run test → Confirm PASS
  ```bash
  [Test execution command]
  ```
  - Result: ⏳ PASS confirmed

#### ✋ Phase 2 Gate
- [ ] Bug capture test PASS
- [ ] All existing tests 100% PASS
- [ ] Verified fix is minimal

---

### Phase 3: Verify & Complete
**Goal**: Manual verification and similar bug review
**Status**: ⏳ Pending | 🔄 In Progress | ✅ Complete

#### Tasks
- [ ] **Task 3.1**: Manual verification
  - Test with original reproduction steps: ⏳
  - Bug resolution confirmed: ⏳

- [ ] **Task 3.2**: Related feature test
  - Affected feature test: ⏳
  - No side effects confirmed: ⏳

- [ ] **Task 3.3**: Similar bug review
  - Same pattern exists elsewhere? [Yes/No]
  - Additional fix needed: [Yes/No]

- [ ] **Task 3.4**: Documentation
  - Bug cause recorded: ⏳
  - Prevention measures recorded: ⏳

#### ✋ Phase 3 Gate
- [ ] Manual verification complete
- [ ] Similar bug review complete
- [ ] Documentation complete

---

## ✋ Final Quality Gate

### Bug Resolution Confirmation
- [ ] **Bug Test PASS**: Bug capture test passes
- [ ] **Manual Confirmation**: Original symptom resolved
- [ ] **Cannot Reproduce**: Bug cannot be reproduced under same conditions

### Regression Prevention
- [ ] **All Existing Tests 100% PASS**
- [ ] **Related Features Work Normally**
- [ ] **No Performance Impact**

### Code Quality
- [ ] **Minimal Change**: Only necessary parts modified
- [ ] **Lint Pass**: Code style maintained
- [ ] **Clear Fix**: Fix intent is clear

### Validation Commands
```bash
# Python/FastAPI (uv)
uv run pytest tests/test_bug_*.py -v  # Bug tests
uv run pytest  # All tests
uv run ruff check .
uv sync  # Sync dependencies

# TypeScript/React
npm test -- --testPathPattern="bug"  # Bug tests
npm test  # All tests
npm run lint
```

---

## 📝 Notes & Learnings

### Bug Cause Summary
```
[One-line summary of root cause]
```

### Prevention Measures
- [How to prevent this type of bug]
- [Tests/validations to add]
- [Things to check during code review]

### Similar Bug Possibilities
- [Other locations with same pattern]
- [Areas needing additional review]

### Lessons Learned
- [What was learned from this bug]

---

## 🔄 Rollback Strategy

### If Fix Causes Issues
- [ ] Revert fix commit
- [ ] Restore previous state
- [ ] Start analysis again

---

## 📊 Progress Tracking

| Phase | Status | Time Spent |
|-------|--------|------------|
| Phase 1: Reproduce & Analyze | ⏳ | - |
| Phase 2: Test & Fix | ⏳ | - |
| Phase 3: Verify & Complete | ⏳ | - |

**Total Time**: - hours

---

**Bug Status**: 🔄 In Progress
**Next Action**: [Next task]
**Blocked By**: [Current blocker] or None
