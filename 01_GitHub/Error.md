# Error

---

## Error Case 1

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

---
