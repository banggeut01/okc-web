# AI-DLC State Tracking

## Project Information
- **Project Name**: okc-web (Obsidian Vault Integration Web Platform)
- **Project Type**: Greenfield
- **Start Date**: 2026-09-08T02:02:15Z
- **Current Phase**: INCEPTION
- **Current Stage**: **Workflow Planning APPROVED** (Option B, 2026-09-08) → **Application Design IN PROGRESS** (comprehensive). Plan generated via 3-lens panel. 3-lens 패널(demo-velocity / judging-criteria / engineering-correctness) 조정 → `inception/plans/execution-plan.md` 작성(Mermaid validated + text-alt). 결정: Application Design(comp.) + Units Generation(std.) EXECUTE; Functional Design selective(U3/U4 comp · U1/U2 std · U5/U6 skip); NFR Requirements(min.) · NFR Design(std.) · Infrastructure Design(min.) EXECUTE; Code Generation(comp.) + Build and Test(std., 하드-MUST screenshots/·CI·lockfile·README·PROCESS narrative 예약) EXECUTE; Operations SKIP. 유닛 7개(U0 어댑터/큐 → U1 Auth → U2 Upload → U3 Orchestration → U4 Review[E4 wow] → U5 Serving[E5 wow], U6 Frontend 인터리브). Risk=High. (직전: personas.md 3종 + stories.md 29 stories/5 epics; coverage_ok=true; consistency-audit passed.) Application Design UI-screens deliverable **LANDED** (application-design/ui-screens.md 43KB + design-system.md 22KB written; critique coverage_ok=true; user-directed early start — formal Application Design gate still pending, after Workflow Planning). Hackathon judging-criteria gate doc created (hackathon-judging-criteria.md). **req-③ RESOLVED** — user confirmed **경우 B** (관리자 '선택' = 결정 행동 {승인 as-is / regenerate / omission / minor waive} → core 전달 → core가 이후 처리; **승자 선택 아님**; **okc-core 무수정**; 모순은 불변·hash-bound로 보존 → C3 차별성 유지). Code-verified wf_91476e22-fe1 (PARTIAL: no mutable conflict flag; IntegrationCheckpoint 7-variant derived state + critic gate; contradictions immutable hash-bound data). ③ scrutiny thread CLOSED; consistency-audit PASSED (wf_4b277935-b79, coverage_ok=true across 8 artifacts; 2 patches applied) + Decision Record created (inception/requirements/decision-records.md).

## Project Context (non-derivable)
- **Hackathon project** — goal is **placement/winning**. Demo quality matters: the web UI must be **clean and easy to read**. UI direction: clean/minimal with a few strategic focal "wow" screens (conflict/critic review, provenance/verify). Carry into Application Design / NFR / Code Generation.
- **Hackathon judging criteria (MANDATORY per-stage gate)** — ref: https://main.d3gkmtkue9o7ly.amplifyapp.com/ and `aidlc-docs/hackathon-judging-criteria.md`. Scoring: **AI 심사 40%** (인간 gating 보정 가능) + **인간 투표 60%** (전시 페이지 투표). AI 심사 = 6항목/100점:
  1. **AI 협업 진정성** — 단계별 산출물이 서로 이어지고 앞 단계 결정이 뒤에 반영되는가 (문서 양·도구 종류 무관). ← AI-DLC 추적성이 직접 득점.
  2. **문제 정의** — 누구의/어떤 문제를/어떻게 푸는지가 독자에게 그대로 전달; 시점·빈도·대상 사용자 구체성이 높을수록 가점 (아이디어 크기·시장성 제외).
  3. **차별성** — 기존 도구 대비 **구조적** 차별점이 코드/설계 문서로 확인 (주장만으론 0점).
  4. **실제 동작·구현 완성도** — 코드로 실제 동작 + **screenshots/ 또는 result/ 시연 스크린샷 필수**; 빌드·진입점·락파일·CI, 에러/전역 핸들러, 진입점→실제 구현 완결, 스크린샷↔README 정합, 핵심 경로 스텁/TODO 없음.
  5. **온보딩·사용성** — 처음 보는 사람이 막힘없이 시작·다음 행동 인지; 화면 자체가 사용법 설명; 시작 경로·매뉴얼·UI 직관성·인터랙션 피드백(로딩/성공/오류/빈 화면)·핵심 시나리오 end-to-end 완결.
  6. **유지보수성** — 코드 구조·모듈화·설정 분리, 시크릿 비하드코딩, 인증·인가·입력 검증, 로깅·관측 (해커톤 감안, 프로덕션 수준까진 불요).
  → **각 스테이지 완료 게이트에서 위 6기준의 해당 항목 충족 여부를 점검하고 완료 메시지에 요약한다.**

## Workspace State
- **Existing Code**: No (greenfield — only AI-DLC install artifacts present)
- **Programming Languages**: None yet (to be determined during NFR/tech-stack selection)
- **Build System**: None yet
- **Project Structure**: Empty (greenfield)
- **Reverse Engineering Needed**: No (okc-web itself has no code; okc-core is a separate dependency repo)
- **Workspace Root**: c:/Users/genie/workplace/okc-web

## Key Dependency
- **okc-core** (`c:/Users/genie/workplace/okc-core`) — OKC (Obsidian Knowledge Compilation), Rust workspace v0.3.0. Provides the vault compilation/integration engine, integration records, critic/curator approval, provenance, okc-app services, and Python + Node bindings. okc-web is built ON TOP of okc-core.
- **okc-mcp** — currently UNIMPLEMENTED. Intended MCP that builds a local Obsidian vault and serves it as a RAG source. In scope for okc-web only as an integration target (URL/API), pending clarification.

## Code Location Rules
- **Application Code**: Workspace root (NEVER in aidlc-docs/)
- **Documentation**: aidlc-docs/ only
- **Structure patterns**: See code-generation.md Critical Rules

## Extension Configuration
| Extension | Enabled | Decided At |
|---|---|---|
| Security Baseline | No (Q11=B) | Requirements Analysis |
| Resiliency Baseline | No (Q12=B) | Requirements Analysis |
| Property-Based Testing | No (Q13=C) | Requirements Analysis |

_All extensions opted OUT (hackathon PoC scope) → full rule files NOT loaded. Basic upload validation still applied as ordinary requirements, not as enforced extension rules._

## Stage Progress

### 🔵 INCEPTION Phase
- [x] Workspace Detection — COMPLETED
- [ ] Reverse Engineering (N/A — greenfield)
- [x] Requirements Analysis — COMPLETED (standard/comprehensive)
- [x] User Stories — COMPLETED (29 stories / 5 epics; **APPROVED 2026-09-08, Option B**)
- [x] Workflow Planning — COMPLETED (execution-plan.md; **APPROVED 2026-09-08, Option B**)
- [~] Application Design — IN PROGRESS (comprehensive) (현재 단계)
- [ ] Units Generation — EXECUTE (standard)

### 🟢 CONSTRUCTION Phase (per-unit loop: U0→U1→U2→U3→U4→U5, U6 interleaved)
- [ ] Functional Design — EXECUTE (selective: U3/U4 comprehensive · U1/U2 standard · U5/U6 skip)
- [ ] NFR Requirements — EXECUTE (minimal)
- [ ] NFR Design — EXECUTE (standard)
- [ ] Infrastructure Design — EXECUTE (minimal)
- [ ] Code Generation — EXECUTE (comprehensive) — ALWAYS, per-unit
- [ ] Build and Test — EXECUTE (standard; 하드-MUST exit artifacts: screenshots/·CI·lockfile·README·PROCESS narrative·secret scan)

### 🟡 OPERATIONS Phase
- [ ] Operations — SKIP (placeholder; 로컬 단일 프로세스 PoC, 범위 밖)
