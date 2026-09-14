# 인공지능활용세미나 1

숙명여자대학교 · 2026학년도 2학기
[The Missing Semester of Your CS Education](https://missing.csail.mit.edu/) 2026 개정판을 바탕으로,
**AI 코딩 도구를 실제로 써서 만들어 보는** 수업입니다.

이 페이지는 **"지금 어느 저장소로 가야 하는지"** 를 알려주는 안내판입니다.

---

## 🧭 지금 어디로 가야 하나요?

| 하려는 것 | 가야 할 곳 |
|---|---|
| 실습 환경 만들기 (Fork · Codespaces) | [**hands-on**](https://github.com/smwu-ai-seminar/hands-on) |
| 주차별 실습 따라 하기 | [**hands-on** → `docs/STUDENT-GUIDE.md`](https://github.com/smwu-ai-seminar/hands-on/blob/main/docs/STUDENT-GUIDE.md) |
| 강의계획서 확인 | [**hands-on** → `docs/syllabus-2026-fall.md`](https://github.com/smwu-ai-seminar/hands-on/blob/main/docs/syllabus-2026-fall.md) |
| 읽은 것 · 만든 것 정리해서 올리기 | [**wiki**](https://github.com/smwu-ai-seminar/wiki) |
| 다른 수강생이 정리한 내용 찾아보기 | [**wiki**](https://github.com/smwu-ai-seminar/wiki) 또는 조교 봇에게 질문 |
| 주제 하나로 출처 달린 리포트 뽑기 | [**GPT-Researcher**](https://github.com/smwu-ai-seminar/GPT-Researcher) |
| 조교 봇(MissingTA)이 어떻게 만들어졌는지 보기 | [**MissingTA**](https://github.com/smwu-ai-seminar/MissingTA) |

> **저장소를 눌렀는데 404가 뜨나요?**
> 아래 저장소는 모두 **비공개**입니다. 이메일로 받은 **조직 초대를 먼저 수락**해야 보입니다.
> 초대를 못 받았거나 만료됐다면 교수/조교에게 GitHub 아이디를 알려주세요.

---

## 📦 저장소 안내

### [hands-on](https://github.com/smwu-ai-seminar/hands-on) — 실습용 저장소
수업 실습은 전부 여기서 시작합니다.

1. 이 저장소를 **Fork** 해서 내 계정으로 복사합니다.
2. **내 Fork 저장소**에서 `Code` → `Codespaces` → `Create codespace on main`
   (원본이 아니라 **내 저장소**에서 만드세요.)
3. 최초 생성은 4분 정도 걸립니다. 도구를 설치하는 시간이라 정상입니다.
4. 작업한 내용은 **반드시 `git push`** 하세요. Codespace 안에만 있는 파일은 사라질 수 있습니다.

실습 환경에는 Coding Agent 두 가지가 미리 설치되어 있습니다.

| 도구 | 실행 명령 | 사용 시점 |
|---|---|---|
| OpenCode | `opencode` | 6~7주차 |
| Claude Code | `claude` | 9주차 이후 Product 개발 |

자세한 절차와 문제 해결은 [`docs/STUDENT-GUIDE.md`](https://github.com/smwu-ai-seminar/hands-on/blob/main/docs/STUDENT-GUIDE.md) 에 있습니다. **열어놓고 따라 하세요.**

### [wiki](https://github.com/smwu-ai-seminar/wiki) — 학생 공동 위키
읽은 것 · 만든 것 · 실험한 것을 한곳에 모으는 곳입니다.
목표는 Q&A 가 아니라 **공동 연구** — 서로의 작업을 조교 봇을 통해 찾을 수 있는 상태를 만드는 것입니다.

- 원본 자료는 `raw/` 에 넣고, LLM 코딩 도구가 규칙에 맞춰 `wiki/` 페이지를 만듭니다.
- **`main` 에 직접 push 하지 않습니다. 반드시 PR 로** — 리뷰가 1차 방어이자 8주차 코드 리뷰 실습입니다.
- 모든 페이지에 **작성자(GitHub handle)** 가 들어갑니다. 봇이 인용할 때 저자를 밝히기 위해서입니다.

기여 절차는 [`CONTRIBUTING.ko.md`](https://github.com/smwu-ai-seminar/wiki/blob/main/CONTRIBUTING.ko.md), 페이지 작성 규칙은 [`WIKI_SCHEMA.md`](https://github.com/smwu-ai-seminar/wiki/blob/main/WIKI_SCHEMA.md) 를 보세요.

> ⚠️ `raw/` 에 올린 원문은 자동 처리 봇이 **외부 API 로 전송**합니다.
> 원치 않는 파일은 frontmatter 에 `auto_ingest: false` 한 줄을 넣으면 건너뜁니다.

### [GPT-Researcher](https://github.com/smwu-ai-seminar/GPT-Researcher) — 리서치 도구
연구 주제를 한 줄 넣으면 알아서 웹을 뒤지고 **출처가 달린 리포트**를 써 주는 도구입니다.

```
주제 입력  →  검색  →  본문 수집  →  요약·정리  →  outputs/ 에 .md .pdf .docx
```

- 파이썬도 가상환경도 필요 없습니다. **Docker Desktop 하나만** 설치하면 됩니다.
- 저장소를 받고 `.env` 에 키를 채운 뒤 `docker compose up --build -d` → <http://localhost:8000>
- 리포트는 **한국어가 기본**이고, `my-docs/` 에 내 PDF·docx 를 넣으면 웹 대신 그 문서를 근거로 씁니다.
- 잘 안 되면 먼저 `docker compose exec gpt-researcher python tools/check_config.py` — 무엇이 틀렸는지 한국어로 알려줍니다.

설치 준비물부터 증상별 대처까지 [README](https://github.com/smwu-ai-seminar/GPT-Researcher/blob/main/README.md) 에 순서대로 정리되어 있습니다.

### [MissingTA](https://github.com/smwu-ai-seminar/MissingTA) — 수업 조교 봇
강의 자료와 공동 위키를 읽고 답하는 **AIN Teams 에이전트**의 소스 코드입니다.
평소 실습에서 직접 건드릴 일은 없지만, 봇이 어떻게 동작하는지 궁금하거나
비슷한 에이전트를 만들어 보고 싶을 때 참고하세요. 강의 슬라이드(`slides/`)도 여기 있습니다.

---

## ✅ 처음 오셨다면

- [ ] 조직 초대 수락 (이메일 확인)
- [ ] [GitHub Student Pack](https://education.github.com/pack) 등록 — 학교 이메일로 인증하면 Codespaces 무료 사용 시간이 크게 늘어납니다
- [ ] [hands-on](https://github.com/smwu-ai-seminar/hands-on) Fork 후 Codespace 생성
- [ ] [`docs/STUDENT-GUIDE.md`](https://github.com/smwu-ai-seminar/hands-on/blob/main/docs/STUDENT-GUIDE.md) 훑어보기

**Codespaces 할당량 아끼기**
15분 동안 입력이 없으면 자동으로 일시 중지됩니다. 실습이 끝나고 더 쓰지 않는 Codespace 는
[github.com/codespaces](https://github.com/codespaces) 에서 **삭제**해 주세요.

---

## 🆘 막혔을 때

1. 실습 환경이 이상하면 터미널에서 `bash .devcontainer/verify.sh` 를 실행하고,
   필수 항목에 ❌ 가 보이면 **그 화면을 교수/조교에게 보여주세요.**
2. 수업 내용 질문은 **조교 봇(MissingTA)** 에게 먼저 물어보세요.
3. 그래도 해결되지 않으면 해당 저장소에 **Issue** 를 남기거나 수업 시간에 질문해 주세요.
