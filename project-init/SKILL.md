---
name: vibe-coding-planner
description: Planning and development skill optimized for vibe coding. Supports Clean Architecture, SOLID principles, and quality-driven development. Specialized for Python, TypeScript, FastAPI, and React projects. Keywords: plan, planning, vibe coding, clean architecture, solid, quality, python, typescript, fastapi, react.
---

# Vibe Coding Planner

## 🎯 Purpose

Generate structured development plans based on vibe coding philosophy:
- **Codebase-Aware**: Always consider the full context
- **Immediate Validation**: Always verify immediately after writing code
- **No Guessing**: Read actual code and judge, don't assume
- **Quality First**: Prioritize simplicity, clarity, and maintainability

---

## 🧠 Core Principles: Vibe Coding Philosophy

### 1. Codebase First
```
⛔ NEVER DO:
- Implement based on guesses without reading code
- Introduce new patterns ignoring existing ones
- Judge the whole by looking at only part

✅ ALWAYS DO:
- Read all related code before starting work
- Understand existing patterns and conventions
- Check dependencies and impact scope
```

### 2. Immediate Validation
```
After every code change:
1. Verify build/compile
2. Run linter/formatter
3. Type check (if applicable)
4. Run related tests
5. Manual behavior verification
```

### 3. Simplicity First
```
Complex solution vs Simple solution → Always choose simplicity

Judgment Criteria:
- Is the line count minimal?
- Is it understandable at a glance?
- Are dependencies minimal?
- Is it easy to test?
```

---

## 🏗️ Clean Architecture Guide

### Layer Structure
```
┌─────────────────────────────────────────────────────┐
│                    Presentation                      │
│         (React Components, FastAPI Routes)           │
├─────────────────────────────────────────────────────┤
│                    Application                       │
│            (Use Cases, Services, DTOs)              │
├─────────────────────────────────────────────────────┤
│                      Domain                          │
│        (Entities, Value Objects, Interfaces)        │
├─────────────────────────────────────────────────────┤
│                   Infrastructure                     │
│    (Repositories, External APIs, Database)          │
└─────────────────────────────────────────────────────┘
```

### Python/FastAPI Project Structure
```
src/
├── domain/                 # Core business logic
│   ├── entities/          # Entities, Value Objects
│   ├── interfaces/        # Abstract interfaces
│   └── exceptions/        # Domain exceptions
├── application/           # Application logic
│   ├── use_cases/         # Use Cases
│   ├── services/          # Application services
│   └── dto/               # Data Transfer Objects
├── infrastructure/        # External system integration
│   ├── repositories/      # Repository implementations
│   ├── database/          # DB config, migrations
│   └── external/          # External API clients
└── presentation/          # API layer
    ├── api/               # FastAPI routers
    ├── schemas/           # Pydantic schemas
    └── dependencies/      # Dependency injection
```

### TypeScript/React Project Structure
```
src/
├── domain/                # Core business logic
│   ├── entities/         # Types, Interfaces
│   ├── repositories/     # Repository interfaces
│   └── errors/           # Custom errors
├── application/          # Application logic
│   ├── use-cases/        # Use Cases
│   ├── services/         # Service logic
│   └── dto/              # DTO types
├── infrastructure/       # External systems
│   ├── api/              # API clients
│   ├── storage/          # Local storage
│   └── repositories/     # Repository implementations
└── presentation/         # UI layer
    ├── components/       # React components
    ├── hooks/            # Custom hooks
    ├── pages/            # Page components
    └── contexts/         # Context API
```

---

## 📏 SOLID Principles Checklist

### S - Single Responsibility
- [ ] Does the class/function have only one responsibility?
- [ ] Is there only one reason to change?
- [ ] Does the name clearly describe the role?

### O - Open/Closed
- [ ] Is it open for extension?
- [ ] Is it closed for modification?
- [ ] Are there extension points through abstraction?

### L - Liskov Substitution
- [ ] Can subtypes substitute for base types?
- [ ] Does it not violate contracts?
- [ ] Is exception handling consistent?

### I - Interface Segregation
- [ ] Are interfaces small and focused?
- [ ] Do clients not depend on unused methods?
- [ ] Are interfaces separated by role?

### D - Dependency Inversion
- [ ] Do high-level modules not depend on low-level modules?
- [ ] Do they depend on abstractions?
- [ ] Is dependency injection used?

---

## 🎯 Code Quality Standards

### 1. Simplicity
```python
# ❌ Over-engineering
class UserServiceFactoryBuilder:
    def create_factory(self):
        return UserServiceFactory()

# ✅ Simple solution
class UserService:
    def get_user(self, user_id: str) -> User:
        return self.repository.find(user_id)
```

### 2. Clarity
```typescript
// ❌ Unclear names
const d = getData();
const p = process(d);

// ✅ Clear names
const userOrders = fetchUserOrders(userId);
const validatedOrders = validateOrderStatus(userOrders);
```

### 3. DRY (Don't Repeat Yourself)
```python
# ❌ Duplicate code
def get_active_users():
    users = db.query(User).filter(User.status == 'active').all()
    return [UserDTO.from_entity(u) for u in users]

def get_admin_users():
    users = db.query(User).filter(User.role == 'admin').all()
    return [UserDTO.from_entity(u) for u in users]

# ✅ Extract and reuse
def _get_users_by_filter(filter_condition) -> list[UserDTO]:
    users = db.query(User).filter(filter_condition).all()
    return [UserDTO.from_entity(u) for u in users]

def get_active_users():
    return _get_users_by_filter(User.status == 'active')

def get_admin_users():
    return _get_users_by_filter(User.role == 'admin')
```

### 4. Appropriate Data Structures
```typescript
// ❌ O(n) lookup
const users: User[] = [...];
const user = users.find(u => u.id === targetId);

// ✅ O(1) lookup
const usersById: Map<string, User> = new Map();
const user = usersById.get(targetId);
```

### 5. Performance and Resource Management
```python
# ❌ Memory waste
def process_large_file(path: str):
    content = open(path).read()
    for line in content.split('\n'):
        process(line)

# ✅ Streaming processing
def process_large_file(path: str):
    with open(path) as f:
        for line in f:
            process(line)
```

---

## 📋 Planning Workflow

### Step 1: Codebase Analysis (Required)
```
⚠️ DO NOT plan without reading code!
1. Read all related files
2. Understand existing architecture patterns
3. Create dependency map
4. Analyze impact scope
5. Check existing test structure
```

### Step 2: Phase Decomposition (TDD Integration)
Each phase must satisfy:
- **Tests First**: Write tests before implementation
- **1-4 hours** to complete
- **Independent rollback** possible
- **Verifiable** deliverables

### Step 3: Generate Plan Document
Create `docs/plans/PLAN_<feature-name>.md`

### Step 4: User Approval
**Important**: Must get approval before starting implementation

---

## ✋ Quality Gate Standards

### Build & Test
- [ ] **Build Success**: Compile/build without errors
- [ ] **All Tests Pass**: No skipped tests
- [ ] **Coverage Maintained**: No decrease from baseline

### TDD Compliance
- [ ] **RED**: Tests written first and fail
- [ ] **GREEN**: Minimal code to pass tests
- [ ] **REFACTOR**: Quality improved while maintaining tests

### Code Quality
- [ ] **Linting**: No errors/warnings
- [ ] **Formatting**: Project standard compliance
- [ ] **Type Check**: Pass

### Vibe Coding Check
- [ ] **Simplicity**: Is there no simpler solution?
- [ ] **Clarity**: Is code self-explanatory?
- [ ] **No Duplication**: DRY principle compliance
- [ ] **Verification Complete**: Confirmed by execution

---

## 🛠️ Validation Commands

### Python/FastAPI (uv)
```bash
uv run pytest --cov=src --cov-report=html
uv run ruff check .
uv run ruff format --check .
uv run mypy src/
uv sync
```

### TypeScript/React
```bash
npm test -- --coverage
npm run lint
npm run format:check
npx tsc --noEmit
npm run build
```

---

## 📊 Phase Sizing Guide

| Size | Phases | Total Time | Examples |
|------|--------|------------|----------|
| Small | 2-3 | 3-6 hours | Single component, simple feature |
| Medium | 4-5 | 8-15 hours | Auth system, CRUD features |
| Large | 6-7 | 15-25 hours | Complex integration, architecture changes |

---

## 🧠 Codebase Context & Session Memory

### CRITICAL: Whole-Codebase Thinking

```
⚠️ EVERY Implementation Must Consider:

1. □ How is this done ELSEWHERE in this project?
2. □ What PATTERNS already exist that I should follow?
3. □ What UTILITIES already exist that I can reuse?
4. □ Will my change BREAK anything else?
```

### Before Writing ANY Code

| Question | Action |
|----------|--------|
| Similar code exists? | `grep -r "similar_term" src/` → Use as reference |
| Utility already exists? | Check `utils/`, `helpers/`, `lib/` folders |
| Naming convention? | Look at 3+ similar files for pattern |
| Import style? | Copy from existing file in same folder |

### Session Context Memory

```
⚠️ IN LONG CONVERSATIONS:

1. REMEMBER what was implemented earlier
2. CHECK for contradictions with previous code
3. VERIFY patterns are consistent across all changes
4. DON'T repeat mistakes already corrected
5. DON'T reinvent what was already created this session
```

### Cross-File Impact Check

```markdown
Before ANY change, verify:
- [ ] All CALLERS of modified code still work
- [ ] All DEPENDENCIES are used correctly  
- [ ] SHARED types/interfaces aren't broken
- [ ] TESTS cover the change
```

### Consistency First

```
If unsure about any pattern:
1. STOP
2. SEARCH codebase for similar examples
3. COPY the existing pattern exactly
4. ONLY deviate if there's a specific reason
```

---

## 📚 Supporting Files
- [plan-template.md](plan-template.md) - Full Plan Document Template