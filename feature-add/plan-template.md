# Feature Implementation Plan: [Feature Name]

**Status**: 🔄 In Progress
**Started**: YYYY-MM-DD
**Last Updated**: YYYY-MM-DD
**Estimated Completion**: YYYY-MM-DD
**Feature Type**: 🆕 New Feature | 🔧 Enhancement | 🔄 Refactor

---

## ⚠️ CRITICAL: Feature Addition Principles

> **🧠 Core**: Respect existing code. Follow patterns. Integrate incrementally.

### Mandatory Requirements
1. 📖 **Analyze Code First**: Read similar feature code first
2. 🔄 **Reuse Patterns**: Leverage existing patterns and utilities
3. 🧪 **Strict TDD**: Tests first, implementation later
4. ✅ **Prevent Regression**: Maintain 100% existing test pass rate
5. 🎯 **Incremental Integration**: Break into small units for safety

### After Each Phase Completion
1. ✅ Verify all existing tests pass
2. ✅ Verify all new tests pass
3. 🧪 Run Quality Gate verification
4. 📝 Record learnings in Notes
5. ➡️ Proceed to next phase only after verification complete

⛔ **DO NOT proceed if existing tests fail**

---

## 📋 Overview

### Feature Description
[Description of feature to add]

### Why This Feature?
[Why this feature is needed]

### Success Criteria
- [ ] Criterion 1
- [ ] Criterion 2
- [ ] Criterion 3

### User Impact
[What benefits users will receive]

---

## 🔍 Codebase Analysis (Required Before Starting)

### Similar Feature Analysis
| Existing Feature | File Path | Patterns to Reference |
|------------------|-----------|----------------------|
| [Existing feature 1] | `path/to/file` | [What to reference from this feature] |
| [Existing feature 2] | `path/to/file` | [What to reference from this feature] |

### Reusable Code
| Code | File Path | Purpose |
|------|-----------|---------|
| [Utility/Helper] | `path/to/file` | [How to use] |
| [Existing component] | `path/to/file` | [How to use] |

### Existing Architecture Patterns
- **Layer Structure**: [Currently used layers]
- **Dependency Injection**: [DI pattern]
- **Error Handling**: [Error handling pattern]
- **Test Structure**: [Test organization method]

### Impact Scope Analysis
- **Files to Modify**: [Files requiring direct modification]
- **Affected Files**: [Indirectly affected files]
- **Test Impact**: [Tests requiring modification/addition]

---

## 🏗️ Architecture Decisions

### Clean Architecture Application
```
Layer structure for this feature:

Presentation: [API/UI components]
     ↓
Application: [Use Cases/Services]
     ↓
Domain: [Entities/Interfaces]
     ↓
Infrastructure: [Repository implementations/External integrations]
```

### SOLID Application Plan
- [ ] **S**: Assign single responsibility to each class/function
- [ ] **O**: Implement through extension instead of modifying existing code
- [ ] **L**: Comply with existing interface contracts
- [ ] **I**: Define only necessary interfaces
- [ ] **D**: Depend on abstractions, use dependency injection

### Key Design Decisions

| Decision | Rationale | Relationship to Existing Patterns |
|----------|-----------|-----------------------------------|
| [Decision 1] | [Reason] | [Following/Extending existing pattern] |
| [Decision 2] | [Reason] | [Following/Extending existing pattern] |

---

## 📦 Dependencies

### Existing Code Dependencies
- [ ] `module/path`: [Usage purpose]
- [ ] `module/path`: [Usage purpose]

### New External Dependencies (Minimize)
- Package 1: version X.Y.Z - [Why needed]

---

## 🧪 Test Strategy

### TDD Principle
**Write tests first, then implement to make tests pass.**

### Following Existing Test Patterns
```
Existing test structure:
tests/
├── unit/
│   └── [Follow existing pattern]
├── integration/
│   └── [Follow existing pattern]
└── e2e/
    └── [Follow existing pattern]
```

### Test Plan for This Feature
| Test Type | Target | Coverage Target |
|-----------|--------|-----------------|
| Unit | [Business logic] | ≥80% |
| Integration | [Component integration] | Critical paths |
| E2E | [User flow] | Main flow |

---

## 🚀 Implementation Phases

### Phase 1: [Foundation - Base Structure]
**Goal**: [Working feature completed in this phase]
**Estimated Time**: X hours
**Status**: ⏳ Pending | 🔄 In Progress | ✅ Complete

#### 📖 Code Analysis (Required Before Implementation)
- [ ] Similar feature code reading complete
- [ ] Reusable code identified
- [ ] Existing patterns understood

Referenced existing code:
- `path/to/similar/feature`: [Referenced pattern]
- `path/to/utility`: [Code to reuse]

#### 🔴 RED: Write Failing Tests
- [ ] **Test 1.1**: [Feature] unit test
  - File: `tests/unit/[feature]/test_[component].py`
  - Reference existing test pattern: `tests/unit/[similar]/test_*.py`
  - Test cases:
    - Happy path
    - Edge cases
    - Error conditions

- [ ] **Test 1.2**: [Integration] test
  - File: `tests/integration/test_[feature].py`

#### 🟢 GREEN: Implement to Pass Tests
- [ ] **Task 1.3**: [Component] implementation
  - File: `src/[layer]/[component].py`
  - Following existing pattern: `src/[layer]/[similar].py`
  - Reusing: [existing utilities/helpers]

- [ ] **Task 1.4**: [Connection code] implementation
  - File: `src/[layer]/[integration].py`

#### 🔵 REFACTOR: Quality Improvement
- [ ] **Task 1.5**: Refactoring
  - [ ] Remove duplicate code
  - [ ] Verify consistency with existing code
  - [ ] Improve naming

#### ✋ Quality Gate

**⚠️ STOP: DO NOT proceed to Phase 2 until all items pass**

**Existing Code Impact**:
- [ ] **Existing Tests 100% Pass**: No regression
- [ ] **Existing Features Work**: Manual test confirmed

**TDD Compliance**:
- [ ] **RED**: Tests written first, failure confirmed
- [ ] **GREEN**: Minimal implementation to pass tests
- [ ] **REFACTOR**: Quality improved while maintaining tests

**Consistency**:
- [ ] **Pattern Compliance**: Following existing architecture patterns
- [ ] **Naming**: Following existing conventions
- [ ] **Style**: Lint/format pass

**Validation Commands**:
```bash
# Python/FastAPI (uv)
uv run pytest  # All tests (existing + new)
uv run pytest --cov=src --cov-report=term-missing
uv run ruff check . && uv run ruff format --check .
uv run mypy src/
uv sync  # Sync dependencies

# TypeScript/React
npm test  # All tests
npm run lint && npm run format:check
npx tsc --noEmit
npm run build
```

---

### Phase 2: [Core Logic]
**Goal**: [Specific deliverable]
**Estimated Time**: X hours
**Status**: ⏳ Pending | 🔄 In Progress | ✅ Complete

#### 📖 Code Analysis
- [ ] Review Phase 1 results
- [ ] Analyze additional reference code

#### 🔴 RED / 🟢 GREEN / 🔵 REFACTOR
[Same structure as Phase 1]

#### ✋ Quality Gate
[Same checklist as Phase 1]

---

### Phase 3: [Integration]
**Goal**: [Specific deliverable]
**Estimated Time**: X hours
**Status**: ⏳ Pending | 🔄 In Progress | ✅ Complete

#### 📖 Code Analysis
- [ ] Analyze full integration impact
- [ ] Verify E2E scenarios

#### 🔴 RED / 🟢 GREEN / 🔵 REFACTOR
[Same as previous Phases]

#### ✋ Quality Gate
[Same as Phase 1 + integration tests added]

---

## ⚠️ Risk Assessment

| Risk | Probability | Impact | Mitigation |
|------|-------------|--------|------------|
| Existing feature regression | Medium | High | Maintain 100% existing tests, manual testing |
| Pattern mismatch | Low | Medium | Thorough existing code analysis |
| Performance impact | Low | Medium | Benchmark testing |
| Complexity increase | Medium | Medium | Simplicity principle, refactoring |

---

## 🔄 Rollback Strategy

### If Phase 1 Fails
- [ ] Delete new files
- [ ] Revert existing file changes
- [ ] Remove dependencies

### If Phase 2/3 Fails
- [ ] Restore to previous Phase state
- [ ] Revert related changes

---

## 📊 Progress Tracking

### Completion Status
- **Phase 1**: ⏳ 0% | 🔄 50% | ✅ 100%
- **Phase 2**: ⏳ 0% | 🔄 50% | ✅ 100%
- **Phase 3**: ⏳ 0% | 🔄 50% | ✅ 100%

### Time Tracking
| Phase | Estimated | Actual | Variance |
|-------|-----------|--------|----------|
| Phase 1 | X hours | - | - |
| Phase 2 | X hours | - | - |
| Phase 3 | X hours | - | - |

---

## 📝 Notes & Learnings

### Lessons from Existing Code
- [What learned from existing patterns]
- [Code reused]

### Implementation Notes
- [Insights discovered during implementation]
- [Changed decisions]

### Blockers
- **Blocker 1**: [Description] → [Resolution]

---

## ✅ Final Checklist

**Final Verification Before Completion**:
- [ ] All existing tests pass
- [ ] All new tests pass
- [ ] Manual testing of existing features complete
- [ ] Manual testing of new features complete
- [ ] No performance impact confirmed
- [ ] Consistency with existing patterns verified
- [ ] Documentation updated

---

**Plan Status**: 🔄 In Progress
**Next Action**: [Next task]
**Blocked By**: [Current blocker] or None
