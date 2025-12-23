---
name: vibe-coding-feature-add
description: 바이브코딩에 최적화된 기능 추가 스킬. 기존 코드베이스에 새로운 기능을 안전하게 추가합니다. Clean Architecture, SOLID 원칙 준수. Keywords: feature, add, implement, new, function, capability, enhancement, python, typescript, fastapi, react.
---

# Vibe Coding: Feature Add

## 🎯 Purpose

기존 코드베이스에 새로운 기능을 **안전하고 일관성 있게** 추가:
- **기존 코드 존중**: 현재 패턴과 컨벤션 유지
- **점진적 통합**: 작은 단위로 나누어 안전하게 추가
- **영향 최소화**: 기존 기능에 대한 사이드 이펙트 방지
- **품질 유지**: 테스트 커버리지와 코드 품질 유지/향상

---

## 🧠 핵심 원칙: 기능 추가 시 바이브코딩

### 1. 코드베이스 분석 우선 (Analyze First)
```
⛔ 절대 하지 말 것:
- 기존 코드를 읽지 않고 새 기능 구현
- 기존 패턴을 무시한 새로운 방식 도입
- 비슷한 기존 기능이 있는지 확인하지 않음

✅ 반드시 할 것:
- 유사한 기존 기능 코드 찾아 읽기
- 기존 아키텍처 패턴 파악
- 영향받는 모든 모듈 식별
- 기존 테스트 패턴 확인
```

### 2. 기존 패턴 재사용 (Reuse Patterns)
```
새 기능 추가 시:
1. 비슷한 기존 기능은? → 복사 후 수정
2. 사용 가능한 유틸리티는? → 재사용
3. 기존 인터페이스 확장 가능? → 확장
4. 새로운 패턴이 필요한가? → 최소화
```

### 3. 점진적 통합 (Incremental Integration)
```
큰 기능 = 작은 기능들의 조합

분해 전략:
1. 독립적으로 테스트 가능한 단위로 분해
2. 각 단위는 1-4시간 내 완료
3. 각 단위가 동작하는 상태 유지
4. 점진적으로 통합
```

---

## 🏗️ Feature Add 워크플로우

### Step 1: 코드베이스 분석 (필수)
```markdown
분석 체크리스트:
- [ ] 유사한 기존 기능 코드 확인
- [ ] 사용할 레이어별 기존 패턴 파악
- [ ] 재사용 가능한 유틸리티/헬퍼 확인
- [ ] 영향받는 모듈 목록 작성
- [ ] 기존 테스트 구조 파악
```

### Step 2: 설계 검토
```markdown
설계 체크리스트:
- [ ] Clean Architecture 레이어 결정
- [ ] 필요한 인터페이스 정의
- [ ] 의존성 주입 방식 결정
- [ ] 에러 처리 전략 결정
- [ ] 테스트 전략 수립
```

### Step 3: TDD 기반 구현
```
각 단위별:
🔴 RED → 🟢 GREEN → 🔵 REFACTOR
```

### Step 4: 통합 및 검증
```markdown
통합 체크리스트:
- [ ] 기존 테스트 모두 통과
- [ ] 새 테스트 모두 통과
- [ ] 수동 E2E 테스트
- [ ] 성능 영향 확인
```

---

## 📏 기능 추가 시 SOLID 체크리스트

### 새 클래스/모듈 추가 시
- [ ] **S**: 이 클래스는 하나의 책임만 가지는가?
- [ ] **O**: 기존 코드 수정 없이 확장으로 구현했는가?
- [ ] **L**: 기존 인터페이스를 위반하지 않는가?
- [ ] **I**: 필요한 인터페이스만 구현하는가?
- [ ] **D**: 구체 구현이 아닌 추상화에 의존하는가?

### 기존 코드 수정 시
- [ ] 수정이 정말 필요한가? (확장으로 해결 불가?)
- [ ] 수정 범위가 최소인가?
- [ ] 기존 테스트가 여전히 통과하는가?
- [ ] 새로운 테스트가 추가되었는가?

---

## 🎯 코드 품질 기준 (기능 추가)

### 1. 일관성 (Consistency)
```python
# ❌ 기존 패턴 무시
class NewFeature:
    def getData(self):  # camelCase - 기존이 snake_case면 위반
        pass

# ✅ 기존 패턴 준수
class NewFeature:
    def get_data(self):  # 기존 컨벤션 따름
        pass
```

### 2. 재사용 (Reusability)
```typescript
// ❌ 중복 구현
const formatDateNew = (date: Date) => {
  return date.toISOString().split('T')[0];
};

// ✅ 기존 유틸리티 재사용
import { formatDate } from '@/utils/date';
const formatted = formatDate(date);
```

### 3. 확장성 (Extensibility)
```python
# ❌ 하드코딩된 분기
def process(type: str):
    if type == "A":
        return process_a()
    elif type == "B":
        return process_b()
    # 새 타입 추가시 코드 수정 필요

# ✅ 전략 패턴 사용
class ProcessorRegistry:
    def register(self, type: str, processor: Processor):
        self._processors[type] = processor
    
    def process(self, type: str):
        return self._processors[type].process()
```

### 4. 테스트 용이성 (Testability)
```python
# ❌ 테스트하기 어려움
class Feature:
    def execute(self):
        data = requests.get("https://api.example.com")
        return self._process(data)

# ✅ 의존성 주입으로 테스트 용이
class Feature:
    def __init__(self, api_client: ApiClient):
        self._api_client = api_client
    
    def execute(self):
        data = self._api_client.get_data()
        return self._process(data)
```

---

## 📋 Feature Add 계획 템플릿

### 기능 규모별 가이드

| 규모 | 페이즈 수 | 시간 | 특징 |
|------|----------|------|------|
| **Small** | 2-3 | 2-6시간 | 단일 컴포넌트, 기존 패턴 재사용 |
| **Medium** | 4-5 | 8-15시간 | 여러 레이어 수정, 새 모듈 추가 |
| **Large** | 6-7 | 15-30시간 | 아키텍처 영향, 복잡한 통합 |

### 페이즈 구조 (기능 추가용)

```markdown
### Phase N: [기능 단위]

#### 📖 코드 분석
- [ ] 유사 기능 코드 확인
- [ ] 재사용 가능 코드 식별
- [ ] 영향 범위 파악

#### 🔴 RED: 테스트 작성
- [ ] 유닛 테스트 (기존 테스트 패턴 따름)
- [ ] 통합 테스트 (필요시)

#### 🟢 GREEN: 구현
- [ ] 기존 패턴에 맞춰 구현
- [ ] 기존 유틸리티 재사용

#### 🔵 REFACTOR: 정리
- [ ] 중복 제거
- [ ] 기존 코드와 일관성 확인

#### ✋ Quality Gate
- [ ] 기존 테스트 모두 통과
- [ ] 새 테스트 모두 통과
- [ ] 린트/포맷 통과
- [ ] 기존 패턴과 일관성 확인
```

---

## ✋ Quality Gate (기능 추가용)

### 필수 검증 항목

**기존 코드 영향**:
- [ ] **기존 테스트 통과**: 모든 기존 테스트 100% 통과
- [ ] **회귀 없음**: 기존 기능 동작 확인
- [ ] **성능 유지**: 성능 저하 없음

**새 기능 품질**:
- [ ] **TDD 준수**: Red-Green-Refactor 사이클 완료
- [ ] **커버리지**: 새 코드 ≥80% 커버리지
- [ ] **문서화**: 공개 API 문서화

**일관성**:
- [ ] **패턴 준수**: 기존 아키텍처 패턴 따름
- [ ] **네이밍**: 기존 네이밍 컨벤션 따름
- [ ] **스타일**: 린트/포맷 규칙 통과

**SOLID 원칙**:
- [ ] **단일 책임**: 새 클래스/함수가 단일 책임
- [ ] **개방/폐쇄**: 기존 코드 수정 최소화
- [ ] **의존성 역전**: 추상화에 의존

---

## 🛠️ 검증 명령어

### Python/FastAPI (uv)
```bash
# 전체 테스트 (기존 + 신규)
uv run pytest --cov=src --cov-report=term-missing

# 린트 & 포맷
uv run ruff check .
uv run ruff format --check .

# 타입 체크
uv run mypy src/

# 특정 기능 테스트
uv run pytest tests/ -k "feature_name" -v

# 의존성 동기화
uv sync
```

### TypeScript/React
```bash
# 전체 테스트
npm test -- --coverage

# 린트 & 포맷
npm run lint
npm run format:check

# 타입 체크
npx tsc --noEmit

# 빌드 확인
npm run build
```

---

## ⚠️ 주의사항

### 피해야 할 안티패턴

| 안티패턴 | 문제점 | 대안 |
|---------|--------|------|
| Big Bang 통합 | 한 번에 큰 변경 = 높은 위험 | 점진적 통합 |
| 복붙 후 수정 | 중복 코드 양산 | 추상화 후 재사용 |
| 기존 패턴 무시 | 일관성 저하 | 기존 패턴 분석 및 준수 |
| 테스트 나중에 | 품질 저하 | TDD 엄격 준수 |

### 체크포인트 질문

코드 작성 전:
- "이미 비슷한 기능이 있는가?"
- "재사용할 수 있는 코드가 있는가?"
- "기존 패턴은 무엇인가?"

코드 작성 후:
- "기존 테스트가 모두 통과하는가?"
- "기존 코드와 일관성이 있는가?"
- "불필요한 복잡도가 추가되지 않았는가?"

---

## 📚 Supporting Files
- [plan-template.md](plan-template.md) - 기능 추가 계획 템플릿
