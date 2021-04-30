## Don't Repeat Yourself

: 반복하지 마라

- 드라이는 특정한 지식, 의도 로직 등이 다양한 곳에서 다양한 형태로 반복되어지는 것을 피하자

## WET(Write Everything Twice)

: 모든 걸 두번 씩 작성

> DRY is about the duplication of knowledge, of intent. It's about expressing the same thing in two different places, possibly in two totally

> Every piece of knowledge must have a single, umambiguous, authoritative representation within a system by the Pragmatic Programmer

- 단 한곳에서 명확하고 신뢰할 수 있도록 존재해야 함.

> 코드, 기능, 로직이 반복되는 것을 피하자!

> 드라이하게 로직을 형성시켜야, 추후 유지보수에서 한곳만을 겨냥해서 유지보수하더라도 문제가 없게 된다.!, 재사용성도 높아지고 한 군데서만 볼 수 있다.

- 코드 예시

```JS
function greetings(user){
    return `Hi ${user.firstName} ${user.lastName}`;
}

function goodbye(user){
    return `See you next time ${user.firstName} ${user.lastName}`;
}
```

> 두 코드의 중복이 있어서 모드 수정해야 한다.

```JS
function greetings(user){
    return `Hi ${user.fullName()}`;
}

function goodbye(user){
    return `See you next time ${user.fullName()}`;
}

class User{
    fullName(){
        return `${this.firstName} ${this.lastName}`;
    }
}
```

> 이렇게 공통적으로 운영하게 되는 경우, 유지보수성, 재사용성 측면에서 매우 유리해진다.

- Quiz : 드라이한가요?

```JS
function validateBody(body){
    if(!body.id){
        throw new Error('Validation failed. The attribute id is missing. ')
    }
    if(!body.name){
        throw new Error('Validation failed. The attribute name is missing');
    }

    if(!body.count){
        throw new Error('Validation failed. Thre attribute count is missing.');
    }
}
```

- 중복은 있지만 한 가지의 로직을 처리하고 있고, 이 로직이 다른 곳에서 중복적으로 발생하고 있지 않기 때문에 드라이라고 볼 수 없음.
- 로직, 지식 의도, 비즈니스로직 이 모든 것들이 중복되지 않도록 조금 더 광범위한 측면이 있음

```JS
function validateBody(body){
    const attributes = ['id','name','count'];
    attributes.forEach(attribute => {
        if(!body[attribute]) {
            throw new Error(
                `Validation failed. The attribute "${attribute}" is missing.`
            );
        }
    });
}
```

## KiSS(Keep It Simple, Stupid)

> Most systems work best if they are kept simple rather than made complicated; therefoer, simplicity should be a key goal in design and unnecessary complexity should be avoided. - Kelly Johnson

- **Code** : 코드를 누구나 이해할 수 있고 심플하고 간결하게
- **function**: 함수의 이름, 매개변수를 한번에 이해할 수 있도록 한 가지의 기능을 갖는 함수를
- **class** : 한가지의 책임을 갖는 클래스를 만드느 것
- **View** :뷰를 담당하는 UI에서는 비즈니스 로직을 넣지 말고 최대한 심플하고 멍청하게 UI에 관련된 로직들만 담당하고 있어야 함.
- **Service** : 여러가지 기능을 복합적으로 담당하는 하나의 큰 서비스를 만들기 보다는 단 하나의 기능을 담당하는 개별적인 서비스
- **System** : 이를 통해서 KISS를 지향하는 시스템이 만들어지는 것임

### Code

```JS
function getFirst(array, isEven){
    return array.find(x => (isEven ? x % 2 === 0 : x % 2 ! == 0));
}
```

> 보다 직관적으로 구분하기!

```JS
function getFirstOdd(array){
    return array.find(x=>x%2 !== 0);
}
function getFirstEven(array){
    return array.find(x=>x%2 === 0);
}
```

### Function

```JS
function updateAndPring(rawData){
    // prep data...
    // more code ...
    db.update(rawData);
    // get printer...
    /// more code ...
    printer.print(data);
}
```

> 함수를 개별적인 기능으로

```JS
function update(rawData){
    //prpe data...
    db.update(rawData);
    // more code ...
    return data;
}

function print(data){
    // get printer...
    // more code ...
    printer.print(data);
}
```

### Class

```JS
class UserOrderService{
    userDb;
    orderDb;
    paymentClient;
    processUserOrder(userId, orderId){
        const user = userDb.select(/*Query*/);
        if(!user){
            throw Error('...');
        }
        const order = orderDb.select(/*db query*/);
        if(!order){
            throw Error('...');
        }
        paymentClient
            .connect(/*url*/);
            .then(/*process payment*/);
            .catch(/*retry*/);
        orderDb.updateOrder(order, PAID);
    }
}
```

> 서비스별로 구분되는 것이 매우 중요하다!

```JS
class UserService{
    userDb;
    getUser(){
        return userDb.select(/*db query*/);
    }
}

class OrderService{
    orderDb;
    createOrder(user, product){}
    getOrder(orderId){
        return orderDb.select(/*db query*/);
    }
}

class PaymentService{
    paymentClient;
    proecessPayment(orderRequest){
        return payementClient
            .connect(/*url*/)
            .then(/*process payment*/)
            .catch(/*retry*/);
    }
}
```

### View

```JS
class LoginView {
    display(){
        //display view..
    }
    onLoginButtonClick(){
        fetch('https://server.com')
            .tehn(data => data.json())
            .then(data => {
                if(data.token) {
                    localStorage.setItem('TOKEN', data.token);
                    // updatae UI elements
                }
                else {
                    // ...
                }
            })
            .catch(error => {
                if(error.statusCode === 500){
                    // retry fetch?
                } else if (error.statusCode === 400) {
                    // handle an error
                }
                // show error message
            });
    }
}
```

> UI를 담당하는 클래스에는 UI를 담당하는 로직만 잇어야 한다!
> 사용자 데이터 관련 로직은 있으면 안된다!
> 최대한 심플하고 멍청하게 만드는 것이 중요함!

```JS
class LoginView {
    constructor(usePresneter){
        this.userPresenter = userPresenter;
    }

    display(){
        // display view..
    }

    onLoginButtonClick(){
        this.userPresenter
            .login()
            .then(result => {
                //update text UI element with result.diplayMessage
                // update button UI element with result.buttonText
            });
    }
}

class UserPresenter {
    userService;
    login(){
        this.userService
            .login()
            .then(result => {
                iif(result.success) {
                    localStorage.setItem('TOKEN', result.token);
                    return{
                        displayMessage: result.message,
                        buttonText : 'Go Home',
                    };
                } else {
                    return {
                        displayMessage : 'Unable to login',
                        buttonText : 'OK',
                    };
                }
            })
            .catch(error => {
                //Something really went wrong!
            });
    }
}

```

# YAGNI(You Ain't Gonna Need It)

- right feature, build right -> cost of carry, cost of delay
- right feature, build wrong -> cost of carry, cost of delay, cost of repair

- wrong feature -> -> cost of carry, cost of delay, cost of repair, cost of building

1. 필요하지 않는 기능
2. 사용하지 않는 기능
3. 지나치게 미래지향적인 기능

너무 지나치게 만들지는 말자!
(깨끗하게, 변경이 쉽게, 유지보수에 용이하게 만들자!)

```Javascript
function deleteUser(id, softDelete = false) {
    if (softDelete){
        //don't delete from db but only mark as deleted.
        return this._softDelete(id);
    } //-> 이 코드는 미래에 필요하지도 않을 기능이라 비추이다!
    return db.removeById(id);
}
```

1. YAGNI를 통해서 불필요한 요소를 제거하고,
2. KISS를 통해서 심플함을 추가하면 퀄티티 있는 코드를 만들 수 있음.
