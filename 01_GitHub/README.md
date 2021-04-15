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

* 가장 좋은 점은 해당 이슈에 코멘트가 달리면 이메일ㄹ 모두에게 공유가 가능하다! 

## 개발진행관리(Project 탭)

- 개발 목록은 화면단위로 관리함. 각 화면에 필요한 다양한 api 개발이 필요하더라도 각각을 별도로 관리하지 않고, 사용자가 직접 사용하는 화면단위로 목록을 관리한다. 
- 개발목록 / 개발 진행중 / 개발완료/ 테스트 완료/ 최종 개발 완료 5개 컬럼으로 나누어서 관리하는 것이  일반적이다.
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