# \#3. 깃과 브랜치

## - I. Branch 란?
 브랜치(Branch)의 어원은 나뭇가지이지만, 나무가 가지에서 새 줄기를 뻗듯이 여러 갈래로 퍼지는 데이터 흐름을 가리키는 말로 사용한다.

**- 브랜치를 사용하는 이유**

 개발 단계에서는 다양한 종류의 버전을 구분하여 개발하여야 할 때가 있다.
이때, 각각의 버전을 서로 다른 레포지토리(Repository)로 구분하여 진행한다면 각 저장소별 중복되는 내용도 많아진다.
 게다가, 한 레포지토리에서 개발한 기능을 다른 버전의 레포지토리로 가져다 사용할 때 충돌이 발생할 수 있다. 이를 보완하기 위해 브랜치가 필요하다.
 
**- 브랜치의 기능**

초기에 버전 관리를 시작하게 되면 main 브랜치(구, master branch)에서 시작하게 된다.
이때, 새로운 기능을 추가하기 위해 브랜치를 파게 되면 기존 내용이 그대로 담긴 채 main에는 영향을 주지 않는 새 브랜치가 생성되게 된다.
이와 같이 새 branch를 만드는 것을 "**분기**한다" 라고 함.

만약, 작업을 모두 끝마쳐 main에 이를 반영하고 싶다면 merge를 통해 병합할 수 있다.


## - II. Branch 사용하기

- `git branch`
> 현재 repository의 branch를 확인

- `git branch <name>`
> \<name> 이라는 이름의 branch 생성

- `git branch -d <name>`
> \<name> 이라는 이름의 branch 제거

- `git switch <name>`
> \<name> 이라는 이름의 branch로 전환

- `git log <name1>..<name2>`
> \<name2> 이라는 이름의 branch에만 있는 commit 확인

- `git mearge <name>`
> \<name> 이라는 이름의 branch를 병합

#### ※ fest-forward-merge(빨리 감기 병합)이란?
main에서 branch생성 후, main에 다른 변화가 없다면 병합 시에 main을 분기한 branch의 최신 commit을 가리키도록 하는 것.

## - III. main과 분기에서 같은 파일을 수정할 경우

- git은 같은 문서의 서로 다른 곳을 변경해도 자동으로 합쳐주는 기능이 있어서 문제가 없음.

만약, 같은 문서의 같은 곳을 변경한다면 병합 시 충돌이 발생하게 되고 다음과 같이 변함.

```
~ 생략 ~
<<<<<<<< HEAD
[content1]
=======
[content2]
>>>>>>> <name>
~ 생략 ~
```
해당 위치가 충돌이 발생한 위치이다.
충돌이 발생하였으므로 자동 병합이 아닌, 사용자가 직접 수정 후 병합을 진행하여야 한다.

#### ※ 이를 도와주는 자동 병합 프로그램이 존재함.
병합 알고리즘에는 2-way merge와 3-way merge가 존재하는데, 3-way 알고리즘을 지원하는 프로그램을 선택하는 것이 좋다.

## - IV. 연습 문제

> 1. 새로운 branch 'fixed'를 만든다
- `git branch fixed`

> 2. 생성했던 'fixed' branch로 이동
- `git switch fixed`

> 3. commit log에서 한 줄에 한 commit씩 표시
- `git log --oneline`

> 4. 수정한 파일을 stage에 한번에 올리기
- `git add . (git add -A)`

> 5. commit log에 각 branch의 commit을 그래프로 표시
- `git log --branches --graph`

> 6. 터미널 창에서 'edit.txt' 내용을 확인
- `cat edit.txt`

> 7. 'doit' 디렉토리로 만드는 동시에 지역 저장소로 만들기
- `git init doit`

> 8. 현재 main branch에 있으며, 'fixed' branch를 'main' branch에 병합
- `git merge fixed`

> 9. 병합이 끝난 'fixed' branch를 삭제
- `git branch -d fixed`