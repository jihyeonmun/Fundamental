## GitHub?

- 깃허브 (원래는 Logical Awesonme LLC)는 분산 버전 관리툴인 깃(Git)을 사용하는 프로젝트를 지원하는 웹호스팅 서비스이다.

## Git?

- 깃은 컴퓨터 파일의 변경사항을 추적하고 여려 명의 사용자들 간에 해당 파일들의 작업을 조율하기 위한 분산 버전 관리 시스템이다. 소프트웨에 개발에서 소스코드 관리에 주로 사용되지만 어떠한 집한의 파일의 변경사항을 지속적으로 추적하기 위해 사용될 수 있다.

## Commit & Push?

![git push & pull](https://blog.kakaocdn.net/dn/dcc3ub/btqNQamP35o/hmXwFIBPB82ea5NX3ZwQyK/tfile.svg)

- 일반적으로 로컬 레포지토리(우리의 PC)에서 커밋을 계속해서 진행하게 되고 원격 레포지토리(Github)에 push를 날려서 저장하게 한다!
- 일반적으로 branch는 master를 활용하게 한다.

##Pull

- pull은 update된 원격 깃허브를 기반으로 로컬 레포지토리를 업데이트하는 것으로 보면 된다.

##GitFlow?
![참고 GitFlow](https://postfiles.pstatic.net/MjAxODAyMDNfOTgg/MDAxNTE3NjI3MzI0NjU1.V2GkhqrdgVSj0N7n8PDlWb9JvEQInMis5jW1b7QnCE8g.PQtKm7LOuraB3UeBICJ-byEe4SOTiWfIzQylWvzAPxog.PNG.aufcl4858/kF7Uf.png?type=w2)

- 깃 플로우 전략은 소프트웨어 소스코드를 관리하고 출시하기 위한 '브랜치 관리 전략' 중 하나이다.
- 깃 폴로우는 Vicent Driessen이 제안한 git의 workflow 디자인에 기반한 브랜칭 모델이다. git-flow에서 사용하는 브랜치의 종류는 5가지이며, 크게 항상 유지되는 메인 브랜치(master, develop)와 일정 기간 유지되는 보조 브랜치(feature,release,hotfix)로 나뉜다.

1. master - 제품으로 출시되는 브랜치
2. Develop - 다음 출시 버전을 개발하는 브랜치
3. Feature - 기능을 개발하는 브랜치
4. Release - 이번 출시 버전을 준비하는 브랜치
5. Hotfix - 출시버전에서 발생한 버그를 수정하는 브랜치

- 브랜치 간에 수정사항을 병합하기 위해서는 `Compare & Pull Request`를 활용해야 한다

- 결국 base branch에 비교대상이 되는 branch를 통해 수정사항을 반영하게 한다.

- 일반적으로 pull request 내용에서 수정사항을 요청드리고, 관리자는 확인한 뒤에 `Merge Pull Request`, `Confirm Merge`를 통해 승인하게 된다.

- 특히 이슈 관리를 통해서 각 팀별 인원별로 업무를 할당하고 수행여부를 계속해서 체크해나가면서 기록물로 관리하고 있는 것이 아주 중요하다고 볼수 있다.(나 또한 나의 깃허브를 이슈관리를 통해 관리하는 것이 맞는 거 같다! )

#### 참고사이트

[유투브 개발자의 품격](https://youtu.be/-27WScuoKQs)

# 우리는 Github를 이렇게 사용한다.

깃허브는 프로젝트를 진행하면서 일어나는 크고 작은 이슈, 개발진행사항, 개발자간의 커뮤니테이션 등 다양한 task 들에 대해서 Github 하나만을 이용해서 진행한다.

## 이슈 관리

- 프로젝트 진행시 나오는 모든 이슈, 고객 미팅, 개발 시 필요한 준비사항 등 프로젝트에서 필요한 모든 내용을 이슈관리를 통해서 관리한다.

![이슈관리](https://miro.medium.com/max/1400/1*8C5uVUH57G6nlJRRcYjv8A.png)

-> 사실 여기서 나도 막혔던 것이 라벨링이 상당히 중요한데, 이 참고링크에서는 가이드라인을 제공해주었다.

1. **meeting** : 고객 /사용자와의 업무협의 미팅이 있는 경우 사용한다. 미팅시 필요한 내용/ 확인해야할 사항 / 요청해야 할 사항 등을 정리

2. **todo** : 한주단위로 각자해야할 task를 등록한다. task 작성시 add a task list 버튼을 이용해서 task 목록을 작성하면, 이슈 리스트 화면에서 task의 진척 사항을 직관적으로 확인할 수 있다.

3. **development** : 개발을 하기 위해서 사전에 완료되어야 하는 task 목록을 작성한다. 해당 task가 완료되어야 개발자가 실제 개발에 착수할 수있다. 개발시 주의해야할 업무 내역과 비즈니스 로직을 정리하여 개발자가 개발시 참조하도록 한다.

4. **bug** : 개발자가 projects 탭에서 개발목록을 개발완료로 이동시켜 놓으면 해당 개발목록에 대해서 테스트를 진행하고, 테스트에서 나온 bug 내용을 작성하게 된다.

- 가장 좋은 점은 해당 이슈에 코멘트가 달리면 이메일ㄹ 모두에게 공유가 가능하다!

## 개발진행관리(Project 탭)

- 개발 목록은 화면단위로 관리함. 각 화면에 필요한 다양한 api 개발이 필요하더라도 각각을 별도로 관리하지 않고, 사용자가 직접 사용하는 화면단위로 목록을 관리한다.
- 개발목록 / 개발 진행중 / 개발완료/ 테스트 완료/ 최종 개발 완료 5개 컬럼으로 나누어서 관리하는 것이 일반적이다.
- 개발 주기는 한 달 주기로 하며, 한 달을 기준으로 개발해야할 목록을 개발목록 컬럼에 추가하며, 이때 개발해야 할 목록과 연관된 이슈 등록 번호를 맵핑해서 등록한다. 예를 들어 해당 화면 개발에 필요한 화면 정보 및 업무 정보/ DB 정보 등을 이슈에 상세등록하고 해당 이슈번호를 개발목록에 맵핑하여, 개발자가 쉽게 연관 정보를 찾아볼수 있도록 하고 있다.

## 개발 코드 관리

![commit](https://miro.medium.com/max/1400/1*6FN17_Ww6r5Q_L-JXwU-sQ.png)

commit시 최대한 상세하게 commit내용을 등록하고 commit 카테고리를 지정하여 쉽게 찾고, 관리 될 수 있도록 하고 있다.
크게 아래와 같이 commit 카테고리를 관리할 수 있다.

- [INITIAL] — repository를 생성하고 최초에 파일을 업로드 할 때
- [ADD] — 신규 파일 추가
- [UPDATE] — 코드 변경이 일어날때
- [REFACTOR] — 코드를 리팩토링 했을때
- [FIX] — 잘못된 링크 정보 변경, 필요한 모듈 추가 및 삭제
- [REMOVE] — 파일 제거
- [STYLE] — 디자인 관련 변경사항

## 문서 관리

- 구글 드라이브에서 각종 문서를 관리함과 동시에 이슈 등록 시 참조해야할 문서에 대한 링크를 등록하여 사용하면 된다.

![개발 문서](https://miro.medium.com/max/1400/1*VopDv-q7irFR9-nWFNfLPA.png)

[우리는 Github를 이렇게 사용한다.](https://medium.com/returnvalues/%EC%9A%B0%EB%A6%AC%EB%8A%94-github%EB%A5%BC-%EC%9D%B4%EB%A0%87%EA%B2%8C-%EC%82%AC%EC%9A%A9%ED%95%9C%EB%8B%A4-83789075e5b6)

---

# 실생활에서 Github 진라면 순한맛

## Basic

```git
echo "# JavaInterview" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/jihyeonmun/JavaInterview.git
git push -u origin main
```

> 일반적으로 위와 같은 형태로 시작하고, 각 파일 추가하고, 커밋하고, 브랜치 설정하고 원격 레포지토리 리모트(연결)해서 푸쉬한다.

```git
git pull origin master
```

> 내가 업데이트가 안되서 push 안되는 경우가 종종있다. 추가적으로 pull을 하고 나서 push를 해야하고, 충돌하는 것을 없애도록 하는 것도 필요하다!

## 항상 세팅!

```git
git config --global user.name "사용자 이름"
git config --global user.email "사용자 깃 이메일"
```

---

# 실생활에서 Github 진라면 매운맛

## Git

### git 개념 및 명령어 정리

개인 개발을 넘어, 공동 개발에서 효율적인 코드 형상 관리를 하기 위함.

#### Git 영역

##### (1) Working Directory (Local)

​ 개인 코드 작성

##### (2) Staging 영역

​ git add 를 통해서 수정된 코드를 올리는 영역

##### (3) Repository

​ git commit 을 통해서 최종 수정본을 제출

### Git 작업 플로우

먼저 터미널에 git을 설치합니다.

linux (Ubuntu) 기준

$ sudo apt install git-all

##### (1) 저장소(Repository) 생성

원하는 폴더 들어간 후

```
$ git init
```

또는 기존 github에 있는 저장소를 내 로컬로 복제할 수도 있습니다.

```
$ git clone (git 저장소의 URL)
```

##### (2) 코드 생성 (in Working directory)

이 예제에서는 README.md 라는 파일에 스트링 문자를 쓰는 코드를 만들겠습니다.

```
$ echo "Hello, Git!" > README.md

```

확인 >>

```
$ cat README.md
Hello, Git!
```

##### (3) Staging 영역에 추가

코드 수정이 완료되면 staging 영역에 추가합니다.

```
$ git add .
```

현재 디렉토리에 있는 업데이트 된 파일을 전부 스테이징 영역으로 추가합니다.

또는,

```
$ git add -A
```

수정된 파일 전부를 스테이징 영역에 추가합니다.

```
$ git status
```

로 현재 add 내역을 확인할 수 있습니다.

##### (4) Repository에 commit

```
$ git commit -m "2020-02-16 README.md update"
```

-m 은 메세지의 약자이고, 뒤에 ""안에 공유할 메시지 내용을 적어주시면 됩니다.

##### (5) 원격 저장소에 push, 업데이트 된 내용은 pull

내 local 디렉토리로 부터 원격저장소(Remote repository)로 보내기 위해서는 push 명령어를 사용합니다.

그 전에 원격 저장소와 내 로컬을 연결해야 합니다.

##### 원격 저장소 연결 (github)

```
$ git remote add origin (원격 저장소 github URL)
```

origin은 remote repository의 이름이며, 다른 이름으로 설정해도 무방합니다.

##### push

```
$ git push origin master
```

origin이라는 원격저장소의 master 브랜치 (브랜치는 뒤에서 설명)에 푸쉬합니다.

##### pull

또한 다른 사람이 원격 저장소(Remote repository)에 업데이트한 파일이 있을 때, 원격저장소와 내 로컬저장소의 상태를 동일하게 만들기 위해 pull을 이용합니다.

```
$ git pull
```

---

그 외 알아두면 좋은 git 명령어

##### (6) 커밋 이력 확인

```
$ git log
```

또는

한 줄로 요약해서 보고 싶은 경우

```
$ git log --oneline
```

##### (7) 파일변경시 (Working drectory → Staging) 내역 확인 및 취소

현재 디렉토리에 README.md 가 있다는 가정하에,

이 파일에 다른 내용을 적어 업데이트하고, 무엇이 바뀌었는지 확인해봅니다.

##### 파일 내용 변경

```
$ echo "update test" >> README.md
```

##### 내용 변경 확인

```
$ cat README.md
Hello, Git!
update test
```

##### 변경 내용 확인

```
$ git diff
```

##### staging 취소 (unstage)

```
$ git reset
```

또는

```
$ git reset --hard
```

working directory 까지도 변경전 상태로 되돌림 즉, 변경한 내용이 소멸되므로 주의

##### (8) commit 정리

여러개의 commit을 하나의 commit으로 정리 -> 불닭볶음면급 상당히 고단수

```
$ git rebase -i
```

직전과 금번 커밋을 하나로 정리

```
git commit --amend
```

###### Git Branch

프로젝트 진행 시, 중간에 에러가 발생한다면 이를 고쳐야합니다. 하지만 그와 동시에 지금 진행하고 있는 프로젝트에서 새로운 모듈을 개발해야 할 경우 위 두 코드는 독립적으로 수행되어야 합니다.

따라서 master (기본 브랜치) 외에 다른 브랜치가 하나더 필요합니다.

##### (9) branch 확인

```
$ git branch
```

현재 설정된 브랜치 앞에 \* 가 붙습니다.

##### (10) branch 생성 및 변경

```
$ git branch mybranch
```

새로운 브랜치 mybranch를 생성했습니다.

```
$ git checkout mybranch
```

기존 브랜치(master)에서 새로운 브랜치(mybranch)로 전환합니다.

따라서 바뀐 브랜치에서 commit을 하면, 원래 브랜치에는 업데이트가 안되고, 새로운 브랜치에서만 업데이트가 됩니다.

push는 다음과 같이 진행하면 됩니다.

```
$ git push origin mybranch
```

origin이라는 원격저장소의 mybranch로 push합니다.

---

### Pull Request와 Merge

-> 진짜 제일 많이 쓰일 거 같은 팔도비빔면급

commit을 한다고 최종 코드가 수정되는 것은 아닙니다.

개인이 commit을 했으면, 관리자가 이 코드를 리뷰하고 바꿀것이 있으면 수정해달라고 다시 요청해야하기 때문입니다. 그 과정을 알아봅니다.

##### 1) Pull Request 발행 (Review 의뢰자)

github에 접속 후, 원격저장소에 들어가서 해당 commit의 pull request 버튼을 누르면 Reviewer에게 풀리퀘스트 메시지 전송

##### 2) Review & Comment (Review 수행자)

리뷰 후 comment 할 것이 있으면 comment 버튼 클릭

##### 3) Comment 대응 (Review 수행자)

local에서 코드 수정 후 원래와 같은 방식으로 commit 수행

```
$ git add .
$ git commit -m "커밋 메시지"
$ git push
```

##### 4) Review 및 병합 (Review 수행자)

리뷰 후 최종 결과 만족 시 병합(merge) → github에서 pull request merge 버튼 클릭

### 출처

[tistory-wordbe](https://wordbe.tistory.com/entry/Git-%EC%82%AC%EC%9A%A9-%EB%B0%A9%EB%B2%95-%EC%A0%95%EB%A6%ACcommit-push-pull-request-merge-%EB%93%B1)

---

# So What? (Summary | Routine)

## 처음 시작

```git
echo "# JavaInterview" >> README.md
//확인 원하면 cat README.md
git init
git add README.md
//확인 원하면 git status
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/jihyeonmun/JavaInterview.git
git push -u origin main
// 다른 사람이 업데이트한 파일이 있으면 git pull
// 커밋 이력 확인해야 하니 git log
// 변경 확인 git diff
// staging 취소 git reset
// commit 정리 git rebase -i
// 두개만 저리하면 git commit --amend
// 브랜치 확인 git branch
// 브랜치 생성 git branch mybranch
// 브랜치 쓸때 git push origin mybranch
```

## 협업

```
1) Pull Request 발행
2) Review & Comment
3) Comment 대응
4) Review 및 병합 -> 만족하면 merge
```

---

# Error

```
To https://github.com/jihyeonmun/SelfLearningaboutJavaSpring.git
 ! [rejected]        main -> main (non-fast-forward)
error: failed to push some refs to 'https://github.com/jihyeonmun/SelfLearningaboutJavaSpring.git'
hint: Updates were rejected because a pushed branch tip is behind its remote
hint: counterpart. Check out this branch and integrate the remote changes
hint: (e.g. 'git pull ...') before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
```

> 정석은 아니지만 쓰지 않으면 깃허브 세부 설정에서 master로 default로 설정하거나

```
git pull origin master
```

원격지 저장소에 내용과 저의 코드가 겹치는 부분 없이 깔끔하게 병합(merge)이 될 수도 있고,같은 부분을 고쳤다던지 한다면, 충돌(conflict)이 발생할 수 있다.

강제로 그냥 때려박는 경우가 가능

물론, 경우에 따라 독이나 약이 될 수 있음...

```
$ git pull origin master --allow-unrelated-histories
```

### 추가 추천 사항

> 1. git pull
> 2. 로컬 저장소에서 변경된 내용 확인 및 작업
> 3. git commit -a ( 'master' branch를 통합한다 )
>    : 그런데 우선 git commit -m "메시지" 로 먼저 시도를 해 볼 것을 추천한다. 근데 안된다면 1번부터 다시 해봐야 한다.
> 4. git push "리모트저장소 닉네임" "브랜치이름"
