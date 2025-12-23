---
name: vibe-coding-bug-fix
description: 바이브코딩에 최적화된 버그 수정 스킬. 체계적인 문제 분석, 근본 원인 파악, 안전한 수정을 지원합니다. Keywords: bug, fix, debug, issue, error, problem, defect, hotfix, patch, python, typescript, fastapi, react.
---

# Vibe Coding: Bug Fix

## 🎯 Purpose

버그를 **체계적이고 안전하게** 수정:
- **증상이 아닌 원인 해결**: 근본 원인(Root Cause) 파악
- **재현 우선**: 버그를 먼저 재현하고 테스트로 캡처
- **회귀 방지**: 수정 후 동일 버그 재발 방지
- **최소 변경**: 필요한 최소한의 코드만 수정

---

## 🧠 핵심 원칙: 버그 수정 시 바이브코딩

### 1. 추측하지 말고 확인하라 (Verify, Don't Assume)
```
⛔ 절대 하지 말 것:
- 로그/에러 메시지만 보고 원인 추측
- 코드를 읽지 않고 수정 시도
- "아마 이것이 원인일 거야" 식 접근

✅ 반드시 할 것:
- 버그 재현 먼저 시도
- 관련 코드 전체 읽기
- 디버깅으로 실제 동작 확인
- 근본 원인 파악 후 수정
```

### 2. 테스트로 버그 캡처 (Capture with Test)
```
버그 수정 순서:
1. 버그 재현
2. 버그를 재현하는 테스트 작성 (FAIL)
3. 근본 원인 분석
4. 수정 (테스트 PASS)
5. 기존 테스트 모두 통과 확인
```

### 3. 최소 변경 원칙 (Minimal Change)
```
수정 범위 최소화:

✅ 좋은 수정:
- 버그 원인만 정확히 수정
- 관련 없는 코드 변경 없음
- 리팩토링은 별도 PR로

❌ 나쁜 수정:
- "ついでに" 다른 것도 수정
- 불필요한 코드 정리
- 범위를 넘어선 개선
```

---

## 🔍 Bug Fix 워크플로우

### Step 1: 버그 재현 (필수)
```markdown
재현 체크리스트:
- [ ] 버그 재현 성공
- [ ] 재현 조건 문서화
- [ ] 재현 단계 명확히 기록
```

### Step 2: 정보 수집
```markdown
수집할 정보:
- [ ] 에러 메시지/로그
- [ ] 스택 트레이스
- [ ] 입력 데이터
- [ ] 환경 정보
- [ ] 재현 빈도
```

### Step 3: 근본 원인 분석
```markdown
분석 체크리스트:
- [ ] 관련 코드 전체 읽기
- [ ] 실행 흐름 추적
- [ ] 의심 지점 디버깅
- [ ] 근본 원인 확정
```

### Step 4: 테스트로 버그 캡처
```markdown
테스트 작성:
- [ ] 버그를 재현하는 테스트 작성
- [ ] 테스트 실행 → FAIL 확인
- [ ] 이 테스트가 버그를 정확히 캡처하는지 확인
```

### Step 5: 수정 및 검증
```markdown
수정 체크리스트:
- [ ] 최소한의 코드만 수정
- [ ] 버그 테스트 PASS
- [ ] 기존 테스트 모두 PASS
- [ ] 수동 검증 완료
```

---

## 🔬 근본 원인 분석 (RCA) 가이드

### 5 Whys 기법
```
버그: 사용자가 로그인할 수 없다

Why 1: 왜 로그인이 안 되는가?
→ 인증 토큰이 만료되었다

Why 2: 왜 토큰이 만료되었는가?
→ 토큰 갱신 로직이 실행되지 않았다

Why 3: 왜 갱신 로직이 실행되지 않았는가?
→ 갱신 타이밍 계산이 잘못되었다

Why 4: 왜 타이밍 계산이 잘못되었는가?
→ UTC/로컬 시간 변환 버그

Why 5: 왜 시간 변환에 버그가 있는가?
→ 타임존 처리 누락 ← 근본 원인
```

### 디버깅 전략

**Python**:
```python
# 브레이크포인트
import pdb; pdb.set_trace()

# 또는 breakpoint() (Python 3.7+)
breakpoint()

# 로깅으로 추적
import logging
logging.debug(f"value: {value}, type: {type(value)}")
```

**TypeScript/JavaScript**:
```typescript
// 브레이크포인트
debugger;

// 콘솔 로깅
console.log('checkpoint', { value, state });

// 조건부 로깅
if (DEBUG) console.trace('stack trace here');
```

---

## 📏 버그 수정 체크리스트

### 수정 전
- [ ] 버그 재현 성공
- [ ] 관련 코드 전체 읽음
- [ ] 근본 원인 파악 완료
- [ ] 버그 캡처 테스트 작성 (FAIL)

### 수정 중
- [ ] 최소한의 코드만 수정
- [ ] 수정 의도가 명확함
- [ ] 부수효과(side effect) 없음

### 수정 후
- [ ] 버그 캡처 테스트 PASS
- [ ] 기존 테스트 100% PASS
- [ ] 수동 검증 완료
- [ ] 유사 버그 가능성 검토

---

## 🎯 버그 유형별 가이드

### 1. 로직 버그
```python
# 문제: 경계 조건 오류
# ❌ 버그
if count > 10:  # 10은 포함 안됨
    process()

# ✅ 수정
if count >= 10:  # 10 포함
    process()
```

**분석 포인트**:
- 경계 값 (boundary values)
- off-by-one 에러
- 조건문 논리

### 2. Null/None 관련 버그
```python
# 문제: None 체크 누락
# ❌ 버그
def get_name(user):
    return user.name  # user가 None이면 에러

# ✅ 수정
def get_name(user):
    if user is None:
        return None
    return user.name
```

```typescript
// ❌ 버그
const name = user.name;  // user가 undefined일 수 있음

// ✅ 수정
const name = user?.name ?? 'Unknown';
```

### 3. 비동기 버그
```python
# 문제: await 누락
# ❌ 버그
async def fetch_data():
    data = api.get_data()  # await 누락
    return process(data)

# ✅ 수정
async def fetch_data():
    data = await api.get_data()
    return process(data)
```

```typescript
// 문제: 레이스 컨디션
// ❌ 버그
useEffect(() => {
  fetchData().then(setData);  // 언마운트 후 setState 가능
}, []);

// ✅ 수정
useEffect(() => {
  let cancelled = false;
  fetchData().then(data => {
    if (!cancelled) setData(data);
  });
  return () => { cancelled = true; };
}, []);
```

### 4. 타입 관련 버그
```python
# 문제: 타입 불일치
# ❌ 버그
def calculate(value):
    return value + 10  # value가 str이면 에러

# ✅ 수정
def calculate(value: int) -> int:
    return int(value) + 10
```

### 5. 상태 관리 버그
```typescript
// 문제: 직접 상태 변경
// ❌ 버그
const updateItem = (items, id, value) => {
  const item = items.find(i => i.id === id);
  item.value = value;  // 직접 변경
  setItems(items);
};

// ✅ 수정
const updateItem = (items, id, value) => {
  setItems(items.map(item =>
    item.id === id ? { ...item, value } : item
  ));
};
```

---

## 📋 Bug Fix 계획 템플릿

### 버그 규모별 가이드

| 규모 | 시간 | 특징 |
|------|------|------|
| **Hotfix** | 1-2시간 | 명확한 원인, 단일 파일 수정 |
| **Standard** | 2-4시간 | 분석 필요, 여러 파일 관련 |
| **Complex** | 4-8시간 | 깊은 분석 필요, 시스템 영향 |

### 페이즈 구조 (버그 수정용)

```markdown
### Phase 1: 재현 & 분석
- [ ] 버그 재현
- [ ] 정보 수집
- [ ] 코드 분석
- [ ] 근본 원인 파악

### Phase 2: 테스트 & 수정
- [ ] 버그 캡처 테스트 작성 (FAIL)
- [ ] 최소 수정 적용
- [ ] 테스트 PASS 확인
- [ ] 기존 테스트 PASS 확인

### Phase 3: 검증 & 완료
- [ ] 수동 검증
- [ ] 유사 버그 검토
- [ ] 문서화
```

---

## ✋ Quality Gate (버그 수정용)

### 필수 검증 항목

**버그 해결 확인**:
- [ ] **버그 테스트 PASS**: 버그 캡처 테스트 통과
- [ ] **수동 확인**: 원래 증상 해결됨
- [ ] **재현 불가**: 동일 조건에서 버그 재현 안됨

**회귀 방지**:
- [ ] **기존 테스트 100% PASS**: 회귀 없음
- [ ] **관련 기능 테스트**: 부수효과 없음

**수정 품질**:
- [ ] **최소 변경**: 필요한 부분만 수정
- [ ] **명확한 수정**: 수정 의도가 명확함
- [ ] **린트/포맷 통과**: 코드 스타일 유지

---

## 🛠️ 검증 명령어

### Python/FastAPI (uv)
```bash
# 특정 버그 테스트
uv run pytest tests/test_bug_fix.py -v

# 전체 테스트
uv run pytest --cov=src

# 린트
uv run ruff check .

# 의존성 동기화
uv sync
```

### TypeScript/React
```bash
# 특정 버그 테스트
npm test -- --testPathPattern="bug-fix"

# 전체 테스트
npm test

# 린트
npm run lint
```

---

## ⚠️ 주의사항

### 피해야 할 안티패턴

| 안티패턴 | 위험 | 대안 |
|---------|------|------|
| 추측으로 수정 | 다른 버그 유발 | 재현 & 분석 먼저 |
| 테스트 없이 수정 | 회귀 버그 위험 | 테스트로 캡처 |
| 과도한 수정 | 새 버그 유발 | 최소 변경 |
| 증상만 수정 | 버그 재발 | 근본 원인 해결 |

### 수정 전 자문

- "이것이 정말 근본 원인인가?"
- "이 수정이 다른 곳에 영향을 주는가?"
- "더 간단한 수정 방법이 있는가?"
- "이 버그가 다른 곳에도 있을 수 있는가?"

---

## 📚 Supporting Files
- [plan-template.md](plan-template.md) - 버그 수정 계획 템플릿
