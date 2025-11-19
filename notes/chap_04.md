# \#4. 깃과 브랜치

## - I. 원격 저장소와 깃허브

**· 원격 저장소란?**

**로컬 저장소가 아닌 컴퓨터나 서버에 만든 저장소**를 의미한다. 특히 이는 백업 뿐만 아니라, 규모가 큰 프로젝트에서의 협업을 할 때에도 필수적이다.

Git과 관련해 가장 많이 사용하는 서비스가 **GitHub**이다.

### - GitHub로 할 수 있는 것들
**1. 원격 저장소에서 Git을 사용할 수 있다.**

따로 Git을 사용하지 않고도 온라인에서 Git의 버전 관리 기능을 사용할 수 있음.


**2. 지역 저장소를 백업할 수 있다.**

GitHub가 아닌 Google Dirve 등 다양한 클라우스 서비스에 백업해도 되지만, GitHub에 백업하면 손쉽게 commit이 가능하기 때문.


**3. 온라인 개발 툴을 사용할 수 있다.**

GitHub에 코드스페이스(Codespaces)라는 기능이 추가되어 클라우드에서 작성 및 수정할 수 있게 되었는데, GitHub에 나만의 개발 환경을 만들어 둘 수 있다.


**4. 협업 프로젝트에 사용할 수 있다.**

인터넷만 가능하면 누구나 접근할 수 있고, Git과 GitHub에서 다양한 협업 관련 툴을 제공한다. 따라서, 이를 사용할 경우 팀원 여러명이 하나의 프로젝트를 진행하기에도 쉽다.


**5. 자신의 개발 이력을 남길 수 있다.**

GitHub에서 소스를 수정하고 오픈 소스에 참여해서 하는 일은 모두 기록으로 남게 된다. 이는 어느 분야에 관심이 있는지, 어떤것을 개발했고 현재 개발 진행중인지 등, 개발자가 자신의 이력을 관리하기 좋은 곳이기 때문이다.


**6. 다른 사람의 소스를 살펴볼 수 있고, 오픈 소스에 참여할 수 있다.**

다른 사람의 소스를 읽어 보고 분석하며, 자기 나름대로 소스를 수정하고 작성은 실력을 높히는데에도 큰 도움이 된다. 또한, GitHub에는 Git을 비롯하여 웹 개발, AI, 데이터 과학 등 다양한 오픈 소스가 공개되어 있다.


## - II. 로컬 저장소와 원격 저장소

- 지역 저장소(Local Repository) : **사용자의 컴퓨터** 내에 있는 저장소
- 원격 저장소(Remote Repository) : **GitHub**에 있는 저장소
- 로컬에서 원격 저장소로 등록하는 것은 **푸쉬(push)** 라고 한다.
- 원격 저장소에서 로컬로 내려받는 것은 **풀(pull)** 이라고 한다.

단, local repository와 remote repository를 연결하였기 때문에 변경 사항이 있을경우 push와 pull을 통해 동일하게 만들어야 한다.

이를 **동기화(synchronize)** 라고 한다.

### · 원격 저장소 생성

GitHub에서 repository를 생성할 경우 입력해야 할 것들이 나타난다.

- 1. `Repository name`

Repository의 **이름**. 영문, 숫자, 언더바(_) 등 일부 특수기호가 가능하며, 공백 입력 시 자동으로 '-' 로 바꿔준다.


- 2. `Description`

Repository를 소개하는 **간단한 설명**이다. 공백으로 비워둘 수 있다.


- 3. `Public/Private option`

Repository를 공개로 둘지 비공개로 둘지 설정한다.


- 4. `Add a README`

Repository 생성 시, **README.md 파일을 자동으로 생성할지**에 대한 여부를 묻는 설정이다.


- 5. `Add a .gitignore`

Repository 생성 시, **.gitignore 파일을 자동으로 생성할지에 대한 여부**를 묻는 설정이다. 아래 드롭다운 선택지에서 어떤 언어와 관련된 것을 포함할지 고를 수 있다.


- 6. `Choose a license`

오픈 소스 프로젝트 개발 시, 이를 위한 **라이센스**를 선택할 수 있다.


## - III. 지역 저장소를 원격 저장소에 연결(HTTP)

- local repository와 remote repository를 연결하기 위해서는 다음과 같은 명령어가 필요하다.

`git remote add origin  <repository_url>`

※ 원격 저장소의 주소는 다음과 같다:
`https://github.com/<ID>/<repository_name>`

- 원격 저장소에 잘 연결되었는지 확인

`git remote -v`

## - IV. local과 remote 간 동기화

- local의 branch를 remote에 push

`git push -u origin main`


- local에서 파일을 push할 경우.

`git push`


- remote에서 파일을 pull할 경우.

`git pull`


※ 원격 저장소에서 직접 파일을 추가하여 commit도 가능하다.

## - V. GitHub에 SSH 원격 접속

- SSH 원격 접속이란?

SSH는 **s**ecure **sh**ell의 약자로, 보안이 강화된 안전한 방법으로 정보를 교환.


- SSH 키 생성(RSA Algorithm)

`ssh-keygen`


- 보안이 더 강한 ed25519 Algorithm을 사용하는 SSH 키 생성

`ssh-keygen -t ed25519 -C <name>`


이때, -t 옵션은 key type(ed25519)을 지정해주며 -C 옵션은 Comment(\<name>)를 의미한다.

## - VI. 연습 문제

> 1. 원격 저장소에 연결
- `git remote add origin <repository_url>`

> 2. 원격 저장소에 연결되었는지 확인
- `git remote -v`

> 3. 지역 저장소의 commit을 맨 처음 원격 저장소로 올리기
- `git push -u origin main`

> 4. 지역 저장소의 commit을 원격 저장소로 올리기
- `git push`

> 5. 원격 저장소의 commit을 지역 저장소로 내려받기
- `git pull`

> 6. SSH 키 생성
- `ssh-keygen <option>`