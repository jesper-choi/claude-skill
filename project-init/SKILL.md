---
name: vibe-coding-planner
description: 바이브코딩에 최적화된 기능 계획 및 개발 스킬. Clean Architecture, SOLID 원칙, 품질 중심 개발을 지원합니다. Python, TypeScript, FastAPI, React 프로젝트에 특화. Keywords: plan, planning, vibe coding, clean architecture, solid, quality, python, typescript, fastapi, react.
---

# Vibe Coding Planner

## 🎯 Purpose

바이브코딩 철학에 기반한 구조화된 개발 계획 생성:
- **전체 코드베이스 인식**: 항상 전체 맥락을 고려한 개발
- **즉각적 검증**: 코드 작성 직후 반드시 검증
- **추측 금지**: 실제 코드를 읽고 판단, 가정하지 않음
- **품질 우선**: 단순함, 명확함, 유지보수성 최우선

---

## 🧠 핵심 원칙: 바이브코딩 철학

### 1. 코드베이스 우선 (Codebase First)
```
⛔ 절대 하지 말 것:
- 코드를 읽지 않고 추측으로 구현
- 기존 패턴을 무시한 새로운 방식 도입
- 일부만 보고 전체를 판단

✅ 반드시 할 것:
- 작업 전 관련 코드 전체 읽기
- 기존 패턴과 컨벤션 파악
- 의존성과 영향 범위 확인
```

### 2. 즉각 검증 (Immediate Validation)
```
모든 코드 변경 후:
1. 빌드/컴파일 확인
2. 린터/포매터 실행
3. 타입 체크 (해당시)
4. 관련 테스트 실행
5. 수동 동작 확인
```

### 3. 단순함 우선 (Simplicity First)
```
복잡한 해결책 vs 단순한 해결책 → 항상 단순함 선택

판단 기준:
- 코드 줄 수가 적은가?
- 한눈에 이해되는가?
- 의존성이 최소인가?
- 테스트하기 쉬운가?
```

---

## 🏗️ Clean Architecture 가이드

### 레이어 구조

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

### Python/FastAPI 프로젝트 구조
```
src/
├── domain/                 # 핵심 비즈니스 로직
│   ├── entities/          # 엔티티, 값 객체
│   ├── interfaces/        # 추상 인터페이스 (Repository 등)
│   └── exceptions/        # 도메인 예외
├── application/           # 애플리케이션 로직
│   ├── use_cases/         # 유스케이스
│   ├── services/          # 애플리케이션 서비스
│   └── dto/               # 데이터 전송 객체
├── infrastructure/        # 외부 시스템 연동
│   ├── repositories/      # Repository 구현체
│   ├── database/          # DB 설정, 마이그레이션
│   └── external/          # 외부 API 클라이언트
└── presentation/          # API 계층
    ├── api/               # FastAPI 라우터
    ├── schemas/           # Pydantic 스키마
    └── dependencies/      # 의존성 주입
```

### TypeScript/React 프로젝트 구조
```
src/
├── domain/                # 핵심 비즈니스 로직
│   ├── entities/         # 타입, 인터페이스
│   ├── repositories/     # Repository 인터페이스
│   └── errors/           # 커스텀 에러
├── application/          # 애플리케이션 로직
│   ├── use-cases/        # 유스케이스
│   ├── services/         # 서비스 로직
│   └── dto/              # DTO 타입
├── infrastructure/       # 외부 시스템
│   ├── api/              # API 클라이언트
│   ├── storage/          # 로컬 스토리지
│   └── repositories/     # Repository 구현
└── presentation/         # UI 계층
    ├── components/       # React 컴포넌트
    ├── hooks/            # 커스텀 훅
    ├── pages/            # 페이지 컴포넌트
    └── contexts/         # Context API
```

---

## 📏 SOLID 원칙 체크리스트

### S - Single Responsibility (단일 책임)
- [ ] 클래스/함수가 하나의 책임만 가지는가?
- [ ] 변경 이유가 하나만 존재하는가?
- [ ] 이름이 역할을 명확히 설명하는가?

### O - Open/Closed (개방/폐쇄)
- [ ] 확장에 열려있는가? (새 기능 추가 용이)
- [ ] 수정에 닫혀있는가? (기존 코드 변경 최소화)
- [ ] 추상화를 통한 확장 포인트가 있는가?

### L - Liskov Substitution (리스코프 치환)
- [ ] 하위 타입이 상위 타입을 대체 가능한가?
- [ ] 계약(인터페이스)을 위반하지 않는가?
- [ ] 예외 처리가 일관적인가?

### I - Interface Segregation (인터페이스 분리)
- [ ] 인터페이스가 작고 집중적인가?
- [ ] 클라이언트가 사용하지 않는 메서드에 의존하지 않는가?
- [ ] 역할별로 인터페이스가 분리되어 있는가?

### D - Dependency Inversion (의존성 역전)
- [ ] 고수준 모듈이 저수준 모듈에 의존하지 않는가?
- [ ] 추상화에 의존하는가? (구체 구현 X)
- [ ] 의존성 주입을 사용하는가?

---

## 🎯 코드 품질 기준

### 1. 단순함 (Simplicity)
```python
# ❌ 과도한 엔지니어링
class UserServiceFactoryBuilder:
    def create_factory(self):
        return UserServiceFactory()

# ✅ 단순한 해결책
class UserService:
    def get_user(self, user_id: str) -> User:
        return self.repository.find(user_id)
```

### 2. 명확함 (Clarity)
```typescript
// ❌ 불명확한 이름
const d = getData();
const p = process(d);

// ✅ 명확한 이름
const userOrders = fetchUserOrders(userId);
const validatedOrders = validateOrderStatus(userOrders);
```

### 3. 중복 제거 (DRY)
```python
# ❌ 중복 코드
def get_active_users():
    users = db.query(User).filter(User.status == 'active').all()
    return [UserDTO.from_entity(u) for u in users]

def get_admin_users():
    users = db.query(User).filter(User.role == 'admin').all()
    return [UserDTO.from_entity(u) for u in users]

# ✅ 추출 및 재사용
def _get_users_by_filter(filter_condition) -> list[UserDTO]:
    users = db.query(User).filter(filter_condition).all()
    return [UserDTO.from_entity(u) for u in users]

def get_active_users():
    return _get_users_by_filter(User.status == 'active')

def get_admin_users():
    return _get_users_by_filter(User.role == 'admin')
```

### 4. 적절한 자료구조
```typescript
// ❌ 부적절한 자료구조 (O(n) 탐색)
const users: User[] = [...];
const user = users.find(u => u.id === targetId);

// ✅ 적절한 자료구조 (O(1) 탐색)
const usersById: Map<string, User> = new Map();
const user = usersById.get(targetId);
```

### 5. 성능과 리소스 관리
```python
# ❌ 메모리 낭비
def process_large_file(path: str):
    content = open(path).read()  # 전체 로드
    for line in content.split('\n'):
        process(line)

# ✅ 스트리밍 처리
def process_large_file(path: str):
    with open(path) as f:
        for line in f:  # 한 줄씩 처리
            process(line)
```

---

## 📋 Planning Workflow

### Step 1: 코드베이스 분석 (필수)
```
⚠️ 코드를 읽지 않고 계획하지 말 것!

1. 관련 파일 전체 읽기
2. 기존 아키텍처 패턴 파악
3. 의존성 맵 작성
4. 영향 범위 분석
5. 기존 테스트 구조 확인
```

### Step 2: 페이즈 분해 (TDD 통합)
각 페이즈는 다음을 충족:
- **테스트 우선**: 구현 전 테스트 작성
- **1-4시간** 이내 완료 가능
- **독립적 롤백** 가능
- **검증 가능한** 결과물

**페이즈 구조**:
```markdown
### Phase N: [구체적 결과물]
**Goal**: [이 페이즈에서 동작하는 기능]
**Estimated Time**: X시간

#### 🔴 RED: 실패하는 테스트 작성
- [ ] 테스트 케이스 1
- [ ] 테스트 케이스 2

#### 🟢 GREEN: 테스트 통과 구현
- [ ] 최소 구현 1
- [ ] 최소 구현 2

#### 🔵 REFACTOR: 품질 개선
- [ ] 중복 제거
- [ ] 네이밍 개선
- [ ] 구조 최적화

#### ✋ Quality Gate
[전체 검증 체크리스트]
```

### Step 3: 계획 문서 생성
`docs/plans/PLAN_<feature-name>.md` 생성

### Step 4: 사용자 승인
**중요**: 구현 시작 전 반드시 승인 받기

### Step 5: 문서 생성 및 안내

---

## ✋ Quality Gate 표준

### 빌드 & 테스트
- [ ] **빌드 성공**: 에러 없이 컴파일/빌드
- [ ] **모든 테스트 통과**: 스킵된 테스트 없음
- [ ] **커버리지 유지**: 기존 대비 감소 없음

### TDD 준수
- [ ] **RED**: 테스트가 먼저 작성되고 실패함
- [ ] **GREEN**: 테스트 통과를 위한 최소 코드
- [ ] **REFACTOR**: 테스트 유지하며 품질 개선

### 코드 품질
- [ ] **린팅**: 에러/경고 없음
- [ ] **포매팅**: 프로젝트 표준 준수
- [ ] **타입 체크**: (해당시) 통과

### Clean Architecture 준수
- [ ] **레이어 분리**: 의존성 방향 올바름
- [ ] **인터페이스 사용**: 구체 구현에 직접 의존 X
- [ ] **단일 책임**: 각 모듈이 하나의 역할

### 바이브코딩 체크
- [ ] **단순함**: 더 단순한 해결책이 없는가?
- [ ] **명확함**: 코드가 자기 설명적인가?
- [ ] **중복 없음**: DRY 원칙 준수
- [ ] **검증 완료**: 실행하여 동작 확인

---

## 🛠️ 기술 스택별 검증 명령어

### Python/FastAPI (uv)
```bash
# 테스트
uv run pytest --cov=src --cov-report=html

# 린팅 & 포매팅
uv run ruff check .
uv run ruff format --check .

# 타입 체크
uv run mypy src/

# 보안 검사
uv run bandit -r src/
uv run pip-audit

# 의존성 동기화
uv sync
```

### TypeScript/React
```bash
# 테스트
npm test -- --coverage

# 린팅 & 포매팅
npm run lint
npm run format:check

# 타입 체크
npx tsc --noEmit

# 빌드
npm run build
```

---

## 📊 Phase Sizing 가이드

| 규모 | 페이즈 수 | 총 시간 | 예시 |
|------|----------|---------|------|
| Small | 2-3 | 3-6시간 | 단일 컴포넌트, 간단한 기능 |
| Medium | 4-5 | 8-15시간 | 인증 시스템, CRUD 기능 |
| Large | 6-7 | 15-25시간 | 복잡한 통합, 아키텍처 변경 |

---

## ⚠️ Risk Assessment

각 리스크에 대해:
- **확률**: Low/Medium/High
- **영향**: Low/Medium/High
- **완화 전략**: 구체적 조치

**일반적 리스크**:
| 리스크 | 완화 전략 |
|--------|----------|
| 기존 코드와 충돌 | 영향 범위 사전 분석, 점진적 변경 |
| 성능 저하 | 벤치마크 테스트, 프로파일링 |
| 테스트 부족 | 커버리지 목표 설정, TDD 엄격 준수 |
| 복잡도 증가 | 단순함 원칙 검토, 리팩토링 |

---

## 🔄 Rollback Strategy

각 페이즈별 롤백 계획:
1. **코드 변경 취소**: git revert 또는 수동 복원
2. **DB 마이그레이션**: 역방향 마이그레이션 준비
3. **설정 복원**: 이전 설정 백업
4. **의존성 복원**: package.json/requirements.txt 복원

---

## 📚 Supporting Files
- [plan-template.md](plan-template.md) - 전체 계획 문서 템플릿