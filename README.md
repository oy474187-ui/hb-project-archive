# HB Portfolio Finder v10 — 관리자 + 공개 사이트

## 구성
- `index.html` : 방문자가 보는 공개 포트폴리오
- `admin.html` : 콘텐츠 편집·이미지 업로드·GitHub 저장 관리자 화면
- `content.json` : 28개 프로젝트의 원고·이미지·링크 데이터 (두 페이지가 공유)
- `images/` : 업로드한 이미지 파일
- `media.js` : 구버전 호환용 기본 이미지 데이터 (일상 편집은 필요 없음)

## 배포
1. ZIP 압축을 풀고 **ZIP 안의 파일들을** GitHub 저장소 최상단에 업로드합니다.
2. GitHub Settings → Pages → Deploy from a branch → main / (root)를 선택합니다.
3. `https://사용자명.github.io/저장소명/` 은 공개 사이트입니다.
4. `https://사용자명.github.io/저장소명/admin.html` 은 관리자 편집 화면입니다.

## GitHub에서 직접 저장하기
1. GitHub Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token.
2. **해당 저장소 하나만** 선택하고 Repository permissions → **Contents: Read and write** 권한을 설정합니다. 토큰 만료일도 설정하세요.
3. `admin.html`을 열고 GitHub 사용자명, 저장소 이름, 브랜치, 토큰을 입력합니다.
4. 'GitHub에서 최신 데이터 불러오기'를 눌러 저장소의 최신 변경사항을 가져옵니다.
5. 프로젝트를 선택하고 제목/설명/성과/이미지/링크를 변경합니다.
6. 'GitHub에 저장'을 누르면 `content.json`이 업데이트되고 새 이미지가 `images/`에 업로드됩니다.
7. Pages가 새 배포를 완료하면 방문자 `index.html`에서도 변경사항이 보입니다. 배포 반영에는 시간이 걸릴 수 있습니다.

## 사진 올리기
- 각 이미지 슬롯에서 '새 이미지 선택'을 누르고 WebP/JPG/PNG를 선택하세요.
- 4 MB 이하로 권장/제한했습니다. 대용량 이미지는 WebP로 압축하세요.
- 이미지를 선택하기만 해서는 업로드되지 않습니다. 하단 **GitHub에 저장** 버튼을 눌러야 합니다.
- 기존 이미지를 바꾸면 새 이미지 경로를 참조하며, 이전 파일은 자동 삭제되지 않습니다.
- 외부 URL을 입력할 수 있지만, 공개 접근 가능한 이미지 URL이어야 합니다.

## 꼭 알아둘 점
- **GitHub Pages만으로 인증된 자체 DB가 제공되지는 않습니다.** 관리자 페이지는 GitHub REST API와 사용자가 직접 입력한 Personal Access Token으로 저장합니다.
- `admin.html` 파일 주소 자체는 공개됩니다. **토큰은 HTML/JSON/이미지/GitHub 저장소에 절대 입력하거나 커밋하면 안 됩니다.** 토큰은 세션 메모리 내에서만 사용하고 브라우저 저장소에 기록하지 않습니다.
- 본인 계정에 로그인하고 안전한 기기에서만 사용하세요. 토큰 유출 시 GitHub에서 즉시 폐기하세요.
- URL로 공개된 원본 이미지는 누구나 접근할 수 있습니다. 타인의 초상권/개인정보/회사 내부자료를 확인한 뒤 업로드하세요.
- `file://`로 HTML을 직접 열면 `content.json` fetch가 제한될 수 있습니다. GitHub Pages 주소에서 사용하는 걸 권장합니다.
- 저장 전 JSON 백업 다운로드 기능으로 원본을 보관할 수 있습니다.
- 기존 저장소에 v9 파일이 있다면 v10 파일을 덮어 올리고, 처음에는 `content.json`도 함께 업로드하세요.
