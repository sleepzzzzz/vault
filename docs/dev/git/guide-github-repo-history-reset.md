# GitHub 저장소 이력 완전 초기화 가이드

- **Created At:** 2026-03-27
- **Updated At:** 2026-03-27

1. 기존 로컬 Git 기록 삭제 (과거의 모든 커밋 이력을 지웁니다)
rm -rf .git

2. Git 저장소 새로 만들기
git init

3. 기본 브랜치 이름을 main으로 설정 (최신 깃허브 표준)
git branch -m main

4. 원격 저장소(GitHub) 주소 다시 연결
git remote add origin https://github.com/sleepzzzzz/vault.git

5. 현재 폴더의 모든 파일을 스테이징 영역에 추가
git add .

6. 새로운 '첫 번째' 커밋 생성
git commit -m "chore: initial commit with clean history"

7. GitHub 서버의 main 브랜치 내용을 로컬 상태로 강제 덮어쓰기
git push -u origin main -f

8. (선택) 이전 빌드 결과물이 남은 gh-pages 브랜치 삭제 (깨끗한 재배포를 위함)
git push origin --delete gh-pages

--------------------------------------------------
# [작업 후 필수 체크리스트]

1. GitHub 리포지토리 페이지에서 커밋 이력이 1개로 줄었는지 확인한다.
2. GitHub Settings > Pages 메뉴에서 배포 브랜치가 'gh-pages'로 잘 선택되어 있는지 확인한다. (없다면 Actions 완료 후 재설정)
3. 'docs/hidden/' 폴더가 .gitignore에 잘 등록되어 있어 커밋 목록에 포함되지 않았는지 확인한다.