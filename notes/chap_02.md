# \#2. 깃으로 버전 관리하기 #

- Git에서는 문서 수정 시 간단한 메모(commit)와 함께 수정 내용을 스냅샷으로 찍어서 저장하며, 이를 버전(version)이라고 함.


## - I. Git 저장소 만들기 ##

- `mkdir <name>`
> 디렉토리 생성

- `cd <path>`
> 작업중인 디렉토리 변경

- `ls [option]`
> 현재 디렉토리 내의 파일 출력

- `git init`
> 현재 디렉토리에서 Git을 사용할 수 있도록 초기화

* ※참고 : Git 디렉토리는 사용자가 실수로 삭제할 수 있기 때문에 숨김 처리되어 있다.(.git)


## - II. 버전 만들기 ##

> 프로그램 개발에서는 수정 내용이 쌓이면 번호를 붙여 이전과 구분하는데, 이를 **버전** 이라고 함.

### - 스테이지와 커밋이란? ###

- 1. 작업 트리(working tree) : **작업 디렉토리(working directory)**라고도 하며, 실질적으로 작업을 진행하는 공간

- 2. 스테이지(stage) : 버전으로 만들 파일이 임시로 대기하는 공간. **staging area** 라고도 함.

- 3. 저장소 : **리포지토리(repository)**는 스테이지에서 대기하던 파일들을 버전으로 만들어 저장하는 곳. **커밋(commit)**은 각 버전들을 알 수 있도록 적는 설명.
---

- `git status`
> 현재 Git 상태 확인

- `git add <path>`
> stage에 업로드

- `git commit -m <msg>`
> commit 추가

- `git log`
> 저장소에 저장된 버전 확인

- `git commit -am <msg>`
> 이전에 올린 파일을 스테이징과 커밋을 동시에

* ※참고 : 버전을 한 번이라도 만들었다면 tracked 상태가 됨. 또한, .gitignore를 통해 버전으로 관리하지 않을 파일이나 디렉토리를 지정할 수 있다.

### - modified 상태에 관하여 ###

- 가장 최근 버전에서 파일은 unmodified상태이지만, 파일을 수정하게 되면 modified 상태로 변하게 된다. 이때 stage에 올려 staged 상태로 만들었다가, 버전으로 만들면 다시 unmodified 상태가 된다.
---
- `git restore --staged [path]
> stage에서 모든 파일 또는 [path] 제거

- `git reset [--option] ^HEAD`
> stage에서 내리기 및 commit 취소

- `git revert`
> commit 취소. 단, commit을 했던 기록은 남기게 됨.
---

## - III. 연습 문제 ##

> 1. Git 환경에서 이름을 'easys'로 저장
- `git config user.name 'easys'`

> 2. Git 환경에서 이메일을 'doit@easys.co.kr'로 저장
- `git config user.email 'doit@easys.co.kr'`

> 3. 현재 위치에 지역 저장소 만들기
- `git init`

> 4. Git 상태 확인
- `git status`

> 5. ch01.txt 파일을 stage에 올리기
- `git add ch01.txt`

> 6. staging한 파일을 'ch01'이라는 commit 메시지 붙여 올리기
- `git commit -m 'ch01'`

> 7. 메시지 'ch02'를 붙여 staging과 commit을 동시에 진행하기
- `git commit -am 'ch02'`

> 8. commit 정보를 확인하기
- `git log`

> 9. 최근 버전과 작업 폴더의 수정 파일 간 차이 보여주기
- `git diff`

> 10. 작업 트리에서 work.txt 수정 내용을 취소
- `git restore work.txt`

> 11. work.txt의 staging을 취소
- `git restore --staged work.txt`

> 12. 가장 최근 commit 취소
- `git reset ^HEAD`

> 13. 지정한 commit 해시로 이동하고 이후 commit 취소
- `git reset`

> 14. 지정한 commit 해시의 변경 이력 취소
- `git revert`