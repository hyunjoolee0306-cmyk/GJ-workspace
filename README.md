# 골드제이의원 워크스페이스

블로그 서포터와 학회 PPT 스튜디오를 한 화면에서 쓰는 웹 앱입니다. 설치나 서버 없이 GitHub Pages(또는 내 컴퓨터)에서 바로 열립니다.

## 폴더 구성

```
goldj-workspace/
├─ index.html     ← 상단 로고·탭, 홈 "오늘의 작업대"
├─ logo.png       ← 왼쪽 위 로고
├─ favicon.png    ← 브라우저 탭 아이콘
├─ .nojekyll      ← GitHub Pages가 파일을 그대로 올리게 하는 빈 파일
├─ blog/          ← 블로그 서포터 (원본 그대로, 손대지 않음)
│   ├─ index.html
│   └─ assets/ (app.js, data.js, editor.js, styles.css, fonts/)
└─ ppt/
    └─ index.html ← 학회 PPT 스튜디오
```

탭을 누르면 각 폴더의 앱이 화면 안에 그대로 열립니다. 블로그 서포터는 원래 파일을 하나도 고치지 않고 씁니다.

## 처음 올리기 (GitHub Pages)

1. GitHub에서 **New repository**를 만듭니다 (예: `goldj-workspace`).
2. 저장소 화면에서 **Add file → Upload files**를 누르고, 이 폴더 안의 내용(`index.html`, `logo.png`, `favicon.png`, `blog` 폴더, `ppt` 폴더)을 통째로 끌어다 놓은 뒤 **Commit changes**.
   - `.nojekyll`은 숨김 파일이라 빠질 수 있습니다. 빠졌다면 **Add file → Create new file**에서 이름만 `.nojekyll`로 만들어 커밋하세요.
3. **Settings → Pages**에서 Source **Deploy from a branch**, Branch **main / (root)** → Save.
4. 1~2분 뒤 `https://<깃허브아이디>.github.io/goldj-workspace/` 로 열립니다.

## 블로그 서포터를 고쳤을 때 (업데이트 방법)

블로그 서포터 프로젝트에서 수정한 뒤, **`blog` 폴더만 덮어쓰면 끝**입니다.

1. 블로그 서포터 프로젝트에서 최신 `index.html`과 `assets` 폴더를 받습니다.
2. GitHub 저장소에서 `blog` 폴더로 들어가 **Add file → Upload files**.
3. `index.html`과 `assets` 폴더를 끌어다 놓고 **Commit changes**. 같은 이름의 파일은 새 파일로 바뀝니다.
4. 1~2분 뒤 새로고침하면 반영됩니다.

지켜야 할 것은 두 가지뿐입니다.
- 블로그 서포터의 첫 화면 파일은 `blog/index.html` 자리에 있어야 합니다.
- 홈 "오늘의 작업대"는 블로그 서포터가 브라우저에 저장하는 데이터(이름 `goldj-blog-supporter-v1`, 상태 6단계)를 읽어 요약합니다. 이 저장 이름이나 상태 이름을 바꾸면 블로그 서포터는 그대로 잘 돌아가지만 홈 요약만 비게 되니, 그때는 `index.html` 아래쪽 스크립트 맨 위의 설정 두 줄(`BLOG_KEY`, `BLOG_STATUSES`)만 맞춰 주세요.

학회 PPT 스튜디오를 고친 경우에는 `ppt/index.html` 한 파일만 바꾸면 됩니다.

## Claude 연결 (선택)

- 블로그 서포터 왼쪽 아래 **⚙︎ 설정 · Claude 연결**에서 Anthropic API 키를 넣으면, 같은 키를 **학회 PPT 스튜디오도 함께** 씁니다 (스토리라인 3안, 슬라이드 만들기, 슬라이드별 수정 요청).
- 키는 console.anthropic.com에서 만들고 쓴 만큼 요금이 나갑니다. 키는 그 브라우저에만 저장되고 저장소·백업 파일에는 들어가지 않습니다.
- 키가 없으면 블로그는 "프롬프트 복사", 학회 PPT는 기본 템플릿으로 동작합니다.

## 데이터 저장과 백업

- 작업 내용은 **그 브라우저**에 저장됩니다. 다른 PC·브라우저에서는 비어 있으니 백업 파일로 옮기세요.
  - 블로그: 왼쪽 아래 **데이터 백업 (JSON)** / **백업 불러오기**
  - 학회 PPT: 1단계 '내 프로젝트' 아래 **프로젝트 파일 저장** / **프로젝트 파일 불러오기**
- 브라우저 저장 공간은 보통 5MB 정도라 사진이 많은 PPT 프로젝트는 저장에 실패할 수 있습니다. 그럴 땐 프로젝트 파일로 저장해 두세요.
- 블로그 서포터를 덮어써 업데이트해도 저장된 데이터는 그대로 남습니다 (데이터는 파일이 아니라 브라우저에 있음).

## 공개 범위 주의

무료 계정에서 GitHub Pages를 쓰려면 저장소가 **공개(Public)**여야 하고, 주소를 아는 사람은 누구나 열 수 있습니다. `blog/assets/data.js`에는 예시 원고·스타일 프로필·발행 계획이 들어 있습니다. 외부에 보이면 안 된다면 비공개 저장소(유료 플랜은 비공개 Pages 가능)를 쓰거나, 폴더를 내 컴퓨터에 두고 `index.html`을 더블클릭해서 쓰세요. 내 컴퓨터에서 열 때는 브라우저 보안 설정에 따라 홈의 일부 바로가기(새 글 추가, 특정 발표 바로 열기)가 탭만 여는 것으로 동작할 수 있습니다.

## 인터넷에서 받아 오는 도구

- PPTX 내보내기·PPT 폼 불러오기: pptxgenjs, JSZip (cdn.jsdelivr.net)
- 블로그 PDF 자료: 블로그 서포터 원본 방식(Claude API에 PDF 첨부)
- 영문 글꼴: Google Fonts (Titillium Web, Inter) · 한글 글꼴: Pretendard (blog/assets/fonts, SIL OFL 1.1)
