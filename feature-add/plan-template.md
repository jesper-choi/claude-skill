# Feature Implementation Plan: [Feature Name]

**Status**: 🔄 In Progress
**Started**: YYYY-MM-DD
**Last Updated**: YYYY-MM-DD
**Estimated Completion**: YYYY-MM-DD
**Feature Type**: 🆕 New Feature | 🔧 Enhancement | 🔄 Refactor

---

## ⚠️ CRITICAL: 기능 추가 원칙

> **🧠 핵심**: 기존 코드를 존중하라. 패턴을 따르라. 점진적으로 통합하라.

### 필수 준수 사항
1. 📖 **코드 분석 우선**: 유사 기능 코드 먼저 읽기
2. 🔄 **패턴 재사용**: 기존 패턴과 유틸리티 활용
3. 🧪 **TDD 엄수**: 테스트 먼저, 구현 나중
4. ✅ **회귀 방지**: 기존 테스트 100% 통과 유지
5. 🎯 **점진적 통합**: 작은 단위로 나누어 안전하게

### 각 페이즈 완료 후
1. ✅ 기존 테스트 모두 통과 확인
2. ✅ 새 테스트 모두 통과 확인
3. 🧪 Quality Gate 검증 실행
4. 📝 Notes에 학습 내용 기록
5. ➡️ 검증 완료 후에만 다음 페이즈

⛔ **기존 테스트 실패 시 절대 진행 금지**

---

## 📋 Overview

### Feature Description
[추가할 기능 설명]

### Why This Feature?
[이 기능이 필요한 이유]

### Success Criteria
- [ ] Criterion 1
- [ ] Criterion 2
- [ ] Criterion 3

### User Impact
[사용자에게 어떤 이점이 있는지]

---

## 🔍 코드베이스 분석 (작업 시작 전 필수)

### 유사 기능 분석
| 기존 기능 | 파일 경로 | 참고할 패턴 |
|----------|----------|------------|
| [기존 기능 1] | `path/to/file` | [이 기능에서 참고할 점] |
| [기존 기능 2] | `path/to/file` | [이 기능에서 참고할 점] |

### 재사용 가능한 코드
| 코드 | 파일 경로 | 용도 |
|------|----------|------|
| [유틸리티/헬퍼] | `path/to/file` | [어떻게 사용할지] |
| [기존 컴포넌트] | `path/to/file` | [어떻게 사용할지] |

### 기존 아키텍처 패턴
- **레이어 구조**: [현재 사용 중인 레이어]
- **의존성 주입**: [DI 패턴]
- **에러 처리**: [에러 처리 패턴]
- **테스트 구조**: [테스트 조직 방식]

### 영향 범위 분석
- **수정할 파일**: [직접 수정이 필요한 파일]
- **영향받는 파일**: [간접적으로 영향받는 파일]
- **테스트 영향**: [수정/추가가 필요한 테스트]

---

## 🏗️ Architecture Decisions

### Clean Architecture 적용
```
이 기능의 레이어 구조:

Presentation: [API/UI 컴포넌트]
     ↓
Application: [Use Cases/Services]
     ↓
Domain: [Entities/Interfaces]
     ↓
Infrastructure: [Repository 구현/외부 연동]
```

### SOLID 적용 계획
- [ ] **S**: 각 클래스/함수 단일 책임 부여
- [ ] **O**: 기존 코드 수정 대신 확장으로 구현
- [ ] **L**: 기존 인터페이스 계약 준수
- [ ] **I**: 필요한 인터페이스만 정의
- [ ] **D**: 추상화에 의존, 의존성 주입 사용

### 주요 설계 결정

| Decision | Rationale | 기존 패턴과의 관계 |
|----------|-----------|------------------|
| [결정 1] | [이유] | [기존 패턴 따름/확장] |
| [결정 2] | [이유] | [기존 패턴 따름/확장] |

---

## 📦 Dependencies

### 기존 코드 의존성
- [ ] `module/path`: [사용 목적]
- [ ] `module/path`: [사용 목적]

### 새로운 외부 의존성 (최소화)
- Package 1: version X.Y.Z - [필요 이유]

---

## 🧪 Test Strategy

### TDD 원칙
**테스트를 먼저 작성하고, 테스트가 통과하도록 구현한다.**

### 기존 테스트 패턴 따르기
```
기존 테스트 구조:
tests/
├── unit/
│   └── [기존 패턴 따름]
├── integration/
│   └── [기존 패턴 따름]
└── e2e/
    └── [기존 패턴 따름]
```

### 이 기능의 테스트 계획
| Test Type | 대상 | Coverage Target |
|-----------|------|-----------------|
| Unit | [비즈니스 로직] | ≥80% |
| Integration | [컴포넌트 통합] | Critical paths |
| E2E | [사용자 흐름] | Main flow |

---

## 🚀 Implementation Phases

### Phase 1: [Foundation - 기반 구조]
**Goal**: [이 페이즈에서 완성되는 동작 기능]
**Estimated Time**: X시간
**Status**: ⏳ Pending | 🔄 In Progress | ✅ Complete

#### 📖 코드 분석 (구현 전 필수)
- [ ] 유사 기능 코드 읽기 완료
- [ ] 재사용할 코드 식별 완료
- [ ] 기존 패턴 파악 완료

참고한 기존 코드:
- `path/to/similar/feature`: [참고한 패턴]
- `path/to/utility`: [재사용할 코드]

#### 🔴 RED: 실패하는 테스트 작성
- [ ] **Test 1.1**: [기능] 유닛 테스트
  - File: `tests/unit/[feature]/test_[component].py`
  - 기존 테스트 패턴 참고: `tests/unit/[similar]/test_*.py`
  - 테스트 케이스:
    - Happy path
    - Edge cases
    - Error conditions

- [ ] **Test 1.2**: [통합] 테스트
  - File: `tests/integration/test_[feature].py`

#### 🟢 GREEN: 테스트 통과 구현
- [ ] **Task 1.3**: [컴포넌트] 구현
  - File: `src/[layer]/[component].py`
  - 기존 패턴 따름: `src/[layer]/[similar].py`
  - 재사용: [기존 유틸리티/헬퍼]

- [ ] **Task 1.4**: [연결 코드] 구현
  - File: `src/[layer]/[integration].py`

#### 🔵 REFACTOR: 품질 개선
- [ ] **Task 1.5**: 리팩토링
  - [ ] 중복 코드 제거
  - [ ] 기존 코드와 일관성 확인
  - [ ] 네이밍 개선

#### ✋ Quality Gate

**⚠️ STOP: 모든 항목 통과 전 Phase 2 진행 금지**

**기존 코드 영향**:
- [ ] **기존 테스트 100% 통과**: 회귀 없음
- [ ] **기존 기능 동작 확인**: 수동 테스트

**TDD 준수**:
- [ ] **RED**: 테스트 먼저 작성, 실패 확인
- [ ] **GREEN**: 테스트 통과 최소 구현
- [ ] **REFACTOR**: 품질 개선, 테스트 유지

**일관성**:
- [ ] **패턴 준수**: 기존 아키텍처 패턴 따름
- [ ] **네이밍**: 기존 컨벤션 따름
- [ ] **스타일**: 린트/포맷 통과

**Validation Commands**:
```bash
# Python/FastAPI (uv)
uv run pytest  # 전체 테스트 (기존 + 신규)
uv run pytest --cov=src --cov-report=term-missing
uv run ruff check . && uv run ruff format --check .
uv run mypy src/
uv sync  # 의존성 동기화

# TypeScript/React
npm test  # 전체 테스트
npm run lint && npm run format:check
npx tsc --noEmit
npm run build
```

---

### Phase 2: [Core Logic - 핵심 로직]
**Goal**: [구체적 결과물]
**Estimated Time**: X시간
**Status**: ⏳ Pending | 🔄 In Progress | ✅ Complete

#### 📖 코드 분석
- [ ] Phase 1 결과물 검토
- [ ] 추가 참고 코드 분석

#### 🔴 RED / 🟢 GREEN / 🔵 REFACTOR
[Phase 1과 동일한 구조]

#### ✋ Quality Gate
[Phase 1과 동일한 체크리스트]

---

### Phase 3: [Integration - 통합]
**Goal**: [구체적 결과물]
**Estimated Time**: X시간
**Status**: ⏳ Pending | 🔄 In Progress | ✅ Complete

#### 📖 코드 분석
- [ ] 전체 통합 영향 분석
- [ ] E2E 시나리오 확인

#### 🔴 RED / 🟢 GREEN / 🔵 REFACTOR
[이전 Phase와 동일]

#### ✋ Quality Gate
[Phase 1과 동일 + 통합 테스트 추가]

---

## ⚠️ Risk Assessment

| Risk | Probability | Impact | Mitigation |
|------|-------------|--------|------------|
| 기존 기능 회귀 | Medium | High | 기존 테스트 100% 유지, 수동 테스트 |
| 패턴 불일치 | Low | Medium | 기존 코드 철저히 분석 |
| 성능 영향 | Low | Medium | 벤치마크 테스트 |
| 복잡도 증가 | Medium | Medium | 단순함 원칙, 리팩토링 |

---

## 🔄 Rollback Strategy

### If Phase 1 Fails
- [ ] 새 파일 삭제
- [ ] 기존 파일 변경 취소
- [ ] 의존성 제거

### If Phase 2/3 Fails
- [ ] 이전 Phase 상태로 복원
- [ ] 관련 변경 취소

---

## 📊 Progress Tracking

### Completion Status
- **Phase 1**: ⏳ 0% | 🔄 50% | ✅ 100%
- **Phase 2**: ⏳ 0% | 🔄 50% | ✅ 100%
- **Phase 3**: ⏳ 0% | 🔄 50% | ✅ 100%

### Time Tracking
| Phase | Estimated | Actual | Variance |
|-------|-----------|--------|----------|
| Phase 1 | X시간 | - | - |
| Phase 2 | X시간 | - | - |
| Phase 3 | X시간 | - | - |

---

## 📝 Notes & Learnings

### 기존 코드에서 배운 점
- [기존 패턴에서 배운 점]
- [재사용한 코드]

### Implementation Notes
- [구현 중 발견한 인사이트]
- [변경된 결정 사항]

### Blockers
- **Blocker 1**: [설명] → [해결]

---

## ✅ Final Checklist

**완료 전 최종 확인**:
- [ ] 모든 기존 테스트 통과
- [ ] 모든 새 테스트 통과
- [ ] 기존 기능 수동 테스트 완료
- [ ] 새 기능 수동 테스트 완료
- [ ] 성능 영향 없음 확인
- [ ] 기존 패턴과 일관성 확인
- [ ] 문서 업데이트

---

**Plan Status**: 🔄 In Progress
**Next Action**: [다음 작업]
**Blocked By**: [현재 블로커] or None
