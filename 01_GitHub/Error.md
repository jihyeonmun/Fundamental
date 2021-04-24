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

### git rsa 에러
---

깃허브에 push 하려고 했는데 에러가 발생했다.

Warning: Permanently added the RSA host key for IP address '192.***.***.***' to the list of known hosts.

git@github.com: Permission denied (publickey).

fatal: Could not read from remote repository.



Please make sure you have the correct access rights

and the repository exists.





검색해보니 해결방법이 나왔다.

(참고로 윈도우에 Git이 설치되어 있다는 가정 하의 해결방법이다.)

1. github에 로그인한다.
2. 우측상단의 아이콘을 누르고 Settings를 클릭한다.
3. SSH and GPG keys를 클릭한다.
4. New SSH key를 클릭한다. (여기서 일단 그대로 둬야 함)
5. Git Bash를 실행한다. (Git 설치 필요)
6. ssh-keygen -t rsa -b 4096 -C "email@email.com" 명령어를 실행한다.
7. Enter file in which to save the key (/c/Users/사용자/.ssh/id_rsa): 여기서 엔터를 누른다.
8. 8. Enter passphrase (empty for no passphrase): 암호를 입력하고 엔터를 누른다.
9. Enter same passphrase again: 방금 적은 암호를 다시 입력하고 엔터를 누른다.
10. 완료되면 콘솔에 파일이 생성된 경로가 표시된다.
11. 해당 경로로 이동하여 id_rsa.pub 파일을 메모장으로 연다.
12. 내용을 복사한다.
13. 다시 github 사이트 창으로 간다.
14. SSH keys / Add new 페이지에서 Title에 적당한 제목을 적고 복사한 key를 붙여넣고 Add SSH key 버튼을 누른다.
15. 이제 push 할 때 아까 설정한 암호를 입력하라는 말이 나온다.
16. 아까 입력한 암호를 입력하고 엔터를 치면 이제 잘 push 된다.
#### 참고 사이트
[링크](https://lasdri.tistory.com/809)
