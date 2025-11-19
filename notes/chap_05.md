# \#5. 깃허브로 협업하기

## - I. 서로 다른 컴퓨터에서 원격 저장소 사용

- 원격 저장소 복제하기 : `git clone <repository_url>`

- 하나의 repository에서 두 대 이상의 컴퓨터로 작업을 진행한다면, 수시로 push와 pull을 통해 동기화하여 local과 remote의 상태를 같게 만들어주는 것이 중요하다.

## - II. 원격 branch 정보 가져오기

- fetch는 '불러오다, 가져오다' 라는 의미.

- `git fetch`
> 원격 저장소의 정보를 가져오는 명령어
**※ 정보만 가져올 뿐, merge 하지는 않음**


`git pull`명령은 `git fetch`와 `git merge origin/main`을 합친 것과 같은 기능을 한다.

## - III. 원격 저장소에서 협업하기

- `git clone <repository_url> <branch_name>`
> 저장소를 복제해오는 명령어

 단순히 내가 작업한 내용을 commit한다고 끝나는 것이 아니다.
GitHub에서 pull Request를 통해 commit을 병합하여야 제대로 반영이 된다고 볼 수 있다.

**※ commit을 branch로 병합하는 과정도 하나의 commit이므로 반드시 commit 메시지를 입력해줘야 한다.**

## - IV. 연습 문제

> 1. 원격 저장소를 'myhome'이라는 지역 저장소로 복제
- `git clone <repository_url> myhome`

> 2. 원격 저장소의 commit을 가져오기만 하고, 병합은 하지 않을 때
- `git fetch`

> 3. 원격 저장소의 최신 commit을 가져올 때
- `git pull`

> 4. fetch로 가져온 정보와 최신 commit의 차이를 살펴볼 때
- `git diff HEAD origin/main`

> 5. 현재 Git 환경에서 사용할 이름을 지정할 때
- `git configure user.name "<name>"`

> 6. 현재 Git 환경에서 사용할 이메일 주소를 지정할 때
- `git configure user.email "<email>"`

> 7. GitHub의 apple branch로 첫 commit을 올릴 때
- `git push -u origin apple`

> 8. 협업 저장소에 커밋을 올리고 리뷰를 위한 메시지를 남기는 것은?
- `pull Request(풀 리퀘스트)`