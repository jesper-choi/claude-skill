---
name: vibe-coding-feature-add
description: Feature addition skill optimized for vibe coding. Safely adds new features to existing codebase. Follows Clean Architecture and SOLID principles. Keywords: feature, add, implement, new, function, capability, enhancement, python, typescript, fastapi, react.
---

# Vibe Coding: Feature Add

## 🎯 Purpose

Add new features to existing codebase **safely and consistently**:
- **Respect Existing Code**: Maintain current patterns and conventions
- **Incremental Integration**: Break into small units and add safely
- **Minimize Impact**: Prevent side effects on existing features
- **Maintain Quality**: Maintain/improve test coverage and code quality

---

## 🧠 Core Principles: Vibe Coding for Feature Addition

### 1. Analyze First
```
⛔ NEVER DO:
- Implement new features without reading existing code
- Introduce new patterns ignoring existing ones
- Skip checking if similar existing features exist

✅ ALWAYS DO:
- Find and read similar existing feature code
- Understand existing architecture patterns
- Identify all affected modules
- Check existing test patterns
```

### 2. Reuse Patterns
```
When adding new features:
1. Similar existing feature? → Copy and modify
2. Reusable utilities? → Reuse
3. Can extend existing interface? → Extend
4. Need new pattern? → Minimize
```

### 3. Incremental Integration
```
Big feature = Combination of small features

Decomposition Strategy:
1. Break into independently testable units
2. Each unit completes within 1-4 hours
3. Keep each unit in working state
4. Integrate incrementally
```

---

## 🏗️ Feature Add Workflow

### Step 1: Codebase Analysis (Required)
```markdown
Analysis Checklist:
- [ ] Check similar existing feature code
- [ ] Understand existing patterns per layer
- [ ] Check reusable utilities/helpers
- [ ] Create list of affected modules
- [ ] Understand existing test structure
```

### Step 2: Design Review
```markdown
Design Checklist:
- [ ] Determine Clean Architecture layers
- [ ] Define required interfaces
- [ ] Decide dependency injection approach
- [ ] Decide error handling strategy
- [ ] Establish test strategy
```

### Step 3: TDD-Based Implementation
```
For each unit:
🔴 RED → 🟢 GREEN → 🔵 REFACTOR
```

### Step 4: Integration and Verification
```markdown
Integration Checklist:
- [ ] All existing tests pass
- [ ] All new tests pass
- [ ] Manual E2E testing
- [ ] Check performance impact
```

---

## 📏 SOLID Checklist for Feature Addition

### When Adding New Classes/Modules
- [ ] **S**: Does this class have only one responsibility?
- [ ] **O**: Implemented through extension without modifying existing code?
- [ ] **L**: Does not violate existing interfaces?
- [ ] **I**: Implements only necessary interfaces?
- [ ] **D**: Depends on abstractions, not concrete implementations?

### When Modifying Existing Code
- [ ] Is modification really necessary? (Can't solve through extension?)
- [ ] Is modification scope minimal?
- [ ] Do existing tests still pass?
- [ ] Are new tests added?

---

## 🎯 Code Quality Standards (Feature Addition)

### 1. Consistency
```python
# ❌ Ignoring existing patterns
class NewFeature:
    def getData(self):  # camelCase - violation if existing is snake_case
        pass

# ✅ Following existing patterns
class NewFeature:
    def get_data(self):  # Following existing convention
        pass
```

### 2. Reusability
```typescript
// ❌ Duplicate implementation
const formatDateNew = (date: Date) => {
  return date.toISOString().split('T')[0];
};

// ✅ Reusing existing utility
import { formatDate } from '@/utils/date';
const formatted = formatDate(date);
```

### 3. Extensibility
```python
# ❌ Hard-coded branching
def process(type: str):
    if type == "A":
        return process_a()
    elif type == "B":
        return process_b()
    # Code modification needed when adding new type

# ✅ Using strategy pattern
class ProcessorRegistry:
    def register(self, type: str, processor: Processor):
        self._processors[type] = processor
    
    def process(self, type: str):
        return self._processors[type].process()
```

### 4. Testability
```python
# ❌ Hard to test
class Feature:
    def execute(self):
        data = requests.get("https://api.example.com")
        return self._process(data)

# ✅ Easy to test with dependency injection
class Feature:
    def __init__(self, api_client: ApiClient):
        self._api_client = api_client
    
    def execute(self):
        data = self._api_client.get_data()
        return self._process(data)
```

---

## 📋 Feature Add Plan Template

### Feature Size Guide

| Size | Phases | Time | Characteristics |
|------|--------|------|-----------------|
| **Small** | 2-3 | 2-6 hours | Single component, reusing existing patterns |
| **Medium** | 4-5 | 8-15 hours | Multiple layer modifications, new module addition |
| **Large** | 6-7 | 15-30 hours | Architecture impact, complex integration |

### Phase Structure (for Feature Addition)

```markdown
### Phase N: [Feature Unit]

#### 📖 Code Analysis
- [ ] Check similar feature code
- [ ] Identify reusable code
- [ ] Understand impact scope

#### 🔴 RED: Write Tests
- [ ] Unit tests (following existing test patterns)
- [ ] Integration tests (if needed)

#### 🟢 GREEN: Implement
- [ ] Implement following existing patterns
- [ ] Reuse existing utilities

#### 🔵 REFACTOR: Clean Up
- [ ] Remove duplication
- [ ] Verify consistency with existing code

#### ✋ Quality Gate
- [ ] All existing tests pass
- [ ] All new tests pass
- [ ] Lint/format pass
- [ ] Consistency with existing patterns verified
```

---

## ✋ Quality Gate (for Feature Addition)

### Required Verification Items

**Existing Code Impact**:
- [ ] **Existing Tests Pass**: All existing tests 100% pass
- [ ] **No Regression**: Existing features work correctly
- [ ] **Performance Maintained**: No performance degradation

**New Feature Quality**:
- [ ] **TDD Compliance**: Red-Green-Refactor cycle complete
- [ ] **Coverage**: New code ≥80% coverage
- [ ] **Documentation**: Public API documented

**Consistency**:
- [ ] **Pattern Compliance**: Following existing architecture patterns
- [ ] **Naming**: Following existing naming conventions
- [ ] **Style**: Lint/format rules pass

**SOLID Principles**:
- [ ] **Single Responsibility**: New classes/functions have single responsibility
- [ ] **Open/Closed**: Existing code modification minimized
- [ ] **Dependency Inversion**: Depends on abstractions

---

## 🛠️ Validation Commands

### Python/FastAPI (uv)
```bash
# All tests (existing + new)
uv run pytest --cov=src --cov-report=term-missing

# Lint & Format
uv run ruff check .
uv run ruff format --check .

# Type check
uv run mypy src/

# Specific feature test
uv run pytest tests/ -k "feature_name" -v

# Sync dependencies
uv sync
```

### TypeScript/React
```bash
# All tests
npm test -- --coverage

# Lint & Format
npm run lint
npm run format:check

# Type check
npx tsc --noEmit

# Build verification
npm run build
```

---

## ⚠️ Cautions

### Anti-patterns to Avoid

| Anti-pattern | Problem | Alternative |
|--------------|---------|-------------|
| Big Bang Integration | Large change at once = High risk | Incremental integration |
| Copy-paste & modify | Produces duplicate code | Abstract then reuse |
| Ignoring existing patterns | Reduces consistency | Analyze and follow existing patterns |
| Tests later | Quality degradation | Strict TDD compliance |

### Checkpoint Questions

Before writing code:
- "Does a similar feature already exist?"
- "Is there reusable code?"
- "What are the existing patterns?"

After writing code:
- "Do all existing tests pass?"
- "Is it consistent with existing code?"
- "Was unnecessary complexity added?"

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

### Common Consistency Mistakes

| Mistake | Example | Prevention |
|---------|---------|------------|
| **Reinventing existing utility** | Writing new `formatDate()` when one exists | Search utils/ folder first |
| **Inconsistent API patterns** | REST style when project uses RPC style | Check existing endpoints |
| **Different state management** | Local state when project uses global store | Look at similar components |
| **Ignoring project structure** | Flat files when project uses feature folders | Mirror existing structure |

### Cross-File Impact Awareness

```markdown
Before modifying ANY file, check:

1. **Who calls this code?**
   → Search: references to function/class name
   → Will callers break with my change?

2. **What does this code call?**
   → Are those dependencies still correct?
   → Am I using them correctly?

3. **Shared types/interfaces?**
   → If I change a type, what else breaks?
   → Search for all usages first
```

### Remembering Session Context

```
⚠️ IN LONG SESSIONS:

1. Re-read code written earlier in this conversation
2. Check: "Did I already implement something similar?"
3. Check: "Did I make a mistake earlier that I corrected?"
4. Ensure: Current code doesn't contradict earlier code
5. Verify: Patterns are consistent across all changes
```

### Quick Consistency Checklist

```markdown
Before completing ANY task:
- [ ] Same patterns as existing similar code
- [ ] Same naming conventions as project
- [ ] Same error handling approach
- [ ] Same import/export style
- [ ] No contradiction with earlier session work
- [ ] Reusing existing utilities (not reinventing)
```

---

## 📚 Supporting Files
- [plan-template.md](plan-template.md) - Feature Addition Plan Template
