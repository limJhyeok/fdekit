# fdekit

Forward-deployed engineering skills: problem discovery → requirements alignment → build → handoff

현업 담당자와 함께 시간 제한이 있는 실무 과제를 수행할 때 쓰는 Agent Skill 모음이다.

| 순서 | Skill | 하는 일 | 산출물 |
|---|---|---|---|
| 1 | `problem-discovery` | 문제 설명·데이터·시작 코드를 분석하고 첫 문의 메시지 작성 | `problem-notes.md`, `partner-message.md` |
| 2 | `requirements-alignment` | 담당자 답변 반영, 후속 질문, 근거 있는 요구사항·범위 합의 | `requirements.md` |
| 3 | `build-from-requirements` | 확인 시나리오 → 명세 점검 → 설계 결정 → 구현·검증 → 제출 점검 | `ACCEPTANCE.md`, `DECISIONS.md` |
| 4 | `write-handoff` | 다음 개발자를 위한 인수인계 문서 정리 | `HANDOFF.md` |

## 설치

```bash
git clone https://github.com/limJhyeok/fdekit.git
# 프로젝트 단위
mkdir -p .claude/skills && cp -r fdekit/.agents/skills/* .claude/skills/
# 또는 사용자 전역
mkdir -p ~/.claude/skills && cp -r fdekit/.agents/skills/* ~/.claude/skills/
```

애플리케이션 코드나 보일러플레이트는 포함하지 않는다. 작업 절차·템플릿·점검 목록만 담는다.
