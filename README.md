# Git
> 분산 버전 관리 시스템
- 장점 : 의존x, 동시에 다양한 작업, 백업 복구 용이, 인터넷 연결 없이 작업 가능
- 역할 :코드의 버전(히스토리)를 관리, 개발되어 온 과정 파악, 이전 버전과의 변경 사항 비교
-> 코드의 변경 이력을 기록하고 협업을 원활하게 하는 도구

# Git의 3가지 영역
| 영역 | 뜻 |
| --- | --- |
| Working Directory | 실제 작업 중인 파일들이 위치하는 영역 |
| Staging Area | Working Directory에서 변경된 파일 중, 다음 버전에 포함시킬 파일들을 선택적으로 추가하거나 제외할 수 있는 중간 준비 영역 |
| Repository | 버전 이력과 파일들이 영구적으로 저장되는 영역, 모든 버전과 변경 이력이 기록됨 |

# commit
> 버전
- 변경된 파일들을 저장하는 행위이며, 마치 사진을 찍듯이 기록한다 하여 'snapshot'이라고도 함

# Git init
```git init```

- 저장소 생성하는 명령
- 로컬 저장소 설정(초기화) git의 버전 관리를 시작할 디렉토리에서 진행
- (master)라는 표시는 버전관리 저장소라는 뜻, 현재 버전관리 하고 있는 곳
- git 저장소 내에 또 다른 git 저장소를 만들면 안 됨

# Git add
```git add (파일이름 또는 현재 폴더에 해당 파일이 있으면 .)```

- 변경사항이 있는 파일을 staging area에 추가

# Git commit
```git commit -m "띄울 메시지"```

-staging area에 있는 파일들을 저장소에 기록->해당 시점의 버전을 생성하고 변경 이력을 남기는 것

# Git config --global
```git config --global user.name "이름"```
```git config --global user.email "메일주소"```

# Git log
```git log```

- 변경 내역 보기

# git 기타 명령어
```git status```
- 현재 로컬 저장소의 파일 상태 보기

```git log```
- commit history 보기

```git log --oneline```
- commit 목록 한 줄로 보기

```git config --global -l```
- git global 설정 정보 보기

# Git commit --amend
```git commit --amend```

- commit 메시지 수정 또는 commit 전체 수정
- 터미널에서 새로운 화면으로 들어가게 됨
- 메시지 수정 또는 추가하고, esc 누른 후 :wq 치고 esc 누르면 됨

7/17 배운 거
# Git remote
``` git remote add origin remote_repo_url```

- 로컬 저장소에 원격 저장소 추가
- 추가하는 원격 저장소 별칭
- 추가하는 원격 저장소 주소(url)
-> github 주소

# Git push
```git push origin master```

- 원격 저장소에 commit 목록을 업로드
- git아, push 해줘 origin이라는 이름의 원격 저장소에 master라는 이름의 브랜치를
- 이 명령어까지 해야 원격 저장소에 업로드 완료

# Git pull
```git pull origin master```

- 원격 저장소만의 변경사항만을 받아옴 (업데이트)

# Git clone
```git clone remote_repo_url```

- 원격 저장소 전체를 복제(다운로드)
- clone으로 받은 프로젝트는 이미 git init이 되어 있음

# Git revert
```git revert <commit id>```

- 특정 commit을 없었던 일로 만드는 작업
- “재설정”
- 단일 commit을 실행 취소하는 것
- 프로젝트 기록에서 commit을 없었던 일로 처리 후 그 결과를 새로운 commit으로 추가함

# Git reset
```git reset```

- 특정 commit으로 되돌아가는 작업
- 되돌리기
- 시계를 마치 과거로 돌리는 듯한 행위
- 특정 commit으로 되돌아 갔을 때, 되돌아간 commit 이후의 commit은 모두 삭제

# Git restore
```git restore```

- Modified 상태의 파일 되돌리기
- working directory에서 파일을 수정한 뒤, 파일의 수정 사항을 취소하고, 원래 모습대로 되돌리는 작업
- 원래 파일을 덮어쓰는 원리이기 때문에 수정한 내용은 전부 사라짐
- git restore를 통해 수정 취소 후에는 해당 내용을 복원할 수 없음