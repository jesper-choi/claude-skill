# Implementation Plan: [Feature Name]

**Status**: 🔄 In Progress
**Started**: YYYY-MM-DD
**Last Updated**: YYYY-MM-DD
**Estimated Completion**: YYYY-MM-DD

---

## ⚠️ CRITICAL: 바이브코딩 원칙

> **🧠 핵심 철학**: 추측하지 말고, 코드를 읽어라. 작성 즉시 검증하라.

### 필수 준수 사항
1. ✅ **코드베이스 우선**: 작업 전 관련 코드 전체 읽기
2. 🔍 **추측 금지**: 실제 코드를 읽고 판단, 가정하지 않음
3. ⚡ **즉각 검증**: 모든 코드 변경 후 빌드/테스트/린트 실행
4. 🎯 **단순함 우선**: 복잡한 해결책보다 단순한 해결책 선택
5. 🏗️ **Clean Architecture**: 레이어 분리, SOLID 원칙 준수

### 각 페이즈 완료 후 필수 작업
1. ✅ 완료된 태스크 체크박스 체크
2. 🧪 Quality Gate 검증 명령어 모두 실행
3. ⚠️ 모든 Quality Gate 항목 통과 확인
4. 📅 "Last Updated" 날짜 업데이트
5. 📝 Notes 섹션에 학습 내용 기록
6. ➡️ 모든 검증 통과 후에만 다음 페이즈 진행

⛔ **Quality Gate 실패 시 다음 페이즈 진행 금지**

---

## 📋 Overview

### Feature Description
[이 기능이 무엇이고 왜 필요한지]

### Success Criteria
- [ ] Criterion 1
- [ ] Criterion 2
- [ ] Criterion 3

### User Impact
[사용자에게 어떤 이점이 있는지]

---

## 🧠 코드베이스 분석 (작업 시작 전 필수)

### 분석한 파일 목록
| 파일 경로 | 분석 목적 | 주요 발견 |
|----------|----------|----------|
| `path/to/file1` | [목적] | [발견 사항] |
| `path/to/file2` | [목적] | [발견 사항] |

### 기존 아키텍처 패턴
- **레이어 구조**: [현재 사용 중인 레이어 패턴]
- **의존성 주입**: [DI 방식]
- **에러 처리**: [에러 처리 패턴]
- **테스트 구조**: [테스트 조직 방식]

### 영향 범위 분석
- **직접 영향**: [이 기능이 직접 수정하는 파일/모듈]
- **간접 영향**: [의존성으로 인해 영향받는 파일/모듈]
- **테스트 영향**: [수정이 필요한 테스트]

---

## 🏗️ Architecture Decisions

### Clean Architecture 준수 체크
- [ ] **레이어 분리**: Domain → Application → Infrastructure → Presentation
- [ ] **의존성 방향**: 외부 → 내부 (Infrastructure → Domain)
- [ ] **인터페이스 분리**: Repository 등 추상화 사용

### SOLID 원칙 체크
- [ ] **S** (Single Responsibility): 각 클래스/함수가 단일 책임
- [ ] **O** (Open/Closed): 확장에 열림, 수정에 닫힘
- [ ] **L** (Liskov Substitution): 하위 타입 대체 가능
- [ ] **I** (Interface Segregation): 작은 인터페이스
- [ ] **D** (Dependency Inversion): 추상화에 의존

### 주요 결정사항

| Decision | Rationale | Trade-offs |
|----------|-----------|------------|
| [결정 1] | [이유] | [트레이드오프] |
| [결정 2] | [이유] | [트레이드오프] |

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

### TDD 원칙
**반드시 테스트를 먼저 작성하고, 그 다음 구현한다.**

### Test Pyramid
| Test Type | Coverage Target | Purpose |
|-----------|-----------------|---------|
| **Unit Tests** | ≥80% | 비즈니스 로직, 모델, 핵심 알고리즘 |
| **Integration Tests** | Critical paths | 컴포넌트 상호작용, 데이터 흐름 |
| **E2E Tests** | Key user flows | 전체 시스템 동작 검증 |

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
**Goal**: [이 페이즈에서 구현하는 동작하는 기능]
**Estimated Time**: X시간
**Status**: ⏳ Pending | 🔄 In Progress | ✅ Complete

#### 📖 코드 분석 (구현 전 필수)
- [ ] 관련 기존 코드 읽기 완료
- [ ] 기존 패턴/컨벤션 파악 완료
- [ ] 영향 범위 확인 완료

읽은 파일:
- `path/to/file1`: [확인한 내용]
- `path/to/file2`: [확인한 내용]

#### 🔴 RED: 실패하는 테스트 작성
- [ ] **Test 1.1**: [specific functionality]에 대한 유닛 테스트
  - File: `tests/unit/[feature]/[component]_test.py`
  - Expected: 테스트 실패 (RED) - 기능이 아직 없음
  - 테스트 케이스:
    - Happy path
    - Edge cases
    - Error conditions

- [ ] **Test 1.2**: [component interaction]에 대한 통합 테스트
  - File: `tests/integration/[feature]_test.py`
  - Expected: 테스트 실패 (RED)

#### 🟢 GREEN: 테스트 통과를 위한 최소 구현
- [ ] **Task 1.3**: [component/module] 구현
  - File: `src/[layer]/[component].py`
  - Goal: Test 1.1 통과를 위한 최소 코드
  - 품질 체크:
    - [ ] 단순한가? (더 단순한 방법은 없는가?)
    - [ ] 명확한가? (이름이 설명적인가?)
    - [ ] 중복이 없는가?

- [ ] **Task 1.4**: [integration code] 구현
  - File: `src/[layer]/[integration].py`
  - Goal: Test 1.2 통과

#### 🔵 REFACTOR: 품질 개선 (테스트 유지)
- [ ] **Task 1.5**: 리팩토링
  - [ ] 중복 코드 제거 (DRY)
  - [ ] 네이밍 개선 (명확성)
  - [ ] 불필요한 복잡도 제거
  - [ ] 적절한 자료구조 사용
  - [ ] 인라인 문서화

#### ✋ Quality Gate

**⚠️ STOP: 모든 항목 통과 전 Phase 2 진행 금지**

**TDD 준수 (필수)**:
- [ ] **RED Phase**: 테스트가 먼저 작성되고 실패함
- [ ] **GREEN Phase**: 테스트 통과를 위한 코드 작성됨
- [ ] **REFACTOR Phase**: 테스트 유지하며 품질 개선됨
- [ ] **Coverage**: 목표 커버리지 달성

**빌드 & 테스트**:
- [ ] **빌드**: 에러 없이 빌드/컴파일
- [ ] **테스트 통과**: 모든 테스트 통과 (스킵 없음)
- [ ] **테스트 성능**: 적정 시간 내 완료

**코드 품질**:
- [ ] **린팅**: 에러/경고 없음
- [ ] **포매팅**: 프로젝트 표준 준수
- [ ] **타입 체크**: (해당시) 통과

**바이브코딩 체크**:
- [ ] **단순함**: 더 단순한 해결책이 없음
- [ ] **명확함**: 코드가 자기 설명적임
- [ ] **중복 없음**: DRY 원칙 준수
- [ ] **적절한 자료구조**: 성능 고려한 선택

**Clean Architecture 체크**:
- [ ] **레이어 분리**: 의존성 방향 올바름
- [ ] **SOLID 준수**: 위반 사항 없음

**Validation Commands** (프로젝트에 맞게 수정):
```bash
# Python/FastAPI (uv)
uv run pytest --cov=src --cov-report=term-missing
uv run ruff check .
uv run ruff format --check .
uv run mypy src/
uv sync  # 의존성 동기화

# TypeScript/React
npm test -- --coverage
npm run lint
npm run format:check
npx tsc --noEmit
npm run build
```

---

### Phase 2: [Core Feature Phase Name]
**Goal**: [구체적 결과물]
**Estimated Time**: X시간
**Status**: ⏳ Pending | 🔄 In Progress | ✅ Complete

#### 📖 코드 분석 (구현 전 필수)
- [ ] Phase 1 결과물 검토
- [ ] 추가 관련 코드 분석

#### 🔴 RED: 실패하는 테스트 작성
- [ ] **Test 2.1**: [functionality] 유닛 테스트
- [ ] **Test 2.2**: [interaction] 통합 테스트

#### 🟢 GREEN: 테스트 통과 구현
- [ ] **Task 2.3**: [component] 구현
- [ ] **Task 2.4**: [integration] 구현

#### 🔵 REFACTOR: 품질 개선
- [ ] **Task 2.5**: 리팩토링
  - [ ] 중복 제거
  - [ ] 네이밍 개선
  - [ ] 구조 최적화

#### ✋ Quality Gate
[Phase 1과 동일한 체크리스트]

---

### Phase 3: [Enhancement Phase Name]
**Goal**: [구체적 결과물]
**Estimated Time**: X시간
**Status**: ⏳ Pending | 🔄 In Progress | ✅ Complete

#### 📖 코드 분석 (구현 전 필수)
- [ ] 이전 Phase 결과물 검토
- [ ] 최종 통합 영향 분석

#### 🔴 RED / 🟢 GREEN / 🔵 REFACTOR
[이전 Phase와 동일한 구조]

#### ✋ Quality Gate
[Phase 1과 동일한 체크리스트]

---

## ⚠️ Risk Assessment

| Risk | Probability | Impact | Mitigation Strategy |
|------|-------------|--------|---------------------|
| 기존 코드와 충돌 | Low/Med/High | Low/Med/High | 영향 범위 사전 분석 |
| 성능 저하 | Low/Med/High | Low/Med/High | 벤치마크 테스트 |
| 테스트 부족 | Low/Med/High | Low/Med/High | 커버리지 목표 설정 |

---

## 🔄 Rollback Strategy

### If Phase 1 Fails
- 코드 변경 취소: [파일 목록]
- 설정 복원: [설정 항목]
- 의존성 제거: [추가된 의존성]

### If Phase 2 Fails
- Phase 1 완료 상태로 복원
- 변경 취소: [파일 목록]

### If Phase 3 Fails
- Phase 2 완료 상태로 복원
- [추가 정리 작업]

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
| Phase 1 | X시간 | Y시간 | +/- Z시간 |
| Phase 2 | X시간 | - | - |
| Phase 3 | X시간 | - | - |

---

## 📝 Notes & Learnings

### 코드베이스 인사이트
- [코드를 읽으며 발견한 중요 사항]
- [기존 패턴에서 배운 점]

### Implementation Notes
- [구현 중 발견한 인사이트]
- [원래 계획에서 변경된 결정]

### Blockers Encountered
- **Blocker 1**: [설명] → [해결 방법]

### Improvements for Future
- [다음에는 다르게 할 점]
- [특히 잘 작동한 점]

---

## 📚 References

### Documentation
- [관련 문서 링크]
- [API 레퍼런스]

### Related Issues
- Issue #X: [설명]
- PR #Y: [설명]

---

## ✅ Final Checklist

**완료 전 최종 확인**:
- [ ] 모든 페이즈 완료 및 Quality Gate 통과
- [ ] 전체 통합 테스트 수행
- [ ] 문서 업데이트
- [ ] 성능 벤치마크 목표 달성
- [ ] 보안 리뷰 완료
- [ ] Clean Architecture 준수 확인
- [ ] SOLID 원칙 준수 확인
- [ ] 코드 품질 기준 충족 (단순함, 명확함, 중복 없음)

---

## 📖 TDD 예시 워크플로우

### 예시: User Authentication Feature

**Phase 1: 🔴 RED**
```python
# tests/unit/domain/test_auth_service.py

def test_should_validate_user_credentials():
    # Arrange
    auth_service = AuthService(mock_user_repository)
    credentials = Credentials(username="user", password="pass")
    
    # Act
    result = auth_service.authenticate(credentials)
    
    # Assert
    assert result.is_success
    assert result.user is not None
    # TEST FAILS - AuthService doesn't exist yet
```

**Phase 2: 🟢 GREEN**
```python
# src/application/services/auth_service.py

class AuthService:
    def __init__(self, user_repository: UserRepository):
        self._user_repository = user_repository
    
    def authenticate(self, credentials: Credentials) -> AuthResult:
        # 최소 코드로 테스트 통과
        user = self._user_repository.find_by_username(credentials.username)
        if user and user.verify_password(credentials.password):
            return AuthResult.success(user)
        return AuthResult.failure("Invalid credentials")
        # TEST PASSES
```

**Phase 3: 🔵 REFACTOR**
```python
# 품질 개선 (테스트 유지)
class AuthService:
    def __init__(self, user_repository: UserRepository):
        self._user_repository = user_repository
    
    def authenticate(self, credentials: Credentials) -> AuthResult:
        # 입력 검증 추가
        if not self._validate_credentials(credentials):
            return AuthResult.failure("Invalid input")
        
        # 에러 핸들링 추가
        try:
            user = self._user_repository.find_by_username(credentials.username)
            if user and user.verify_password(credentials.password):
                return AuthResult.success(user)
            return AuthResult.failure("Invalid credentials")
        except RepositoryError as e:
            logger.error(f"Authentication failed: {e}")
            return AuthResult.failure("Authentication failed")
        # TESTS STILL PASS - 품질 개선됨
    
    def _validate_credentials(self, credentials: Credentials) -> bool:
        return bool(credentials.username and credentials.password)
```

### TDD 사이클 시각화

```
🔴 RED
├── 기능 X에 대한 테스트 작성
├── 테스트 실행 → FAILS ❌
└── Commit: "Add failing test for X"

🟢 GREEN
├── 최소 코드 작성
├── 테스트 실행 → PASSES ✅
└── Commit: "Implement X to pass tests"

🔵 REFACTOR
├── 코드 품질 개선
├── 테스트 실행 → STILL PASSES ✅
├── 중복 제거, 네이밍 개선
├── 테스트 실행 → STILL PASSES ✅
└── Commit: "Refactor X for better design"

다음 기능으로 반복 →
```

---

**Plan Status**: 🔄 In Progress
**Next Action**: [다음 작업]
**Blocked By**: [현재 블로커] or None