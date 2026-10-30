# fdekit

Forward-deployed engineering skills: problem discovery → requirements alignment → build → handoff

현업 담당자와 함께 시간 제한이 있는 실무 과제를 수행할 때 쓰는 Agent Skill 모음이다.

| 순서 | Skill | 하는 일 | 산출물 |
|---|---|---|---|
| 1 | `problem-discovery` | 문제 설명·데이터·시작 코드를 분석하고 첫 문의 메시지 작성 | `problem-notes.md`, `partner-message.md` |
| 2 | `requirements-alignment` | 담당자 답변 반영, 후속 질문, 근거 있는 요구사항·범위 합의 | `requirements.md` |
| 3 | `build-from-requirements` | 확인 시나리오 → 명세 점검 → 설계 결정 → 구현·검증 → 제출 점검 | `ACCEPTANCE.md`, `DECISIONS.md` |
| 4 | `write-handoff` | 다음 개발자를 위한 인수인계 문서 정리 | `HANDOFF.md` |
| 5 | `quiz` | 구현한 코드를 스스로 설명하는 리허설 | 저장소 밖의 `~/study/<저장소 이름>/` 기록 |

`playwright`는 웹 화면을 브라우저에서 확인할 때 쓰는 선택 스킬이다. 사용 시 Node.js/npm의 `npx`가 필요하다.

## Codex에서 프로젝트별 설치

스킬을 사용할 **대상 프로젝트**의 `.agents/skills/`에 복사하고, 그 프로젝트에서 Codex를 실행한다. `fdekit`만 별도로 clone한 상태에서는 다른 프로젝트에서 스킬이 검색되지 않는다.

```bash
cd /path/to/workspace  # 대상 프로젝트의 상위 디렉터리
git clone https://github.com/limJhyeok/fdekit.git
cd target-project
mkdir -p .agents/skills
cp -R ../fdekit/.agents/skills/. .agents/skills/
codex
```

이미 같은 이름의 스킬이 있다면 덮어쓰기 전에 내용을 확인한다. 업데이트할 때는 복사를 다시 하고 `git diff`로 변경 내용을 검토한다. 웹 화면 검증이 필요 없다면 `playwright` 폴더는 복사하지 않아도 된다.

## Claude Code에서 프로젝트별 설치

```bash
cd /path/to/target-project
mkdir -p .claude/skills
for skill in problem-discovery requirements-alignment build-from-requirements write-handoff quiz; do
  cp -R /path/to/fdekit/.agents/skills/"$skill" .claude/skills/
done
```

현재 저장소에는 Codex 플러그인 매니페스트와 마켓플레이스 파일이 없다. 플러그인 배포에는 별도 패키징이 필요하다.

애플리케이션 코드나 보일러플레이트는 포함하지 않는다. 작업 절차·템플릿·점검 목록만 담는다.
