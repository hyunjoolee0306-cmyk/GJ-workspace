# 골드제이의원 워크스페이스

블로그 서포터와 학회 PPT 스튜디오를 한 화면에서 쓰는 웹 앱입니다. 설치나 서버 없이 `index.html` 하나로 돌아갑니다.

## 폴더 구성

| 파일 | 설명 |
|---|---|
| `index.html` | 앱 전체 (화면·기능·예시 데이터가 모두 들어 있음) |
| `logo.png` | 왼쪽 위 골드제이의원 로고 |
| `favicon.png` | 브라우저 탭 아이콘 |
| `fonts/PretendardVariable.woff2` | Pretendard 글꼴 (SIL OFL 1.1) |
| `.nojekyll` | GitHub Pages가 파일을 그대로 올리도록 하는 빈 파일 |

## GitHub Pages로 올리기

1. GitHub에서 **New repository**를 만듭니다. 이름은 예를 들어 `goldj-workspace`로 합니다.
2. 저장소 화면에서 **Add file → Upload files**를 누르고, 이 폴더 안의 파일과 `fonts` 폴더를 통째로 끌어다 놓은 뒤 **Commit changes**를 누릅니다.
   - `.nojekyll`은 숨김 파일이라 끌어다 놓을 때 빠질 수 있습니다. 빠졌다면 **Add file → Create new file**로 이름만 `.nojekyll`로 만들어 커밋하세요.
3. **Settings → Pages**에서 Source를 **Deploy from a branch**로, Branch를 **main / (root)**로 정하고 Save를 누릅니다.
4. 1~2분 뒤 `https://<깃허브아이디>.github.io/goldj-workspace/` 주소로 열립니다.

> **공개 범위 주의.** 무료 계정에서 GitHub Pages를 쓰려면 저장소가 **공개(Public)**여야 하고, 페이지 주소를 아는 사람은 누구나 열 수 있습니다. `index.html` 안에는 블로그 예시 원고·스타일 프로필·발행 계획이 들어 있습니다. 외부에 보이면 안 된다면 비공개 저장소에 올리고(유료 플랜은 비공개 Pages 가능), 또는 아래 "내 컴퓨터에서 바로 열기"를 쓰세요.

## 내 컴퓨터에서 바로 열기

폴더를 통째로 내려받아 `index.html`을 더블클릭하면 크롬·엣지·웨일에서 그대로 열립니다.

## Claude 연결 (선택)

- 블로그 서포터 왼쪽 아래 **⚙︎ 설정 · Claude 연결**에서 Anthropic API 키(`sk-ant-...`)를 넣으면 다음 기능이 켜집니다.
  - 블로그: Claude로 초안 쓰기, 방향 3가지 받기, 제목 추천, 편집기 안 다듬기
  - 학회 PPT: 스토리라인 3안, 슬라이드 만들기, 슬라이드별 수정 요청
- 키는 console.anthropic.com에서 만들고, 쓴 만큼 요금이 나갑니다. 키는 **그 브라우저에만** 저장되고 저장소·백업 파일에는 들어가지 않습니다.
- 작성 방식: "기본"은 Sonnet 5.5, "정교하게"는 Opus 5.5를 씁니다.
- 키가 없으면 블로그는 "프롬프트 복사"로, 학회 PPT는 기본 템플릿으로 동작합니다.

## 데이터 저장

- GitHub/내 컴퓨터 버전은 작업 내용을 **그 브라우저(localStorage)**에 저장합니다. 브라우저 기록을 지우면 사라질 수 있으니 백업을 자주 받아 두세요.
  - 블로그: 왼쪽 아래 **데이터 백업 (JSON)** / **백업 불러오기**
  - 학회 PPT: 1단계 '내 프로젝트' 아래 **프로젝트 파일 저장** / **프로젝트 파일 불러오기**
- 브라우저 저장 공간은 보통 5MB 정도라, 사진이 많은 PPT 프로젝트는 저장에 실패할 수 있습니다. 이때는 프로젝트 파일로 저장해 두세요.
- claude.ai 버전(Claude 계정에 저장)과 데이터가 자동으로 이어지지는 않습니다. 옮길 때는 위 백업 파일로 내보내고 불러오세요.

## 인터넷 연결

화면은 GitHub(또는 내 컴퓨터)의 파일로 뜨고, 아래 기능만 인터넷에서 도구를 받아 옵니다.

- PPTX 내보내기·PPT 폼 불러오기: pptxgenjs, JSZip (cdn.jsdelivr.net)
- PDF 자료 읽기: pdf.js (cdnjs.cloudflare.com)
- 영문 글꼴: Google Fonts (Titillium Web, Inter)
