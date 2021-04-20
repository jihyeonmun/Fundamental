# Clean Code

매번 코드를 작성해보면서,
깨끗한 코드 직관적인 코드에 대한 이상향이 있었지만,

무엇보다 다른 프로그래머 분들의 코딩 영상에서 리팩토링을 하시게 되는 과정이 생각보다 이해가 되지 않았다.

그리고, 코드 자체에서 어떠한 문제가 있는지를 인식하는지도 잘 몰랐다.

그렇기에 클린 코드, 리팩토링을 공부한 선배분들의 지식을 습득하고 싶었졌다.

내용은 다음과 같다.

---

### 나쁜 코드로 치르는 대가

나쁜 코드의 문제점은 코드를 고칠떄마다 엉뚱한곳에서 문제가 발생한다. 이번 회사 프로젝트에서도 하드코딩때문에 후에 그게 변경되면서 의도치 않게 사이드 이펙트가 발생했다. 후에 나쁜코드가 쌓인다면 생산성도 떨어지게 되고 마침내 0에 근접하게 된다고 한다.

생산성이 떨어지면 인력을 추가하여 복구를 시도하지만 문제는 더욱 심각해진다.

### 원대한 재설계의 꿈

코드를 재설계하자며 새로운 팀이 꾸려진다. 그리고 오래걸리는경우 엉망이되는데 결국 깨끗한 코드를 만드는 노력 자체가 비용을 절감하는 방법이다.

### 태도

코드가 엉망이라 하나만 고치면 되리라 예상했다가 수백개를 건드린 경험이 있듯이 우리는 여러가지의 핑계를 대며 요구사항이 변경되었다. 일정이 빠듯했다 라는 식의 핑계를 대게 된다. 결국 이런 태도들은 프로그래머의 문제이다

### 원초적 난제

기한을 맞추는 유일한 방법은 언제나 코드를 최대한 개끗하게 유지하는 습관이다.

### 깨끗한 코드라는 예술?

- 깨끗한 코드가 무엇인지 모른다면 작성할 수 없으니 알아야 한다.

### 깨끗한 코드란?

> 비야네 스트롭스트룹 : 우아하고 효율적인 코드 , 철저한 오류처리
> 그래디 부치 : 가독성을 강조
> 큰토마스 : 작성자가 아닌사람도 읽기 쉽고 고치기 쉬운코드, 테스트 케이스가 존재, 의미있는 이름이 존재
> 마이클 페더스 : : 언제나 누군가 주의 깊게 짰다는 느낌을 주는코드
> 론 제프리스 : 중복을 피하라, 한가지 기능만을 수행해라, 제대로 표현하라, 작게 추상화하라
> 워드 커닝햄 : 코드를 읽으면서 짐작했던 기능을 각 루틴이 그대로 수행한다면 깨끗한 코드라 불러도 된다.
> 밥아저씨 생각 : 깨끗한 변수이름, 깨끗한 함수, 깨끗한 클래스

### 보이스카우트 규칙

잘짠 코드가 전부는 아니고, 시간이 지나도 언제나 깨끗하게 유지해야한다. 시간이 지나면서 엉망으로 전락하는 코드가 한둘이 아니다.

그러므로 우리는 적극적으로 코드의 퇴보를 막아야한다.

우리는 체크아웃할 때보다 조금 더 깨끗한 코드를 체크인 한다면 코드는 나빠지지 않는다. 한번에 많은 노력을 투자하지 않고

변수 이름 하나를 개선하고 조금 긴 함수 하나를 분할하고 중복을 제거하고 복잡한 if문 하나를 정리하면 더 나은 프로젝트가 될 수 있다

### 결론

예술책을 읽는다고 예술가가 되는건 아니지만 이책을 읽는다고 뛰어난 프로그래머가 된다는 것은 아니다.

하지만 좋은 정보들로 가득하고 좋은코드와 나쁜코드를 소개하며 나만의 기준을 가지고 나쁜코드를 좋은 코드로 바꾼다면

더 나은 프로그래머가 될거라고 생각한다.

#### 내용 전체 출처

[클린코드](https://namget.tistory.com/entry/클린코드-1장-깨끗한코드?category=786713)

---

나의 코드를 보면서도 남의 코드를 보는 것 같은 느낌이 들 때도 상당히 많았으며,

클린 코드라는 책을 봐도 이해하지 못하는 나를 보면서, 단순히 상식이 아니라 습관 차원에서 공부해보고 싶어졌다.

그렇기에 클린코드에 대한 내용을 작성해보기로 하였다.

---

## 2장

2장 의미있는이름

- 의도를 분명히 밝혀라

의도가 분명하게 이름을 지으라고 말하기는 쉽다. 이 책에서는 의도가 분명한 이름이 중요하다고 강조하고 또 강조한다.

좋은 이름을 지으려면 시간이 걸리지만 그렇게 지어놓으면 후에 유지보수에서 시간을 절약할 수 있다. 그래서 우리는 이름을 주의깊게 살펴서 더 나은이름으로 개선해야한다. 그리고 그걸 읽는 나와 다른사람들도 행복해질 수 있다.

변수나 함수 클래스의 이름은 변수(함수 or 클래스) 의 존재이유? 수행기능? 사용방법? 에 따로 주석이 필요하다면 의도를 분명하게 드러내지 못했다는 말이다.

예들들어

val d = 0; // 경과시간

이름 d는 아무 의미도 드러나지 않는다. d라는 이름만 보고 day인지 delay인지 확인을 한번 더 해줘야한다.

val elapsedTimeInDays : Int = 0
val daysSinceCreation : Int = 0
val daysSinceModeification : Int = 0
val fileAgeInDays : Int = 0

위와같이 의도가 분명한 코드들은 변수명만으로 코드의 이해와 변경 의도가 분명하다.

val theList = arrayListOf<IntArray>()
val list = arrayListOf<IntArray>()
for(x in theList){
if(x[0] == 4){
list.add(x)
}
}

이런 이름을 가진 리스트가 있다고 했을때 딱 변수명만으로는 무슨 동작을 하는 코드인지 알 수 없다.

theList에 무엇이 들었고,
0번째값을 왜 찾아야하며,
값이 4는 무슨 의미인지,
함수가 반환하는 리스트 list는 어떻게 사용하는가?
에 대한 정보가 하나도 드러나지 않는다.

정보제공은 충분히 가능했지만 그렇지 않았다.

우리가 지뢰찾기 게임을 만든다고 가정해보자 그러면 theList가 게임판이라는 사실을 우리는 알 수 있다

theList -> gmeBoard 로 변경해보자

0번째값은 칸 사애를 의미하고 4는 깃발이 꽂힌 상태를 가리킨다.

val gameBoard = arrayListOf<IntArray>()
val STATUS_VALUE = 0
val FLAGGED = 0

fun getFlaggedCells() : List<IntArray>{
val flaggedCells = arrayListOf<IntArray>()
for(cell in gameBoard){
if(cell[STATUS_VALUE] == FLAGGED){
flaggedCells.add(cell)
}
}
return flaggedCells
}

위에서 보듯이 코드의 단순성은 변하지 않는다. 하지만 코드는 더 명확해졌다 더 나아가 int 배열을 사용하는 대신 칸을 간단한 클래스로 만들어도 된다.

isFlagged라는 명시적인 함수를 사용해 FLAGGED라는 상수를 감춰도 좋겠다.

val gameBoard = arrayListOf<Cell>()
val STATUS_VALUE = 0
val FLAGGED = 0

fun getFlaggedCells(): List<Cell> {
val flaggedCells = arrayListOf<Cell>()
for (cell in gameBoard) {
if (cell.isFlagged) {
flaggedCells.add(cell)
}
}
return flaggedCells
}

class Cell(val isFlagged: Boolean = false) {
}

이렇게 개선되었다.

- 그릇된 정보를 피하라

프로그래머는 코드에 그릇된 단서를 남겨서는 안된다. 또한 나름대로 널리 쓰이는 의미 있는 단어를 다른 의미로 사용해도 안된다.

예를 들어 hp,aix, sco는 변수 이름으로 적합하지 않다. 유닉스나 유닉스 변종을 가리키는 이름이기 때문이다.

여러계정을 묶을때 실제로 List가 아니면 accountList라 명명하지 않는다. 프로그래머에게 List라는 단어는 특수한 의미다.

계정을 담는 컨테이너가 실제 List가 아니라면 그릇된 정보를 제공하는 셈이다.

하나의 모듈에서

XYXControllerForEfficientHandlingOfStrings

XYXControllerForEfficientStorageOfStrings

두개의 단어는 엄청 비슷하다. 유사한 개념은 유사한 표기법을 사용한다.

또한 비슷한 개념이라 자동완성기능을 통해 두개의 후보목록으로 뜬다면 엄청나게 유용해진다.

- 의미있게 구분하라

fun copyChar(a1 : CharArray , a2 : CharArray){
for(i in 0 until a1.size){
a2[i] = a1[i]
}
}
a1, a2가 아닌 source destination을 사용한다면 코드 읽기가 더 쉬워진다.

불용어를 추가한 이름 역시 아무런 정보도 제공하지 못한다. \*\*\*\*

(a an the Info , Data)

Product 라는 클래스가 있다고 가정하면 다른 클래스를 ProductInfo, ProductData라고 부른다면 개념은 구분하지 않은채 이름만 달리한 경우이다.

의미가 분명하게 다르다면 사용해도 되지만 zork와 theZork라 이름지어서는 안된다.

또한 불용어는 중복이라고 한다.

variable 이라는 단어 혹은 table 등 이런 불용어를 써서

Name과 NameString 중 Name자체가 다른 타입이 될 수 있는 가능성이 없다. 따라서 그릇된 정보를 피하라 규칙을 위한하게 된다.

Customer 라는 클래스와 CustomerObject라는 클래스를 발견한다고 해도 차이를 느끼기 어렵다.

moneyAmount 와 money

customerInfo와 customer

accountData와 account

theMessage 와 message

두개의 구분이 안된다. 읽는 사람이 차이를 알도록 이름 지어라

class DtaRcrd102{
private val genymdhms = Date()
private val modymdhms = Date()
}
class Customer{
private val generationTimestamp = Date()
private val modificationTimeStamp = Date()
}
두개의 이름을 본다면 위에꺼에 비해 아래의 변수명이 더 명확하지 않은가?

- 검색하기 쉬운 이름을 사용하라

MAX_CLASSES_PER_STUDENT 는 grep을 이용해 찾기 쉽지만 7은 까다롭다 7이 들어가는 다른 파일도 검색되기 때문이다.

따라서

var s = 0
var t = arrayOf(0)
for(j in 0..34){
s += (t[j] \* 4) /5
}

val realDaysPerIdealDay = 4
val WORK_DAYS_PER_WEEKS = 5
val NUMBER_OF_TASKS = 34
for(j in 0..NUMBER_OF_TASKS){
val realTaskDays = taskEstimate[j] \* realDaysPerIdealDay

    val realTaskWeeks = (realTaskDays / WORK_DAYS_PER_WEEKS)
    sum += realTaskWeeks

}
위에에서는 5로 검색해야하지만 아래에서는 WORK를 검색한다면 검색이 된다. 이렇게 쉬운 단어를 이용해 숫자가 아닌 문자를 검색하게 해야한다.

-인코딩을 피하라

인코딩과 헝가리안 표기법은 자제하라.

굳이 부담을 안해도 이름에 인코딩할 정보는 많다.

PhoneNumber phoneString
타입은 바뀌어도 이름은 바뀌지 않는다.

멤버변수 접두어
m\_이라는 접두어를 붙여서 변수를 만들필요도 없다.

--인터페이스 클래스와 구현클래스

인터페이스에는 IShapeFactory I라는 이름의 접두어를 붙이지 않고 구현클래스에 ShapeFactoryImp 나 CShapeFactory가 I를 인터페이스에 붙이는것(IShapeFactory)보다 낫다.

- 자신의 기억력을 자랑하지 마라

루프는 i,j,k 그 이외것은 사용하지 말고, Url을 r과같이 사용하지 말아라. 남들이 이해하기 쉬운 코드를 만들어라

- 클래스 이름

명사나 명사구를 이용하라

-메서드이름

동사나 동사구가 적합하다. postPayment, deletePage, save 등이 좋은 예 접근자 변경자 조건자는 get set is를 붙인다.

Complex fulCrumPoint = Complex.FromRealNumber(23.0)

Complex fulCrumPoint = new Complex(23.0);

위의 코드가 아래의 코드보다 더 좋다.

-기발한 이름은 피하라

프로그래머가 재치를 발휘해 구어체나 속어를 사용하는데 의도를 분명하고 솔직하게 표현해야한다.

-한 개념에 한 단어를 사용하라

어떤건 DeviceManager를 쓴다던지 어떤거는 ProtocolController 라던지 Controller와 Manager라는 단어를 혼용해서 쓰는건 좋지않다.

일관성있는 단어를 사용해야한다.

- 말장난을 하지마라

한 단어를 두 가지 목적으로 사용하지 마라. add라는 메서드가 생겼는데

기존의 add는 덧셈을 위해 썼다고 보면 새 add메서드는 집합에 값 하나를 추가한다.

새로운것과 기존 메서드와 맥락이 다르다. 그러므로 insrert나 append 라는 이름이 적당하다. add라고 부른다면 말장난과 다름이 없다.

- 해법영역에서 가져온 이름을 사용해라

코드읽을사람도 프로그래머이다. 기술개념에는 기술이름이 가장 적합한 선택이다.

- 문제영역에서 가져온 이름을 사용하라

적절하 프로그래머 용어가 없다면 문제 영역에서 이름을 가져와야한다.

- 의미있는 맥락을 추가하라

firstName , lastName, street, houseNumber, city, state, zipcode 라는 변수가 있다면 주소라는것을 알 수 있다.

하지만 state 라는 변수 하나만 사용한다면 이게 주소의 일부라는것을 알 수 가 없다.

따라서 addrFirstName , addrLastName, addrState 라 쓰면 맥락이 분명해지고 주소라는것을 알 수 있다.

-불필요한 맥락을 없애라

고급 휘발유 충전소라는 어플리케이션을 짤때

GSD(Gas Station Deluxe) 로 시작하면 바람직 하지 못하다. 또한 일반적으로 짧은이름이 긴이름보다 좋다.

물론 의미가 분명한 경우에 한해서이다. 이름에 불필요한 맥락을 추가 하지 않도록 주의해야한다.

마치며

위와같이 의미있고 다른 프로그래머가 보더라도 무슨 의도의 이름인지 한눈에 드러올 수 있는 이름의 변수명을 짜도록 노력해보자

---

### 3장

오늘은 클린코드 3장 함수에 대해 포스팅 해보려고 합니다.

프로그래밍의 초창기에는 루틴과 서브루틴으로 나누었다고 한다. 루틴은 한 함수를 동작하는것이고 서브루틴은 그 루틴에서 또 다른 루틴을 실행시킨것을 말한다. 이런 함수를 작성하면서 의도를 분명하게 표현하지 않으면 내용의 정보를 파악하기 어렵다. 어떻게 처음읽는 사람이 직관적으로 파악하게 만들 수 있을까?

### 작게만들어라

함수를 만드는 규칙은 작고 더 작게 만드는것이다. 저자는 20~ 3000천줄의 코드를 작성해본 결과 작은함수가 좋다고 말한다.

그렇다면 얼마나 짧은것이 좋다는 것일까?

함수의 길이는 최대한(4줄이하) 적게 만들어라.

// 함수를 작게 만들어라

```
public static String renderPageWithSetupsAndTeardowns(
PageData pageData, boolean isSuite) throws Exception {
if (isTestPage(pageData))
includeSetupAndTeardownPages(pageDataf isSuite);
return pageData.getHtml();
}
```

위와 같은 코드로 코드를 직관적이고 코드 줄 수는 줄이는것이 마땅하다고 한다.

### 블록과 들여쓰기

위에서 말하고자 하는건 if / else문 / while 문중 들어가는 블록은 한 줄 이어야 한다는 의미다.

블록안에 호출하는 함수이름을 적절하게 지으면 코드를 이해하기 쉬워진다. 즉 중첨구조가 생길만큼의 함수크기를 가지지 말고

들여쓰기 수준은 1단 2단을 넘으면 안된다. 그래야 함수를 읽기 쉬워진다.

### 함수는 한가지만해라

함수의 동작은 한가지만을 해야한다. 하지만 여기서 말하는 한가지만을 알기가 어렵다고 생각될 수 도 있다. 여기서 말하는건

지정된 함수 이름 아래에서 추상화 수준이 하나인 단계만을 수행한다면 한가지 작업을 하는것이다. ...... 함수의 한가지 동작 여부판단 1

우리가 함수를 만드는 이유는 큰 개념을 다음 추상화 수준에서 여러 단계로 나눠 수행하기 위해서인것이기 때문에 위의 코드는 한가지의 작업을 수행하는것이다.

단순히 다른 표현이 아니라 의미 있는 이름으로 다른 함수를 추출할 수 있다면 그 함수는 여러작업을 하는셈이다.

...... 함수의 한가지 동작 여부판단 2

### 함수당 추상화 수준은 하나로

함수가 한가지 작업을 하려면 함수 내의 모든 문장의 추상화 수준이 동일해야한다. 근본개념과 세부사항을 뒤섞기 시작하면 나도 모르게 함수에 세부사항들을 점점 추가하게 된다.

### 위에서 아래로 코드읽기(내려가기 규칙)

코드는 위에서 아래로 이야기처럼 읽혀야 좋다고 한다.

### switch문

스위치문은 여러개의 동작을 관리하기 때문에 작게 만들기 어렵다. 하지만 스위치문을 저차원 클래스에 숨기고 절대 반복하지 않는방법이 있다.

다형성을 이용한다.

```
public Money calculatePay(Employee e)
throws InvalidEmplᄋyeeType {
switch (e.type) {
case COMMISSIONED:
return caleulateCommissionedPay(e);
case HOURLY:
return calculateHourlyPay(e);
case SALARIED:
return calculateSalariedPay(e);
default:
throw new InvalidEmployeeType(e.type);
}
}
```

위의 함수에는 몇가지의 문제가 있다.

1. 함수가 너무 길다.

2. 한가지의 작업만 수행하지 않는다.

3. SRP를 위반한다. (코드의 변경이유가 여럿이기 때문)

4. OCP 위반한다. (새 직원의 유형이 추가 될때마다 코드를 변경하기 때문)

더 큰 문제는 위와같은 코드를 무한정 존재한다는 것이다.

isPayday()

deliverPay()

위의 두개와 같은 모두 유해한 구조들 말이다.

이런 코드는 추상 팩토리를 통해 숨긴다.

```
public abstract class Employee {
public abstract boolean isPayday();
public abstract Money calculatePay();
public abstract void deliverPay(Money pay);
}

public interface EmployeeFactory {
public Employee makeEmployee(EmployeeRecord r) throws InvalidEmployeeType;
}

public class EmployeeFactorylmpl implements EmployeeFactory {

    public Employee makeEmployee(EmployeeReco rd r) throws InvalidEmployeeType {
        switch (r.type) {
            case COMMISSIONED:
                return new CommissionedEmployee(r);
            case HOURLY:
                return new HourlyEmployee(r);
            case SALARIED:
                ret니rn new SalariedEmployee(r);
            default:
                throw new InvalidEmp 'LoyeeType! r.type);
        }
    }

}

```

Employee를 가진 추상 클래스를 생성한 뒤,

factory 추상 팩토리를 생성하고 그것을 구현한 Impl 클래스를 만듭니다.

거기서 사용되는 switch는 다형적 객체를 생성하는것에 이용하고

그 객체들은 Employee 클래스를 상속받아 구현합니다.

이 코드는 위의 코드를 개선한 코드지만, 이런 규칙을 완벽하게 지키기는 어렵다고 합니다.

### 서술적인 이름을 사용하라.

좋은이름이 주는 가치는 강조해도 지나치지 않을 정도로 좋다. 코드를 읽으면서 짐작했던 기능을 각 루틴이 그대로 수행한다면 깨끗한 코드이다.

또한 한하지만 하는 작은 함수에 좋은 이름을 붙인다면 절반은 성공한 것이며, 함수가 작고 단순할 수록 서술적 이름을 고르기 쉬워진다.

그리고 이전 단원에서도 나왔듯이 일관적인 이름을 붙여야한다. include... include... 가 좋은 예이다.

### 함수 인수

함수의 가장 이상적인 인수는 적을수록 좋고 3항의 이상이면 피하는것이 좋고 4항 이상이면 특별한 이유가 필요하다.

인수는 어렵고 인수의 개념을 이해하기 어렵게 만든다.

### 많이쓰는 단항 형식

함수에 인수 한개를 넘기는 이유는 가장 크게 두가지이다.

1. 인수에 질문을 던지는 경우 (boolean fileExist)

2. 인수를 뭔가로 변환해 결과를 반환하는 경우

드물게는 함수형식의 이벤트까지 있고 세가지의 경우가 아니라면 단항함수는 가급적 피한다.

또한 함수의 인수로 StringBuffer를 넘기는 일을 비한다. 변환함수에서 출력인수를 사용하면 혼란을 일으킨다.

### 플래그인수

플래그인수는 부울값을 넘기게 되면 함수가 여러가지를 처리한다는 의미이다.

### 이항함수

인수가 2개는 1개보다 이해하기 어렵다. 불가피한 상황 즉 Point(x,y)와 같은 상황을 사용해야 하는 부분이 아니라면 위험이 따른다는 사실을 이해하고 가능하면 단항으로 변경해야한다.

### 삼항함수

인수가 3개는 2개보다 훨씬 이해하기 어렵다. 따라서

### 인수객체

인수가 2~3개가 필요하다면 독자적인 클래스 변수로 선언할 가능성을 짚어본다.

```
Circle makeCircle(double x, double y, double radius);
Circle makeCirele(Point center, double radius);
```

위는 개념을 잘 표현한것이다.

### 인수목록

때로는 인수가 가변적인 함수도 필요하다.

String.format 메서드가 좋은 예이다. 가변인수를 통해 리스트형 인수를 하나로 취급 할 수 있다.

### 동사와 키워드

함수의 의도나 인수의 순서와 의도를 제대로 표현하기 위해서는 좋은 함수 이름이 필수다.

단항함수는 함수와 인수가 동사/명사쌍을 이뤄야한다. ex write(name) 이름을 쓴다

더 좋은 표현방법은 writeFiled(name) 이름이 필드라는것을 알 수 있다.

함수이름에 키워드를 추가하면서 함수이름에 인수 이름을 넣는다

assertEquals 보단 assertExpectedEqualsActual(Expected, actual)이 더 좋다.

### 부수효과를 일으키지 마라

부수효과는 거짓말이다. 한가지를 하겠다는 약속해놓고 다른짓도 하는것이니까,

```
public class UserValidator {
private Cryptographer cryptographer;
public boolean checkPassword(St ring userName, String password) {
User user = UserGateway.findByName(userName);
if (user != User.NULL) {
String codedPhrase = user.getPhraseEncodedByPasswᄋrd();
String phrase = cryptographer.decrypt(codedPhrase, password);
if ("Valid Password" .equals(phrase)) {
Session.initialize();
return true;
}
}
return false;
}
}
```

여기서 문제되는 코드는 Session.initialize() 코드이다.

사용자는 checkPassword를 통해 비밀번호를 확인하는데 기존 세션정보를 지워버릴 위험이 생긴다.

따라서 **이 코드는 checkPasswordAndInitializeSession 이라는 이름이 훨씬 좋다. but 한가지의 규칙을 위반한다.**

### 출력인수

일반적으로 우리는 인수를 함수 입력으로 해석한다.

appendFooter(s) 라는 코드를 통해 무언가 s를 바닥글로 첨부할지 아니면 s에 바닥글을 첨부할지 모르지만 선언부를 보면 분명해진다.

public void appendFooter(StringBuffer report)

인수 s가 출력 인수라는 사실은 분명하지만 함수 선선부를 찾아보고 나서야 알게됐다.

객체지향에서는 출력인수가 불가피한 경우도 있었지만 객체지향 언어에서는 출력 인수를 사용할 필요가 거의 없다. 출력 인수로 사용하라고 설계한 변수가 바로 this이기 때문이다.

report.appendFooter() 형태로 호출하는것이 좋다.

### 명령과 조회를 분리하라.

함수는 뭔가를 수행하거나 뭔가를 답하거나 둘중 하나만을 해야한다

boolean set(String attribute, String value)

이 함수는 이름이 attribute인 속성을 찾아 value로 설정한 후 성공하면 true, 실패하면 false를 반환한다.

이코드는

if(set("username", "namget"))....

독자입장에서는 무슨뜻인지 모호하다.

if(attributeExist("username")){

setAttribute("username", "namget");

}

이러한 코드처럼 명령과 조회를 분리해서 혼란을 애초에 뿌리 뽑아야한다.

### 오류코드보다는 예외를 사용하라.

오류코드를 반환하는 방식은 명령/조회 분리 규칙을 미묘하게 위반하게 된다. if문에서 명령을 표현식으로 사용하기 쉬운탓이다.

오류 코드 대신에 예외 처리 코드를 사용하면 오류의 처리코드가 원래 코드에서 분리되서 코드가 깔끔해진다.

### try catch 블록 뽑아내기

try catch는 코드 구조에 혼란을 일으키며 정상동작과 오류 처리 동작을 뒤섞는다. 따라서 try/catch 블록을 별도 함수로 뽑아내는것이 좋다.

### 오류처리도 한가지 작업이다.

함수는 한가지 작업을 하고 오류처리도 한가지 작업에 속한다.

### Enum.java 의존성 자석

```
public enum Error {
OK,
INVALID,
N0_SUCH,
LOCKED,
0UT_0F_RES0URCES,
WAITING_FOR_EVENT;
}
```

위와같은 클래스는 의존석 자석이다. 다른클래스에서 Error enum을 import하면서 Error가 변경되면 다시 컴파일하고 배치해야한다.

따라서 오류코드 대신 예외를 사용하면 재컴파일/재배치 없이도 새 예외클래스를 추가할 수 있다.

### 반복하지마라

중복은 모든 악의 근원이다. 중복을 없앴더니 모듈 가독성이 크게 높아졌다. AOP나 COP는 모두 중복 제거 전략이다.

### 구조적 프로그래밍

모든 함수와 함수는 입구와 출구는 하나만 존재한다. 즉 return문이 하나여야 한다는 말이다.

break 혹은 continue나 goto는 절대로 안된다. 함수를 작게만든다면 return , break, continue를 여러차례 사요하면서 단일 입출구 규칙보다 의도를 표현하기 쉬워진다.

### 함수를 어떻게 짜죠?

함수는 처음에는 길고 복잡하고 들여쓰기 단계도 많고 중복된 루프도 많다. 인수 목록도 아주 길다.

이름은 즉흥적이고 코드는 중복된다. 하지만 코드를 테스트하는 단위케이스도 만들고 코드를 다듬고 함수를 만들고 이름을 바꾸고 중복을 제거한다.

메서드를 줄이고 순서를 바꾼다. 때론 전체클래스를 쪼갠다. 이후에는 규칙을 만족하는 함수가 얻어진다.

---

### 클린코드 4장 주석

개발을 하면서 모두들 주석을 다실거라 생각합니다. 잘 달린 주석은 그 어떤 정보보다 유용하고 이상한 주석은 더 이해하기 어렵게 만듭니다.

주석은 우리가 치밀하게 언어에 의도를 표현할 수 있다면 주석은 거의 필요없다고 말합니다. 코드를 표현할 능력이 충분하다면 주석은 거의 필요없다고 합니다.

```
private final String HTTP_DATE_REGEXP =
"[SMTWF][a-z]{2}\\,\\s[0-9]{2}\\s[J FMASOND][a-z]{2}\\sM+[0-9]{4}\\s[0-9]{2}\\:[0-9]{2}\\:[0-9]{2}\\sGMT";

private Response response;

private FitNesseContext context;

private FileResponder responder;

private Locale saveLocale;
```

아마도 HTTP_DATE_REGEXP 라는 상수를 만들고 주석 사이에 다른 인스턴스 변수를 추가했을 가능성이 농후하다. 프로그래머들은

주석을 엄격하게 관리해야 하고 복구성과 관련성과 정확성이 언제나 높아야 한다고 주장한다. 하지만 프로그래머에겐 절도가 필요하다고 한다.

주석을 쓸시간에 코드를 정리하고 표현력을 강화하는 방향으로 작성하여 애초에 주석이 필요 없는 방향으로 에너지를 쏟는다.

불필요한 주석은 아예 없는 주석보다 더 나쁘다.

주석은 나쁜코드를 보완하지 못한다.

코드에 주석을 추가하는 일반적인 이유는 코드품질이 나쁘기 때문이다.

코드의 의도를 표현하라

// 직원에게 복지 혜택을 받을 자격이 있는지 검사한다.

```
if ((employee.flags & HOURLY_FLAG) && (employee.age >65))
```

이런코드 말고

```
if (employee.isEligibleForFuUBenefits())
```

몇초만 더 생각하면 대다수의 의도를 표현 가능하다.

좋은주석

어떠한 주석은 필요하거나 유익하다. 정말로 중요한 주석을 살펴보자

1. 법적인 주석

회사의 소유권을 주장하는 주석들이다.

```
// Copyright (C) 2003,2004,2005 by Object Mentor, Inc. All rights reserved.

// GNU General Public License 버전 2 이상을 따르는 조건으로 배포한다.
```

2. 정보를 제공하는주석

```
//테스트 중인 Responder 인스턴스를 반환한다.

protected abstract Responder responderlnstance();

위와같은 주석이 유용하다 할지라도 가능하다면 함수 이름에 정보를 담는 편이 더 좋다.

responderBeingTested 라고 바꾸면 주석이 필요없어 진다고 한다.

// kk:mm:ss EEE, MMM dd, yyyy 형식이다.

Pattern timeMatcher = Pattern.compile(

"\\d*:\\d*:\\d* \\W*# \\w* \\d*, \\d\*");
```

시간과 날짜를 뜻하는것을 설명한다. 이런코드는 시각과 날짜를 변환하는 클래스를 만들어 코드를 옮기면 더 좋고 깔끔하다.

3. 의도를 설명하는 주석

때때로 주석은 구현을 이해학 도와주는 선을 넘어서 의도까지 설명해준다고 한다.

4. 의미를 명료하게 밝히는 주석

때때로 모호한 인수나 반환값은 그 의미를 읽기 좋게 하면 이해하기 쉬워진다고 한다.

```
assertTrue(a.compareTo(a) == 0) ； // a == a
```

이런 주석들은 도움이 되지만 혹여나 잘못된 주석을 달아놓을수도 있고, 검증하기 쉽지 않다.

5. 결과를 경고하는 주석

// 여유시간이 충분하지 않다면 실행하지 마시오

@Ignore 속성을 이용해 테스트 케이스를 꺼버릴 수 있다. 따라서 @Ignore("실행이 너무 오래걸린다") 라고 쓴다.

```
public static SimpleDateFormat makeStandardHttpDateFormat()

{

// SimpleDateFormat은 스레드에 안전하지 못하다.

// 따라서 각 인스턴스를 독립적으로 생성해야 한다.

SimpleDateFormat df = new SimpleDateFormat("EEE# dd MMN yyyy HH:mm:ss z");

df.setTimeZone(TimeZone.getTimeZone("GMT"));

return df;

}
```

프로그램 효율을 높이기 위해 정적 초기화 함수를 사용하려던 열성적인 프로그래머가 주석 덕분에 실수를 면할 수 있다.

//(이펙티브 자바에서 나오는 자주 사용해서 초기화하는 인스턴스의 경우 정적 초기화를 통해 생성한다)

6. TODO 주석

앞으로 할일을 //TODO 주석으로 남겨두면 좋다.

7. 중요성을 강조하는 주석

```
String listltemContent = match.group(3).trim();
// 여기서 trim은 정말 중요하다. trim 함수는 문자열에서 시작 공백을 제거한다.
// 문자열에 시작 공백이 있으면 다른 문자열로 인식되기 때문이다.
new ListltemWidget(this,listltemContent, this.level + 1);
return buildList(text.substring(match.end())); 8. 공개 API에서 Javadocs
```

설명이 잘 된 공개 API는 참으로 유용하다.

나쁜주석

대다수의 주석은 이 범주에 속한다고 한다. 허술한 코드의 지탱과 엉성한 코드의 변명과 미숙한 결정을 합리화하는 독백이다.

1. 주절거리는 주석

특별한 이유 없이 의무감으로 혹은 프로세스에서 하라고 하니까 하는것.

즉 이런 주석이다.

// 속성파일이 없다면 기본값을 모두 메모리로 읽어들였다는 의미다.

저자에게만 의미있고 나머지에게는 의미가 전해지지 않는 주석이다.

2. 같은 이야기를 중복하는 주석

```
//this .closed 가 true 일 때 반환되는 유틸리티 메서드다.
//타임아웃에 도달하면 예외를 던진다.
public synchronized void waitForClose(finaI long timeoutMillis)
throws Exception {
if (!closed) {
wait(timeoutMillis);
if (!closed)
throw new Exception("MockResponseSender could not be closed");
}
}
```

위와 같은 주석을 달은 목적은 무엇이며 이 주석은 코드보다 더 좋은 정보를 제공하지 못한다.

3. 오해할 여지가 있는 주석

의도는 좋았어도 딱 맞을정도로 엄밀하게 주석을 달지 못하는것.

4. 의무적으로 다는 주석

모든 함수에 JavaDocs를 달거나 모든 변수에 주석을 달아야 한다는 규칙은 어리석다고 한다.

5. 이력을 기록하는 주석

모듈을 편집할때마다 모듈 첫 머리에 주석을 추가하는 주석들

6. 있으나 마나 한 주석

```
// 기본생성자

// 월중 일자

private void startSending() {
try {
doSending();
} catch (SocketException e) {
// 정상. 누군가 요청을 멈췄다.
} catch (Exception e) {
try {
response.add(ErrorResponder.makeExceptionString(e));
response.closeAll();
} catch (Exception el) {
// 이게 뭐야!
}
}
}
```

위에껀 괜찮았지만 아래꺼는 의미없는 주석이다.

이전 회사에서 "이게뭐야"와 같은 로그를 작성하는것을 봤었다. 그런 로그를 볼때마다 작성하나 마나인 로그를 왜 해뒀는지

아직도 의문이였는데, 이책에서 속 시원하게 말해준다.

7. 무서운 잡음

때론 Javadocs도 잡음이다.

```
/** The name. \*/
private String name;
/** The version. _/
private String version;
/\*\* The licenceName. _/
private String licenceName;
/\*_ The version. _/
private String info;
```

실제 저자가 어디서 가져온 코드와 주석인데 마지막 부분에 심지어 잘라넣기를 해서 version이라는 주석을 넣었다

이런 주석은 이익을 얻을만한 내용이 없다.

8. 함수나 변수로 표현할 수 있다면 주석을 달지 마라.

9. 위치를 표시하는 주석

//Actions //////////////////////////

이 주석과 같이 /는 제거해야한다. 하지만 너무 자주 사용하지 않으면 괜찮다고 한다

10. 닫는 괄호에 다는 주석

// while end

// try

11. 공로를 돌리거나 저자를 표시하는 주석

// 릭이 추가함

12. 주석으로 처리한코드

13. html 주석

14. 전역 정보

15. 너무 많은 정보

16. 모호한 관계

/\*\*

- 모든 픽셀을 담을 만큼 충분한 배열로 시작한다(여기에 필터 바이트를 더한다) .
- 그리고 헤더 정보를 위해 200바이트를 더한다.

```
  */
  this.pngBytes =new byte[((this.width +1)*this.height \*3)+200];
```

17. 함수의 헤더

---

오늘은 클린코드 5장 형식에 대해 포스팅 해보려고 합니다.

형식을 맞추는 목적

돌아가는 코드가 개발자의 1차적인 의무라 여길지도 모르지만 코드는 후에 코드의 품질에 영향을 미친다.

따라서 오랜시간 흔적을 더 이상 찾아보기 어려울 정도로 코드가 바뀌어도 구현스타일과 가독성은 유지보수 용이성과 확장성에 영향을 미친다.

원할한 소통을 장려하는 코드형식

1. 적절한 행 길이를 유지하라.

-대략적으로 500줄을 넘기지 않고 200줄 정도인 파일로도 커다란 시스템을 구축 가능하다.

2. 신문기사처럼 작성하라.

- 신문기사처럼 독자가 위에서 아래로 최상단에는 요약하는 표제와 읽어가면서 디테일한 세부사항들이 나오게 한다.

이처럼 소스파일도 신문기사와 비슷하게 이름은 간단하면서 설명이 가능하도록 짓는다.

3. 개념은 빈행으로 분리하라.

- 함수와 함수사이에 한칸의 빈행을 두어 가독성을 높이자.

4.  세로밀집도

        public class ReporterConfig {

    /\*\*

- 리포터 리스너의 클래스 이름
  \*/
  private String m_className;
  /\*\*
- 리포터 리스너의 속성

```
  \*/
  private List<Property> m_properties = new ArrayList<Property>();
  public void addProperty(Property property) {
  m_properties.add(property);
  }
  public class ReporterConfig {
  private String m_className;
  private List<Property> m_properties = new ArrayList<Property>();
```

이 두 코드를 보고 위보다는 아래가 더 읽기 쉽고 한눈에 들어온다.

5. 수직거리

- 함수의 동작방식을 이해하려고 뺑뺑이 돈 기억이 있는가? 서로 다른 파일에 속하는 것이 아니면

서로 밀접한 개념을 가진다면 (연관성이 높다면) 세로로 가까이 두는것이 좋다.

6. 변수선언

- 변수는 사용하는 위치에 최대한 가까이 선언한다.

7. 인스턴스 변수

- 인스턴스 변수는 클래스 맨 처음에 선언한다. 변수간에 세로로 거리를 두지 않는다. 잘 설계한 클래스는 많은 클래스메서드가 인스턴스 변수를 사용하기 때문이다.

8. 종속함수

- 한 하수가 다른함수를 호출한다면 두 함수는 세로로 가까이 배치한다. 되도록 호출하는 함수를 호출 되는 함수보다 일찍 부른다.

a()를 호출하고, a()에 대한 내용이 바로 밑에 나오도록 말이다.

9. 개념적유사성

- 어떤 코드는 서로 끌어당긴다. 개념적인 친화도가 높기 떄문이다. 친화도가 높을수록 가까이 배치한다.

종속성 혹은 비슷한 개념적인 명명법이 비슷하고 기본기능이 유사한 것 들이다.

10. 가로형식 맞추기

- 한 행에는 120자 정도로 글자길이를 제한하자

11. 가로 공백과 밀집도

- 할당문에는 왼쪽 요소와 오른쪽 요소간의 공백을 줘서 나눈다. 연산자 우선순위를 강조하기 위해서도 공백을 사용한다.

12. 가로정렬

13. 들여쓰기

- 짧은문이라도 들여쓰기를 해라.

14. 팀규칙

- 팀규칙이라는 제목은 말장난이고 프로그래머라면 각자 선호하는 규칙이 존재한다. 또한 팀이라면 자신이 선호해야 할 규칙이 바로 팀규칙이다.

---

# 클린코드 6장 객체와 자료구조

변수를 private으로 하는 이유는 남들이 변수에 의존하지 않게 하기 위함이다.

### 자료의 추상화

```
public class Point {
public double x;
public double y;
}

public interface Point {
double getX();
double getY();
void setCartesian(double x, double y);
double getR();
double getTheta();
void setPolar(double r, double theta);
}
```

위의 포인트는 직교좌표계를 사용하는것을 알지만 아래꺼는 직교좌표계인지 극좌표계인지 알 길이 없다.

변수 사이에 함수라는 계층을 넣는다고 구현이 저절로 감춰지지는 않는다. 구현을 감추려면 추상화가 필요하다.

위와 아래중에는 아래쪽이 좋다.

```
public interface Vehicle {
double getFuelTankCapacityInGallons();
double getGallonsOfGasoline();
}

public interface Vehicle {
double getPercentFuelRemaining();
}
```

위의 인터페이스는 자동차 연료 상태를 구체적인 숫자값으로 알려주고, 아래는 자동차 연료 상태를 백분율이라는 추상적인 개념으로 알려준다.

위보다는 아래가 추상적인 개념으로 표현하는편이 좋다.

### 자료/객체 비대칭

```

public class Square {
public Point topLeft;
public double side;
}

public class Rectangle {
public Point topLeft;
public double height;
public double width;
}

public class Circle {
public Point center;
public double radius;
}

public class Geometry {
public final double PI = 3.141592653589793;

    public double area(Object shape) throws NoSuchShapeException {
        if (shape instanceof Square) {
            Square s = (Square) shape;
            return s.side * s.side;
        } else if (shape instanceof Rectangle) {
            Rectangle r = (Rectangle) shape;
            return r.height * r.width;
        } else if (shape instanceof Circle) {



            Circle c = (Circle) shape;
            return PI * c.radius * c.radius;
        } else {
            throw new NoSuchShapeException();
        }
    }

}
```

이 코드를 살펴보자

이코드에 둘레길이를 구하는 함수 perimeter() 함수를 추가하고 싶다면 도형클래스에는 아무런 영향없이 Geometry 코드만 수정하면 되고

하지만 여기서 새로운 도형을 추가하고 싶다면 Geometry 에 속한 함수를 모두 고쳐야한다.

```
public class Square implements Shape {
private Point topLeft;
private double side;

    public double area() {
        return side * side;
    }

}

public class Rectangle implements Shape {
private Point topLeft;
private double height;
private double width;

    public double area() {
        return height * width;
    }

}

public class Circle implements Shape {
private Point center;
private double radius;
public final double PI = 3.141592653589793;

    public double area() {
        return PI * radius * radius;
    }

}
```

하지만 이러한 코드는 geometry 클래스가 필요없어서 새 도형을 추가해도 기존 함수에 아무런 영향을 미치지 않는다.

하지만 새 함수를 추가하고 싶다면 도형클래스 전부를 고쳐야한다.

위쪽에서의 소스 코드와 아래쪽의 소스코드는 근본적으로 양분된다. 즉 상호 보환적인 특징과 사실상 반대인 것이다.

### 자료구조와 객체의 차이점

- 자료구조를 사용하는 절차적 코드는 기존 자료구조를 변경하지 않으면서 새 함수를 추가하기 쉽고

- 객체지향코드는 기존 함수를 변경하지 않으면서 새 클래스를 추가하기 쉽다.

즉 이 둘의 차이를 이해하는것이 중요하다.

새로운함수가 아니라 새로운 자료타입이 필요한경우 클래스와 객체지향기법이 적합하고,

새로운 자료타입이 아니라 새로운 함수가 필요한 경우도 생긴다. 이럴때는 자료구조와 절차적인 코드가 적합하다.

### 디미터의 규칙

클래스 C의 메서드 f는 다음과 같은 객체의 메서드만을 호출해야한다.

-클래스C

-f가 생성한 객체

-f 인수로 넘어온 객체

-C 인스턴스 변수에 저장된 객체

```
final String outputDir = ctxt.getOptions(),getScratchDir().getAbsolutePath();
```

### 기차충돌

여러 객체가 한줄로 이어진 기차처럼 보이기 때문에 기차충돌이라고 말한다.

```
Options opts = ctxt.getOptions();
File scratchDir = opts.getScratchDir();
final String outputDir = scratchDir.getAbsolutePath();
```

위으 코드는 이렇게 줄어야한다.

위에가 디미터를 위반하는지의 여부는 ctxt, Options, ScratchDir 객체인지 아니면 자료구조인지에 달렸다.

객체라면 내부 구조를 숨겨야 하므로 디미터 법칙을 위반한다.

### 잡종구조

이런 혼란으로 때때로 절반은 객체 절반은 자료구조인 잡종의 구조가 나온다.

````
ct```xt.getAbsolutePathOfSc ratchDirectoryOption();

ctx.getScratchDirectoryOption().getAbsolutePath()
````

첫번째는 ctx 객체에 공개해야 하는 메서드가 너무 많고 두번째는 객체가 아니라 자료구조를 반환한다고 가정한다.

둘다 별로란 말이다.

```
String outFile = outputDir + "/" + className.replace('.', '/') + ".class";
FileOutputStream tout = new FileOutputStream(outFile);
BufferedOutputStream bos = new B니fferedOutputStream(fout);
```

위의 코드를

```
BufferedOutputStream bos = ctxt.createScratchFileStream(classFileName);
```

아래의 코드로 만듬으로서 ctxt는 내부 구조를 드러내지 않으며 모듈에서 해당 함수는 자신이 몰라야 하는 여러 객체를 탐색할 필요없다.

따라서 디미터 법칙을 위반하지 않는다.

결론

객체는 동작을 공개하고 자료를 숨긴다. 따라서 기존 동작을 변경하지 않으면서 새 객체타입을 추가하기는 쉬운 반면

기존 객체에 새 동작을 추가하기는 어렵다. 자료구조는 별 다른 동작 없이 자료를 노출한다. 그래서 기존 자료구조에 새 동작을 추가하기는 쉬우나

기존 함수에 새 자료구조를 추가하기는 어렵다.

---

# 클린코드의 오류처리

깨끗한 코드와 오류처리에는 연관성이 있고 상당수의 코드기반은 전적으로 오류 처리 코드에 좌우된다.

오류처리는 중요하고 오류처리로 인해 프로그램 논리를 이해하기 어려워 진다면 깨긋한 코드라 부르기 어렵다.

### 오류코드보다 예외를 사용하라

if문을 통해 Device의 멈춤 강태를 확인하는 코드는 복잡해진다. 함수를 호출한 즉시 오류를 확인해야 하기 때문이다.

그래서 이 단계를 잊어버리기 쉽다. 그래서 오류가 발생하면 예외를 던지는것이 낫다.

그냥 try catch문을 통해 오류를 처리하는것이 낫다.

```
public void sendShutDown() {
try {
tryToShutDown();
} catch (DeviceShutDownError e) {
logger.log(e);
private void tryToShutDown () throws DeviceShutDownError {
DeviceHandle handle = getHandle(DEVl);
DeviceRecord record = retrieveDeviceRecord(handle);
pauseDevice(handle);
clearDeviceWorkQueue(handle);
closeDevice(handle);
}
}
}
```

### try-Catch-Finally 문부터 작성하라.

try-catch-finally문에서 try 블록에 들어가는 코드를 실행하면 어느 시점에서든 실행이 중단된 후 catch 블록으로 넘어 갈 수 있다.

### 미확인 예외를 사용하라.

확인된 예외는 OCP를 위반한다. 메서드에서 확인된 예외를 던졌는데 catch블록이 세 단계 위에 있다면 그 사이 메서드 모두가 선언부에 해당예외를 정의해야한다. 이 말은 하위단계 코드가 변경하면 상위단계 메서드 선언부를 고쳐야 한다는 말이다.

하나가 throws 절을 추가하면 호출하는 함수 모두가 try catch문을 통해 예외를 정의해야한다.

### 예외에 의미를 제공하라

오류메세지에 정보를 담아 예외와 함께 던진다.

### 호출자를 고려해 예외 클래스를 정의하라.

어플리케이션에서 오류를 정의할 때 프로그래머에게 가장 중요한 관심사는 오류를 잡아내는 방법이 되어야한다.

### 정상의 흐름을 반환하라.

### null을 반환하지 마라.

오류를 유발하는 행위는 null을 반환하는 습관이다. 컬렉션이라면 null이 아닌 빈값의 array라도 반환해라

### null을 전달하지 마라

메서드에서 null을 반환하는 방식도 나쁘지만 메서드로 null을 전달하는 방식은 더 나쁘다.

정상적인 인수로 null을 기대하는 api가 아니라면 메서드로 null을 전달하는 코드는 최대한 피한다.

대다수의 프로그래밍은 null을 적절하게 처리하는 방법이 없다 그래서 애초에 null을 넘기지 못하도록 하는것이 합리적이다.

---
