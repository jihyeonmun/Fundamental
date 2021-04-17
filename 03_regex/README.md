# Regex 
## Regex
: Regular Expression

- Stephen Cole Kleene에 의해서 개발되었음.

- 전화번호 패턴을 찾거나, 웹사이트 패턴을 찾는 등 다양한 패턴에 의한 것들을 검색할 때 주로 이용 가능함!
- 사용자가 입력한 데이터가 특정한 패턴에 부합하는지 유효성 검사하는 경우에도 가능함 
- 언어나, 텍스트, 코드에디터 등에서 내장되어 사용가능함! 

- /regex?/i 를 이용해서 활용할 수 있음. 

[실습사이트 - regexr](https://regexr.com/5mhou)

# 정규 표현식 정리

## 문법 정리

### Flags
|Abstract|Expression Flags|뜻|
|:--:|--|--|
|g|global|g 플래그가 붙으면 패턴과 일치하는 모든 것들을 찾습니다. g 플래그가 없으면 패턴과 일치하는 첫 번째 결과만 반환됩니다.|
|i|case insensitive|i 플래그가 붙으면 대소문자 구분 없이 검색합니다. 따라서 A와 a에 차이가 없습니다.|
|m|multiline|다중 행 모드를 활성화합니다.|
|s|single line(dotall)|.이 \n도 포함되도록 'dotall'모드를 활성화함|
|u|unicode|유니코드 전체를 지원함.|
|y|sticky|문자내 특정 위치에서 검색을 진행하는 'sticky'모드를 활성화시킴.|


### Groups and ranges

| Chracter | 뜻                                     |
| -------- | -------------------------------------- |
| `\|`     | 또는                                   |
| `()`     | 그룹                                   |
| `[]`     | 문자셋, 괄호안의 어떤 문자든           |
| `[^]`    | 부정 문자셋, 괄호안의 어떤 문가 아닐때 |
| `(?:)`   | 찾지만 기억하지는 않음                 |

### Quantifiers

| Chracter    | 뜻                                  |
| ----------- | ----------------------------------- |
| `?`         | 없거나 있거나 (zero or one)         |
| `*`         | 없거나 있거나 많거나 (zero or more) |
| `+`         | 하나 또는 많이 (one or more)        |
| `{n}`       | n번 반복                            |
| `{min,}`    | 최소                                |
| `{min,max}` | 최소, 그리고 최대                   |

### Boundary-type

| Chracter | 뜻               |
| -------- | ---------------- |
| `\b`     | 단어 경계        |
| `\B`     | 단어 경계가 아님 |
| `^`      | 문장의 시작      |
| `$`      | 문장의 끝        |

### Character classes

| Chracter | 뜻                           |
| -------- | ---------------------------- |
| `\`      | 특수 문자가 아닌 문자        |
| `.`      | 어떤 글자 (줄바꿈 문자 제외) |
| `\d`     | digit 숫자                   |
| `\D`     | digit 숫자 아님              |
| `\w`     | word 문자                    |
| `\W`     | word 문자 아님               |
| `\s`     | space 공백                   |
| `\S`     | space 공백 아님              |



#### 출처 사이트
[드림코딩 엘리 Github](https://github.com/dream-ellie/regex)
[드림코딩 - 엘리](https://youtu.be/t3M6toIflyQ)

----
# 실습하기

### Practice Text
Hi there, Nice to meet you. And Hello there and hi.
I love grey(gray) color not a gry, graay and graaay. grdy
Ya ya YaYaYa Ya

abcdefghijklmnopqrstuvwxyz
ABSCEFGHIJKLMNOPQRSTUVWZYZ
1234567890

.[]{}()\^$|?*+

010-898-0893
010 898 0893
010.898.893
010-405-3412
02-878-8888

dream.coder.ellie@gmail.com
hello@daum.net
hello@daum.co.kr

http://www.youtu.be/-ZClicWm0zM
https://www.youtu.be/-ZClicWm0zM
https://youtu.be/-ZClicWm0zM
youtu.be/-ZClicWm0zM

----
1. /(Hi/Hello)|(And)/gm
: 1그룹(Hi,Hello)과 2그룹(And)으로 나뉘어지게 됨

2. /gr(e/a)y/gm
: grey, gray 나타남! -> 이 경우 그룹 지정되지만 (?:)로 하게 되면 그룹 지정 안됨
-> 그룹은 저장용인듯

3. /gr[a-e]y/md
: 이러면 gray~grey까지 모두 가능!
-> 이렇기에 [a-f]도 가능!

4. 응용하면 [a-zA-Z0-9]도 가능!
-> 여기서 [^a-zA-Z0-9]면 반대 표시(제외한 나머지)!

5. /gra?y/gm (있고 없고)
-> gray, gry
<br>
    5-1. /gra*y/gm (있고 없고 많고)
    -> gray, gry, graay, graaay

    5-2. /gra+y/gm(하나 또는 많이) 

    5-3. /gra{1,2}y/gm (최소 혹은 최소 그리고 최대 가능!)

6. /\bYa/gm, /Ya\b/gm
-> Ya가 앞에 쓰이는 경우, 뒤에 쓰인 경우

7. /^Ya/gm, /Ya$/gm
-> 문장 처음 Ya, 문장 끝 Ya

8. /./gm
-> 전체

9. /\.\/gm
-> 특수문자는 백슬러시 써야함! 

### Character classes

| Chracter | 뜻                           |
| -------- | ---------------------------- |
| `\`      | 특수 문자가 아닌 문자        |
| `.`      | 어떤 글자 (줄바꿈 문자 제외) |
| `\d`     | digit 숫자                   |
| `\D`     | digit 숫자 아님              |
| `\w`     | word 문자                    |
| `\W`     | word 문자 아님               |
| `\s`     | space 공백                   |
| `\S`     | space 공백 아님              |


### Quiz1. 전화번호부만 선택
/\d\d\d-\d\d\d\d-\d\d\d\d/gm
/\d{2,3}[- .]\d{4}[- .]\d{4}/gm

### QUIZ2. EMAIL
/[a-zA-Z0-9._+-]+@[a-zA-Z0-9-]+\.[a-zA-Z0-9.]+/gm

### Quiz3. Youtube
/(https?:\/\/)?(www\.)?youtu.be\/([a-zA-Z0-9-]{11})/gm

![img](/img/img1.png)


```javascript
const regex = /(https?:\/\/)?(www\.)?youtu.be\/([a-zA-Z0-9-]{11})/;
const url = "https://youtu.be/t3M6toIflyQ";
url.match(regex);
const result = url.match(regex);
result[1]; //주소만 추출 가능!!

```

[RegexOne](http://regexone.com)