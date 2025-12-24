# Implementation Plan: [Feature Name]

**Status**: 🔄 In Progress
**Started**: YYYY-MM-DD
**Last Updated**: YYYY-MM-DD
**Estimated Completion**: YYYY-MM-DD

---

## ⚠️ CRITICAL: Vibe Coding Principles

> **🧠 Core Philosophy**: Don't guess, read the code. Verify immediately after writing.

### Mandatory Requirements
1. ✅ **Codebase First**: Read all related code before starting
2. 🔍 **No Guessing**: Read actual code and judge, don't assume
3. ⚡ **Immediate Validation**: Run build/test/lint after every code change
4. 🎯 **Simplicity First**: Choose simple solutions over complex ones
5. 🏗️ **Clean Architecture**: Layer separation, SOLID principles

### After Each Phase Completion
1. ✅ Check completed task checkboxes
2. 🧪 Run all Quality Gate validation commands
3. ⚠️ Verify all Quality Gate items pass
4. 📅 Update "Last Updated" date
5. 📝 Record learnings in Notes section
6. ➡️ Proceed to next phase only after all verifications pass

⛔ **DO NOT proceed to next phase if Quality Gate fails**

---

## 📋 Overview

### Feature Description
[What this feature is and why it's needed]

### Success Criteria
- [ ] Criterion 1
- [ ] Criterion 2
- [ ] Criterion 3

### User Impact
[What benefits users will receive]

---

## 🧠 Codebase Analysis (Required Before Starting)

### Analyzed Files
| File Path | Analysis Purpose | Key Findings |
|-----------|------------------|--------------|
| `path/to/file1` | [Purpose] | [Findings] |
| `path/to/file2` | [Purpose] | [Findings] |

### Existing Architecture Patterns
- **Layer Structure**: [Currently used layer pattern]
- **Dependency Injection**: [DI method]
- **Error Handling**: [Error handling pattern]
- **Test Structure**: [Test organization method]

### Impact Scope Analysis
- **Direct Impact**: [Files/modules this feature directly modifies]
- **Indirect Impact**: [Files/modules affected by dependencies]
- **Test Impact**: [Tests requiring modification]

---

## 🏗️ Architecture Decisions

### Clean Architecture Compliance Check
- [ ] **Layer Separation**: Domain → Application → Infrastructure → Presentation
- [ ] **Dependency Direction**: Outer → Inner (Infrastructure → Domain)
- [ ] **Interface Separation**: Using abstractions like Repository

### SOLID Principles Check
- [ ] **S** (Single Responsibility): Each class/function has single responsibility
- [ ] **O** (Open/Closed): Open for extension, closed for modification
- [ ] **L** (Liskov Substitution): Subtypes can substitute base types
- [ ] **I** (Interface Segregation): Small interfaces
- [ ] **D** (Dependency Inversion): Depend on abstractions

### Key Decisions

| Decision | Rationale | Trade-offs |
|----------|-----------|------------|
| [Decision 1] | [Reason] | [Trade-offs] |
| [Decision 2] | [Reason] | [Trade-offs] |

---

## 📦 Dependencies

### Required Before Starting
- [ ] Dependency 1: [Description]
- [ ] Dependency 2: [Description]

### External Dependencies
- Package/Library 1: version X.Y.Z
- Package/Library 2: version X.Y.Z

---

## 🧪 Test Strategy

### TDD Principle
**Write tests first, then implement.**

### Test Pyramid
| Test Type | Coverage Target | Purpose |
|-----------|-----------------|---------|
| **Unit Tests** | ≥80% | Business logic, models, core algorithms |
| **Integration Tests** | Critical paths | Component interaction, data flow |
| **E2E Tests** | Key user flows | Full system behavior verification |

### Test File Organization
```
tests/
├── unit/
│   ├── domain/
│   ├── application/
│   └── infrastructure/
├── integration/
│   └── [feature_name]/
└── e2e/
    └── [user_flows]/
```

---

## 🚀 Implementation Phases

### Phase 1: [Foundation Phase Name]
**Goal**: [Working feature implemented in this phase]
**Estimated Time**: X hours
**Status**: ⏳ Pending | 🔄 In Progress | ✅ Complete

#### 📖 Code Analysis (Required Before Implementation)
- [ ] Related existing code reading complete
- [ ] Existing patterns/conventions understood
- [ ] Impact scope verified

Files read:
- `path/to/file1`: [What was confirmed]
- `path/to/file2`: [What was confirmed]

#### 🔴 RED: Write Failing Tests
- [ ] **Test 1.1**: Unit test for [specific functionality]
  - File: `tests/unit/[feature]/[component]_test.py`
  - Expected: Test fails (RED) - feature doesn't exist yet
  - Test cases:
    - Happy path
    - Edge cases
    - Error conditions

- [ ] **Test 1.2**: Integration test for [component interaction]
  - File: `tests/integration/[feature]_test.py`
  - Expected: Test fails (RED)

#### 🟢 GREEN: Minimal Implementation to Pass Tests
- [ ] **Task 1.3**: Implement [component/module]
  - File: `src/[layer]/[component].py`
  - Goal: Minimal code to pass Test 1.1
  - Quality check:
    - [ ] Is it simple? (Is there no simpler way?)
    - [ ] Is it clear? (Are names descriptive?)
    - [ ] Is there no duplication?

- [ ] **Task 1.4**: Implement [integration code]
  - File: `src/[layer]/[integration].py`
  - Goal: Pass Test 1.2

#### 🔵 REFACTOR: Quality Improvement (Maintain Tests)
- [ ] **Task 1.5**: Refactoring
  - [ ] Remove duplicate code (DRY)
  - [ ] Improve naming (clarity)
  - [ ] Remove unnecessary complexity
  - [ ] Use appropriate data structures
  - [ ] Inline documentation

#### ✋ Quality Gate

**⚠️ STOP: DO NOT proceed to Phase 2 until all items pass**

**TDD Compliance (Required)**:
- [ ] **RED Phase**: Tests written first and fail
- [ ] **GREEN Phase**: Code written to pass tests
- [ ] **REFACTOR Phase**: Quality improved while maintaining tests
- [ ] **Coverage**: Target coverage achieved

**Build & Test**:
- [ ] **Build**: Build/compile without errors
- [ ] **Tests Pass**: All tests pass (no skips)
- [ ] **Test Performance**: Completes in reasonable time

**Code Quality**:
- [ ] **Linting**: No errors/warnings
- [ ] **Formatting**: Project standard compliance
- [ ] **Type Check**: (If applicable) Pass

**Vibe Coding Check**:
- [ ] **Simplicity**: No simpler solution exists
- [ ] **Clarity**: Code is self-explanatory
- [ ] **No Duplication**: DRY principle compliance
- [ ] **Appropriate Data Structures**: Performance-conscious choices

**Clean Architecture Check**:
- [ ] **Layer Separation**: Correct dependency direction
- [ ] **SOLID Compliance**: No violations

**Validation Commands**:
```bash
# Python/FastAPI (uv)
uv run pytest --cov=src --cov-report=term-missing
uv run ruff check .
uv run ruff format --check .
uv run mypy src/
uv sync

# TypeScript/React
npm test -- --coverage
npm run lint
npm run format:check
npx tsc --noEmit
npm run build
```

---

### Phase 2: [Core Feature Phase Name]
**Goal**: [Specific deliverable]
**Estimated Time**: X hours
**Status**: ⏳ Pending | 🔄 In Progress | ✅ Complete

#### 📖 Code Analysis (Required Before Implementation)
- [ ] Review Phase 1 results
- [ ] Analyze additional related code

#### 🔴 RED: Write Failing Tests
- [ ] **Test 2.1**: Unit test for [functionality]
- [ ] **Test 2.2**: Integration test for [interaction]

#### 🟢 GREEN: Implement to Pass Tests
- [ ] **Task 2.3**: Implement [component]
- [ ] **Task 2.4**: Implement [integration]

#### 🔵 REFACTOR: Quality Improvement
- [ ] **Task 2.5**: Refactoring
  - [ ] Remove duplication
  - [ ] Improve naming
  - [ ] Optimize structure

#### ✋ Quality Gate
[Same checklist as Phase 1]

---

### Phase 3: [Enhancement Phase Name]
**Goal**: [Specific deliverable]
**Estimated Time**: X hours
**Status**: ⏳ Pending | 🔄 In Progress | ✅ Complete

#### 📖 Code Analysis (Required Before Implementation)
- [ ] Review previous Phase results
- [ ] Analyze final integration impact

#### 🔴 RED / 🟢 GREEN / 🔵 REFACTOR
[Same structure as previous Phases]

#### ✋ Quality Gate
[Same checklist as Phase 1]

---

## ⚠️ Risk Assessment

| Risk | Probability | Impact | Mitigation Strategy |
|------|-------------|--------|---------------------|
| Conflict with existing code | Low/Med/High | Low/Med/High | Pre-analyze impact scope |
| Performance degradation | Low/Med/High | Low/Med/High | Benchmark testing |
| Insufficient testing | Low/Med/High | Low/Med/High | Set coverage targets |

---

## 🔄 Rollback Strategy

### If Phase 1 Fails
- Revert code changes: [File list]
- Restore config: [Config items]
- Remove dependencies: [Added dependencies]

### If Phase 2 Fails
- Restore to Phase 1 complete state
- Revert changes: [File list]

### If Phase 3 Fails
- Restore to Phase 2 complete state
- [Additional cleanup]

---

## 📊 Progress Tracking

### Completion Status
- **Phase 1**: ⏳ 0% | 🔄 50% | ✅ 100%
- **Phase 2**: ⏳ 0% | 🔄 50% | ✅ 100%
- **Phase 3**: ⏳ 0% | 🔄 50% | ✅ 100%

**Overall Progress**: X% complete

### Time Tracking
| Phase | Estimated | Actual | Variance |
|-------|-----------|--------|----------|
| Phase 1 | X hours | Y hours | +/- Z hours |
| Phase 2 | X hours | - | - |
| Phase 3 | X hours | - | - |

---

## 📝 Notes & Learnings

### Codebase Insights
- [Important findings from reading code]
- [Lessons from existing patterns]

### Implementation Notes
- [Insights discovered during implementation]
- [Decisions changed from original plan]

### Blockers Encountered
- **Blocker 1**: [Description] → [Resolution]

### Improvements for Future
- [What to do differently next time]
- [What worked especially well]

---

## ✅ Final Checklist

**Final Verification Before Completion**:
- [ ] All phases complete and Quality Gate passed
- [ ] Full integration testing performed
- [ ] Documentation updated
- [ ] Performance benchmark targets met
- [ ] Security review complete
- [ ] Clean Architecture compliance verified
- [ ] SOLID principles compliance verified
- [ ] Code quality standards met (simplicity, clarity, no duplication)

---

**Plan Status**: 🔄 In Progress
**Next Action**: [Next task]
**Blocked By**: [Current blocker] or None