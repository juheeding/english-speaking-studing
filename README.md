# 무료 AI로 만드는 영어 공부 웹사이트

무료 ChatGPT 또는 Claude로 노트를 정리하고, GitHub 웹 화면에 붙여 넣어 학습 사이트를 운영하는 템플릿입니다. 터미널, 로컬 Git, Node.js, 유료 AI, API 키가 필요하지 않습니다. AI가 정리한 내용을 사람이 확인하고 저장하면 GitHub Pages가 웹페이지로 바꿉니다.

샘플은 모두 이 템플릿을 위해 새로 작성한 가상 자료입니다. 원본 저장소의 수업 내용, 회원 정보, 음성, 외부 서비스 링크, Git 이력은 포함하지 않았습니다.

## 1. 시작 전에 알아두기

- GitHub Free에서 이 방법을 사용하려면 **새 공개 저장소**를 만듭니다. 공개 저장소 파일과 사이트는 누구나 볼 수 있습니다.
- 기존 개인 학습 저장소를 공개 전환하거나 그대로 복제하지 마세요. 삭제한 파일도 Git 이력에 남을 수 있습니다. 이 템플릿 폴더만 새 저장소에 올리는 것을 권장합니다.
- 실명, 이메일, 전화번호, 주소, 실제 일정, 회원 사진·녹음은 올리지 마세요. AI에 전달하기 전에도 가명이나 일반적인 예시로 바꾸세요.
- 직접 작성한 노트와 공개 가능한 짧은 예문을 사용하세요. 교재 전체, 수업 녹음, 타인의 글을 허락 없이 공개하지 마세요.
- 웹사이트에 로그인·비공개 일기·녹음 제출 기능은 없습니다. 개인 기록은 별도로 보관하세요.

## 2. 새 저장소에 템플릿 넣기 — 웹 화면만 사용

### 처음 배포하는 운영자

1. GitHub에 로그인하고 오른쪽 위 **+ → New repository**를 누릅니다.
2. Repository name을 **english-study**로 입력합니다. Public을 선택하고 README 초기화 옵션을 켠 뒤 **Create repository**를 누릅니다. 다른 이름을 써도 되지만 3단계 설정을 함께 바꿔야 합니다.
3. 전달받은 ZIP을 컴퓨터에서 압축 해제합니다. 폴더에 `README.md`, `docs`, `templates`가 있는지 확인합니다.
4. GitHub 저장소의 **Code → Add file → Upload files**에서 **템플릿 폴더 안의 내용**을 올립니다. `english-study-template`라는 바깥 폴더 자체를 올리면 안 됩니다. `docs` 폴더를 통째로 끌어 넣어 하위 폴더를 유지하세요. 기본 README와 겹치면 템플릿 README로 교체합니다.
5. **Commit changes**에 `Add study website template`라고 적고 기본 브랜치 `main`에 저장합니다. Commit은 변경을 저장하고 이력을 남긴다는 뜻입니다.
6. 저장소 맨 위에 `docs/_config.yml`, `docs/index.md`, `docs/_layouts/default.html`, `docs/assets/style.css`, `templates/lesson.md`가 올바른 경로에 있는지 확인합니다. 파일명 앞의 밑줄을 지우지 마세요.

`.gitignore`는 선택 사항이며, 웹사이트에 필수인 숨김 파일은 없습니다. ZIP 전체 파일 하나를 업로드하면 GitHub가 압축을 풀어주지 않으므로 사이트가 만들어지지 않습니다.

### 공개 템플릿 저장소가 준비된 뒤 회원이 복사하는 방법

운영자가 별도 저장소에 위 파일을 게시한 뒤 **Settings → General → Template repository**를 켤 수 있습니다. 회원은 **Use this template → Create a new repository**로 자기 계정에 새 공개 저장소를 만듭니다. 이름은 `english-study`를 권장합니다. 템플릿의 Pages 설정은 복사되지 않으므로 아래 설정을 각자 해야 합니다. 지금 제공된 것은 로컬 파일이며, 사용할 공개 템플릿 저장소 주소는 아직 없습니다.

## 3. 사이트 이름과 주소 설정

GitHub에서 `docs/_config.yml`을 열고 연필 모양 **Edit this file**을 누릅니다.

```yaml
title: "나의 영어 공부 노트"
description: "조금씩 배우고, 내 말로 연습하는 영어"
lang: ko
baseurl: "/english-study"
```

`title`과 `description`을 원하는 문구로 바꾸고 아래의 다른 설정은 유지합니다. `baseurl`은 **슬래시 + 저장소 이름**입니다. 이름이 `my-english`라면 `"/my-english"`로 바꿉니다. 끝에 슬래시를 더하지 마세요. 저장소 이름이 특별히 `USERNAME.github.io`인 사용자 사이트라면 `baseurl: ""`를 사용합니다. 계정 이름은 본인의 GitHub 사용자 이름입니다.

**Commit changes**를 눌러 저장합니다. 홈 제목은 `docs/index.md`의 `# 나의 영어 공부 노트`도 함께 바꾸면 됩니다.

## 4. GitHub Pages 켜기

1. 저장소에서 **Settings → Pages**를 엽니다. 저장소 관리자 권한이 필요합니다.
2. **Build and deployment → Source → Deploy from a branch**를 선택합니다.
3. Branch는 **main**, 폴더는 **/docs**로 선택하고 **Save**를 누릅니다. 기본 브랜치 이름이 다르면 실제 이름을 선택합니다.
4. **Actions** 탭에서 Pages 빌드와 배포 작업이 초록색으로 끝나는지 확인합니다. 직접 작성한 workflow 파일은 필요하지 않습니다.
5. 다시 **Settings → Pages → Visit site**로 접속합니다. 첫 배포는 몇 분 걸릴 수 있습니다. 사이트 주소는 보통 `https://USERNAME.github.io/english-study/`입니다. 이 예시 주소를 그대로 쓰지 말고 Pages 화면의 실제 주소를 사용하세요.
6. 홈 → 수업 기록 → 샘플 → 수업 목록으로 이동해 보고, 휴대폰에서도 글이 읽히는지 확인합니다.

이 템플릿은 Markdown을 HTML로 바꾸는 GitHub Pages 기본 Jekyll 빌드를 사용합니다. **GitHub Actions를 Source로 선택하거나 `.nojekyll` 파일을 추가하지 마세요.** 둘 다 기존 VitePress 방식과 혼동하기 쉬운 부분입니다.

## 5. 매번 수업 기록 추가하기

1. `templates/lesson.md`를 열고 **Code/Raw**에서 내용을 복사합니다. 웹 화면에 렌더링된 글이 아니라 맨 위 `---`까지 있는 원문을 복사합니다.
2. 무료 ChatGPT 또는 Claude에 7단계 프롬프트와 익명화한 학습 메모를 붙여 넣습니다.
3. 영어 뜻·문법과 개인 정보 포함 여부를 확인합니다. AI 답을 그대로 신뢰하지 말고 애매한 표현은 선생님이나 사전으로 확인합니다.
4. 저장소 **Code → Add file → Create new file**에서 파일명을 `docs/lessons/2026-10-15-cafe.md`처럼 입력합니다. 날짜·주제는 실제 기록에 맞게 바꾸세요. 소문자 영어·숫자·하이픈을 권장합니다.
5. AI가 만든 Markdown을 붙여 넣습니다. 바깥쪽의 ` ```markdown `과 마지막 ` ``` `는 제외합니다. 맨 위는 반드시 아래처럼 유지합니다.

```markdown
---
title: "2026-10-15 · 카페 주문"
---
# 카페 주문

## 오늘의 표현

- **I'd like some tea.** 차를 원합니다.
```

6. **Commit changes**를 눌러 저장합니다.
7. `docs/lessons/index.md`를 편집하고 아래 줄을 목록에 추가합니다. 파일 이름과 `.html`을 정확히 맞춥니다. `.md` 원본은 배포할 때 `.html` 페이지가 됩니다.

```liquid
- [10월 15일 · 카페 주문]({{ '/lessons/2026-10-15-cafe.html' | relative_url }})
```

8. 목록 변경도 **Commit changes**로 저장합니다. Actions 배포 완료 후 사이트에서 새 링크를 누릅니다. 새 파일만 만들면 수업 목록에는 자동으로 추가되지 않습니다.

표현집은 `docs/vocabulary/index.md`, 복습은 `docs/review/index.md`를 같은 방식으로 편집합니다. 메뉴 설정이나 프로그램 코드를 매번 수정할 필요는 없습니다.

## 6. Markdown 최소 문법과 수정 취소

```markdown
# 큰 제목
## 작은 제목

**중요한 표현**

- 첫 번째 항목
- 두 번째 항목

**A:** Hello!

**B:** Hi!

- [ ] 아직 연습하지 않음
- [x] 연습 완료
```

문단 사이에는 빈 줄을 넣습니다. 체크 상태는 파일에서 `[ ]`와 `[x]`를 바꾸어 저장하세요. 사이트 방문자가 클릭해도 학습 기록이 저장되는 기능은 없습니다.

실수했다면 해당 파일의 **History**에서 이전 버전을 열어 원문을 복사하고, 현재 파일 편집 화면에 붙여 넣어 새 Commit으로 복구하세요. 공동 저장소에서는 회원에게 **Settings → Collaborators**로 권한을 주거나 변경 제안을 Pull request로 받습니다. 서로 다른 파일을 편집하면 충돌을 줄일 수 있습니다. 여러 회원의 이름은 가명을 권장합니다.

## 7. 무료 ChatGPT / Claude에 붙여 넣을 프롬프트

### 수업 정리

```text
너는 영어회화 학습 노트를 정리하는 도우미야.
아래 메모를 초급~중급 학습자가 복습하기 좋은 한국어 Markdown으로 정리해 줘.
내가 붙인 템플릿의 front matter(맨 위 ---와 title)를 유지해 줘.
오늘의 표현 3~5개(뜻과 상황), 짧은 대화, 내 문장 만들기,
말하기 질문 2개와 예시 답변, 복습 체크를 포함해 줘.
원문에서 가져온 내용과 새로 만든 예문을 구분해 줘.
불확실한 설명은 확인 필요라고 표시하고, 출처를 지어내지 마.
실명·연락처·주소·회사명·개인 일정은 빼고, 교재 원문을 길게 복제하지 마.
스크립트·HTML·외부 이미지·추적 링크 없이 Markdown만 출력해 줘.
GitHub Pages에 복사할 파일 내용만 출력하고 바깥 코드 울타리는 쓰지 마.

날짜와 주제: [직접 입력]
템플릿: [templates/lesson.md 원문 붙여 넣기]
학습 메모: [개인 정보를 제거한 메모 붙여 넣기]
```

### 영작 교정

```text
다음 영어 문장을 교정해 줘. 각 항목을 원문 → 교정문 → 한국어 이유 순으로 써 줘.
의미를 유지하고 B1 수준의 자연스러운 표현을 사용해 줘.
문법 오류와 단순한 스타일 개선을 구분해 줘.
여러 뜻으로 해석되면 추측하지 말고 확인 질문을 해 줘.
개인 정보를 빼고 Markdown만 출력해 줘.
문장: [익명화한 내 문장]
```

### 복습 만들기

```text
아래 공개 학습 노트만 사용해 말하기 질문 5개와 짧은 예시 답변을 만들어 줘.
질문 부분과 답변 부분을 나눠 Markdown으로 써 줘.
새로 만든 예시 답변임을 표시하고, 제공하지 않은 수업 내용을 지어내지 마.
노트: [이번 주 노트 붙여 넣기]
```

## 8. 자주 발생하는 오류

- **사이트 전체가 404:** Pages 설정의 브랜치와 `/docs`를 확인합니다. `docs/index.md`가 있어야 합니다. Actions가 실패했으면 작업을 열고 실패한 단계의 오류를 확인합니다.
- **글은 보이지만 디자인·메뉴가 깨짐:** `_config.yml`의 `baseurl`이 실제 저장소 이름과 같은지, `_layouts/default.html`과 `assets/style.css`가 `docs` 안에 있는지 확인합니다. 저장소 이름 변경 후에도 baseurl을 바꿔야 합니다.
- **새 노트만 404:** 목록 링크의 날짜·대소문자·하이픈이 원본 파일과 같은지 확인합니다. 링크는 `/lessons/파일이름.html` 형식이고 `relative_url`을 유지합니다.
- **새 글이 목록에 없음:** `docs/lessons/index.md`에도 링크를 직접 추가해야 합니다.
- **내용이 코드처럼 보임:** AI 출력 전체를 감싼 코드 울타리를 지웁니다. 작은 문법 예시 안의 울타리는 그대로 둡니다.
- **제목 설정이나 빌드 오류:** 맨 위 `---` 두 줄, `title: "제목"` 형식을 확인합니다. YAML에는 탭 대신 공백을 사용하세요. 제목에 큰따옴표가 들어가면 빼거나 작은따옴표로 바꾸세요.
- **`{{ ... }}`가 글자 그대로 보임:** `.nojekyll`을 제거하고 Source를 Deploy from a branch로 설정합니다. front matter도 확인합니다.
- **Commit 했는데 이전 글이 보임:** Actions에서 최근 배포가 끝났는지 확인한 뒤 새로고침합니다. 캐시가 남으면 시크릿 창에서 접속합니다.
- **Pages 메뉴/편집 버튼이 없음:** 저장소 관리자 권한과 로그인 계정을 확인합니다. 무료 계정의 비공개 저장소는 이 공개 Pages 방식과 조건이 다릅니다.
- **AI 제한 안내가 나옴:** 입력을 한 수업 단위로 줄이고 화면에 표시된 재사용 가능 시간을 기다립니다. 복사해 둔 기존 템플릿을 직접 채워도 됩니다. 다른 대화를 만든다고 계정 제한이 없어지지는 않습니다.

## 9. 무료 사용의 범위와 제한

확인 기준: **2026-10-14**. 요금·모델·제한과 화면 이름은 변경될 수 있습니다.

- 이 절차는 AI의 일반 텍스트 답변을 복사하는 방식입니다. 유료 자동화, 로컬 파일 수정, GitHub 연동 또는 자동 push 권한이 필요하지 않습니다. 무료 ChatGPT/Claude의 기능과 이용 가능량은 계정과 상황에 따라 달라집니다. 현재 앱의 제한 안내를 기준으로 사용하세요.
- ChatGPT는 기능·플랜·플랫폼·지역·출시 상황에 따라 이용 조건이 달라집니다. 파일·이미지·긴 대화에 의존하지 않고 짧은 메모를 나눠 정리하면 이 절차를 유지하기 쉽습니다. 무료로 무제한 자동 작업이 된다는 뜻은 아닙니다. [OpenAI 공식 사용 안내](https://learn.chatgpt.com/docs/use-chatgpt), [플랜·사용 제한 안내](https://learn.chatgpt.com/docs/pricing).
- Claude 무료 플랜에는 사용량 제한이 있으며 공식 시작 안내는 5시간마다 재설정되는 세션 제한을 설명합니다. 메시지 가능량은 입력 길이와 수요 등에 따라 달라집니다. [Claude 공식 시작 안내](https://support.claude.com/en/articles/8114491-get-started-with-claude).
- GitHub Free의 공개 저장소에서 Pages를 사용할 수 있습니다. 기본 `github.io` 주소로 시작하면 도메인을 구입할 필요가 없습니다. Pages는 정적 사이트이며 서버 프로그램·데이터베이스·로그인 기능을 제공하는 방식이 아닙니다. [GitHub Pages 게시 설정](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site).
- Pages의 게시 사이트 크기 제한은 1GB이며, 월 100GB 대역폭과 시간당 10회 빌드의 소프트 제한이 있습니다. 사용자 지정 Actions 빌드에는 일부 조건이 다르므로 공식 문서를 확인하세요. 짧은 Markdown 중심으로 운영하고 큰 녹음·영상을 저장소에 쌓지 않는 것을 권장합니다. [GitHub Pages 제한](https://docs.github.com/en/pages/getting-started-with-github-pages/github-pages-limits).

## 10. 템플릿 파일 구성

```text
README.md                 이 설명서 (사이트 밖, 저장소에서 읽기)
docs/
  _config.yml             제목·주소 설정
  _layouts/default.html   공통 메뉴·페이지 틀
  assets/style.css        모바일 대응 디자인
  index.md                홈
  lessons/index.md        수업 목록
  lessons/sample-cafe.md  새로 작성한 가상 예시
  vocabulary/index.md     표현집
  review/index.md         복습
templates/lesson.md       복사용 빈 양식 (사이트 밖)
```

템플릿 코드는 자유롭게 복사·수정하여 개인 또는 스터디 학습 사이트에 사용할 수 있습니다. 이후 추가하는 자료의 공개 권한은 작성자가 확인하세요.
