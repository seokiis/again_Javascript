# again_Javascript

## 목차

1. [작명 가이드](#작명-가이드)
2. [for in 주의사항](#for-in주의사항)
3. [문자열과 배열 사이](#문자열과-배열-사이)
4. [변수 Var](#변수-Var)

## 작명 가이드

변수를 만들 때 이름을 아무렇게나 지으면 안 됩니다. 이름을 지을 때는 아래와 같이 몇 가지 룰을 따라주세요!

### 꼭 지켜야 하는 룰 (지키지 않으면 오류)

(1) JavaScript 식별자는 '문자(a-z, A-Z)', '밑줄(\_)' 혹은 '달러 기호($)'로 시작해야 합니다. 두 번째 글자부터는 '숫자(0-9)'도 가능합니다.

(2) '대문자'와 '소문자'는 구별합니다. myname과 myName은 다른 이름입니다.

(3) '예약어(JavaScript가 찜해놓은 단어)'는 사용하면 안 됩니다. 예를 들어서 if, for, let 같은 것들이 있습니다. 강의를 듣다 보면 어떤 예약어가 있는지 차차 알게 되실 겁니다.

### 지키면 좋은 룰 (더 좋은 스타일을 위해)

위에 나와 있는 꼭 지켜야 하는 룰들만 지켜도 오류 없이 코드가 돌아갈 것입니다. 하지만 돌아가기만 한다고 다 좋은 코드는 아닙니다. 프로그래밍은 혼자 하는 게 아니기 때문이죠. 여러 사람과 협업할 때 여럿이 일관성 있는 코드를 쓰기 위해서는 어느 정도의 약속이 필요합니다.

나물좀줘! = 나 물 좀 줘? 나물 좀 줘?<br>
사랑해보고싶어! = 사랑해 보고 싶어? 사랑 해보고 싶어?

똑같은 글이지만 띄어쓰기라는 약속을 지켜주면 우리가 전달하고자 하는 문장의 의미를 조금 더 명확하게 할 수 있겠죠? 우리가 코드를 작성할 때도 마찬가지입니다. 코드를 작성하는 일은 여러 사람들과의 협업이기도 하면서 스스로와의 소통이기도 합니다. 우리는 이런 소통을 원활히 하기 위해서 아래와 같은 약속들을 함께 지킵시다!

(1) 의미 없는 이름은 좋지 않습니다.

```jsx
let a, b, c, d;
```

향후 복잡한 프로그램을 짜게 되면 변수와 함수를 여기저기서 적절히 활용해야 하는데, 이름이 a, b, c, d처럼 의미 없이 설정되어 있으면 어떤 값을 저장해뒀는지 찾기도 어렵고 활용하기도 어렵습니다. 또한 프로그램의 가독성이 떨어져서 나중에 스스로 프로그램을 살펴볼 때, 그리고 공동 작업을 할 때 매우 불편한 상황이 발생합니다. 그래서 프로그래밍 초반부터 적절한 이름을 짓는 습관을 들이는 것이 좋습니다!

(2) 너무 추상적인 이름은 좋지 않습니다.

```jsx
let name; // 너무 추상적인 이름
```

상황에 따라 그냥 name이라는 변수명이 적합한 상황도 있을 수 있겠지만, 긴 프로그램을 쓰다 보면 다양한 '이름'들이 있기 때문에 name은 너무 추상적일 수 있습니다. 그럴 때는 조금 더 구체적인 이름으로 이해하기 쉽게 만들어주세요!

(3) 모든 변수 이름은 'camelCase'로 쓰는 것이 좋습니다.

변수명에는 띄어쓰기가 불가능하기 때문에, 띄어쓰기 역할을 대신 할 무언가가 필요합니다. 그중 하나가 'camelCase'라는 것인데요. 첫 번째 글자는 소문자로 하고, 띄어쓰기가 있는 각 단어의 첫 문자를 대문자로 표기하는 방식입니다.

```jsx
let bad_variable_name; // 비추천 방식
let goodVariableName; // 추천 방식
```

중간중간의 대문자가 낙타(camel)의 혹처럼 생겨서 camelCase라고 부릅니다.

사실은 이 밖에도 더 좋은 코드 스타일을 위해 다양한 약속들을 만들어 볼 수 있는데요. 이런 약속들을 스타일 가이드혹은 코딩 컨벤션이라고 부릅니다.

-   [Airbnb의 자바스크립트 스타일 가이드](https://github.com/ParkSB/javascript-style-guide)
-   [Standard JS](https://standardjs.com/rules-kokr.html)

### 참고하기

코드 에디터는 코드를 쉽게 작성할 수 있게 자동화된 기능들이 있습니다. 그래서 만약 자동화된 기능이 우리가 지키려고 하는 스타일 가이드와 일치하지 않는다면 에디터에서 몇 가지 설정을 바꿔주어야 하는데요.
코드 에디터마다 다르겠지만 일반적으로 들여쓰기(indentation) 부분은 신경을 써야 하는 경우가 많습니다.

여러 자바스크립트 스타일 가이드를 살펴보면 대부분 공통적으로 들여쓰기를 space 2칸으로 사용하도록 권장하는 데요.

먼저 VSCode를 실행하고, 설정창(Settings)을 열어주세요.
단축키 Ctrl + , (맥에서는 Cmd + ,)입니다.

Step1: 상단의 검색창에서 editor tab이라고 검색한 다음.
Step2: Editor: Detect Indentation 은 체크 해제해 주세요.
Step3: Editor: Tab Size 는 2로 변경해 주세요.
Step4: 기본 값이라 변경할 필요는 없지만 Editor: Insert Spaces 부분이 체크 되어 있는지만 한 번 확인해주세요.

이렇게 되면 들여쓰기 관련된 설정은 모두 완료됐습니다! 간단하죠?
그런데 기존에 작성한 코드에는 바로 반영이 되지 않을 텐데요.

기존에 작성했던 파일로 돌아가서 단축키 Ctrl + a (맥에서는 Cmd + a)로 전체선택 해주시고
마우스 오른쪽 클릭으로 나타나는 메뉴에서 Fomat Document을 클릭해 주세요.
단축키는 Shift + Alt + F (맥에서는 Shift + Option + F)입니다.

## for in주의사항

이 코드를 한번 보세요.

```jsx
let myObject = {
    2: "알고리즘의 정석",
    3: "컴퓨터 개론",
    1: "자바스크립트 프로그래밍 기초",
};

for (let key in myObject) {
    console.log(myObject[key]);
}
```

```
자바스크립트 프로그래밍 기초
알고리즘의 정석
컴퓨터 개론
```

분명히 객체를 작성할 때는 알고리즘의 정석, 컴퓨터 개론, 자바스크립트 프로그래밍 기초 순서로 작성했는데, 뭔가 우리가 작성한 순서와 다르게 for in 반복문이 수행되었습니다.

왜 이렇게 된 걸까요!? 객체의 프로퍼티는 어떤 순서로 정렬이 되는 걸까요!?

반복문을 사용할 때 이 순서를 알지 못하면, 방금처럼 의도치 않은 결과를 얻게 될 수도 있습니다. 상황에 따라서는 치명적인 오류로 이어질 수도 있겠죠? 그럼 객체의 프로퍼티 네임의 예외사항과 함께 객체의 정렬 방식에 대해서 조금 더 살펴봅시다.

### 숫자형(양수) 프로퍼티 네임

흔한 경우는 아니라서, 처음 객체를 배우는 레슨에서 다루진 않았지만 사실 프로퍼티 네임에는 숫자형(양수)을 작성해서 사용할 수도 있습니다.

```jsx
let myObject = {
    300: "정수",
    1.2: "소수",
};
```

다만 실제로 사용될 때는 문자열로 형 변환이 되어 사용되는데요.

```jsx
let myObject = {
    300: "정수",
    1.2: "소수",
};

for (let key in myObject) {
    console.log(`${key}의 자료형은 ${typeof key}입니다.`);
}
```

```
300의 자료형은 string입니다.
1.2의 자료형은 string입니다.
```

이렇게 for in 문을 활용해서 각 프로퍼티 네임들의 자료형을 확인해보면, 모두 string, 문자열이 출력되는걸 볼 수 있습니다.

그리고 이렇게 예외적인 파라미터 네임은 접근할 때도 대괄호표기법으로만 접근이 가능합니다.

```jsx
let myObject = {
  300: '정수',
  1.2: '소수',
};

console.log(myObject['300']);
console.log(myObject['1.2']);
console.log(myObject.300); // Error!
console.log(myObject.1.2); // Error!
```

### 정수형 프로퍼티 네임

객체의 프로퍼티 네임으로 숫자형을 그대로 사용할 수도 있다는 점을 살펴봤는데요.
for in문을 사용할 때 주의해야 할 순간은 바로 정수형 프로퍼티 네임이 있을 때 입니다.
**객체는 정수형 프로퍼티 네임을 오름차순으로 먼저 정렬하고, 나머지 프로퍼티들은 추가한 순서대로 정렬하는 특징이 있습니다.**

```jsx
let myObject = {
    3: "정수3",
    name: "codeit",
    1: "정수1",
    birthDay: "2017.5.17",
    2: "정수2",
};

for (let key in myObject) {
    console.log(key);
}
```

```
1
2
3
name
birthDay
```

분명히 3, name, 1, birthday, 2순서로 프로퍼티가 작성되었음에도 불구하고, for in문이 실행될 때는 오름차순으로 정렬이 되어 출력이 된 모습을 확인할 수 있습니다.
굳이 for문을 그대로 작성하지 않고도 그냥 콘솔에 myObject를 콘솔에 출력만 해봐도

```
{1: "정수1", 2: "정수2", 3: "정수3", name: "codeit", birthDay: "2017.5.17"}
```

객체가 정수형 프로퍼티에 한해서 오름차순으로 정렬이 되고 나머지는 추가한 순서대로 정렬이 되는 걸 확인할 수 있죠?
처음에 살펴봤던 것처럼 정수형 프로퍼티에 따옴표를 붙여 문자열처럼 만들더라도, 정렬방식은 동일하게 처리됩니다.

```jsx
let myObject = {
    3: "정수3",
    name: "codeit",
    1: "정수1",
    birthDay: "2017.5.17",
    2: "정수2",
};

for (let key in myObject) {
    console.log(key);
}
```

```
1
2
3
name
birthDay
```

자동으로 정렬되는 특성이 장점처럼 느껴질 수도 있지만 대부분의 경우에는 의도치 않은 결과를 가져올 수도 있기 때문에, 일반적으로 정수형 프로퍼티는 잘 사용되지 않는데요.

그래서 불가피한 경우에는 이런 객체의 정렬방식을 잘 이해한 상태에서 사용하고, 가급적 명확한 의미가 있는 프로퍼티 네임을 사용하시는걸 권장합니다.

## 문자열과 배열 사이

문자열도 생각해보면 '문자' + '열'이기 때문에 배열과 비슷한 부분들이 많습니다.

### 비슷한 점

배열과 문자열 모두 length프로퍼티를 가지고 있고, 대괄호 표기법으로 각 요소에 접근할 수 있습니다.

또한, 꽤 많은 메소드들이 배열과 문자열 모두 동일하게 사용됩니다. 배열을 다룰 때 유용한 for..of문을 문자열에 활용할 수도 있습니다.

```jsx
let myString = "Codeit";

for (let str of myString) {
    console.log(str);
}
```

```
C
o
d
e
i
t
```

### mutable vs. immutable

가장 중요한 차이는 **배열은 'mutable(바뀔 수 있는)' 자료형**인 반면 **문자열은 'immutable(바뀔 수 없는)' 자료형**이라는 것입니다.

배열은 요소에 접근해서 할당연산자를 통해 요소를 수정할 수 있었죠?

문자열은 한 번 할당된 값을 수정할 수 없습니다. 다르게 표현해서, 변수에 할당된 문자열을 바꾸고 싶다면, 일부를 바꾸는 게 아니라 새로운 문자열을 지정해주어야 한다는 것이죠.

```jsx
// 배열은 mutable
let myArray = ["C", "o", "d", "e", "i", "t"];
myArray[0] = "B";
console.log(myArray);

// 문자열은 immutable
let myString = "Codeit";
myString[0] = "B";
console.log(myString);
```

```
["B", "o", "d", "e", "i", "t"]
Codeit
```

다시 한번 되돌아보면, 문자열이 가진 메소드들은 모두 return 값들을 활용하고, 본래의 문자열 값을 수정하지 않습니다.
같은 의미에서 문자열에 splice 같은 메소드들은 사용할 수 없겠죠?

## 변수 Var

자바스크립트에는 variable의 약자를 따서 var라는 키워드로 변수를 선언할 때가 있었습니다.
자바스크립트에 변수를 선언하는 방식은 처음부터 let과 const가 아니였던 것이죠!

그래서 오래된 프로젝트들이나 혹은 자바스크립트의 정보들을 정리해둔 조금 오랜 시간이 지난 블로그들을 살펴보면 심심찮게 var라는 키워드를 만나볼 수가 있는데요.

### 중복 선언 허용

var 키워드로 선언한 변수의 첫 번째 문제는, let과 const와는 다르게 **중복 선언이 가능**하다는 겁니다.
똑같은 이름으로 변수를 한 번 더 선언하게 되면, 에러가 발생하는 것이 아니라 그냥 기존의 변수를 덮어써 버리는 것이죠. let키워드로 선언한 변수에 값을 재할당하는 것과는 엄연히 다릅니다.

```jsx
var myVariable = "codeit";
console.log(myVariable);
var myVariable = "Codeit!";
console.log(myVariable);
```

```
codeit
Codeit!
```

이렇게 변수가 중복선언이 되면, 길고 복잡한 코드를 작성할 때 실수를 할 가능성이 커지고, 상황에 따라서는 치명적인 오류가 발생할 수 있습니다.

### 함수 스코프

var 키워드 변수가 사라진 두 번째 문제는 **Scope의 문제**입니다.
let과 const 키워드로 선언한 변수는 if, for, function 등등 어떤 키워드와 관계없이 코드 블록, 즉 {} 중괄호로 감싸진 부분을 기준으로 scope를 갖게 되지만, var 키워드로 선언한 변수는 scope가 function에서만 구분되어 있습니다.

```jsx
{
    let x = 3;
}

function myFunction() {
    let y = 4;
}

console.log(x);
console.log(y);
```

```
Uncaught ReferenceError: x is not defined
```

let이나 const 키워드의 경우에는 중괄호로 감싸진 경우라면 모두 중괄호 밖에서는 지역 변수에 접근할 수 없습니다.

```jsx
{
    var x = 3;
}

function myFunction() {
    var y = 4;
}

console.log(x);
console.log(y);
```

```
3
Uncaught ReferenceError: y is not defined
```

하지만 var 변수는 지역변수의 구분이 함수에만 있기 때문에 if, for, while, switch 등 다양한 상황에서 선언한 변수가 자칫, 전역변수의 역할을 하게 될 수도 있는 것이죠.

참고로 이렇게 함수를 기준으로만 적용되는 스코프를 함수 스코프, 코드 블록을 기준으로 적용되는 스코프를 블록 스코프라는 용어를 사용한다는 점도 참고해 주세요!

### 끌어올림 (Hoisting)

```jsx
console.log(myVariable);
let myVariable;
```

```
Uncaught ReferenceError: Cannot access 'myVariable' before initialization
```

let과 const로 선언한 변수는 선언되기 이전에 사용될 수 없습니다. 하지만, var 변수는 함수 스코프를 기준으로 선언되기 이전에도 변수에 접근이 가능한데요.

```jsx
console.log(myVariable);
var myVariable;
```

```
undefined
```

변수의 선언이 끌려 올라가서 마치, 2번째 줄과 첫 번째 줄이 바뀐 것처럼 동작하는 데요.

```jsx
console.log(myVariable);
var myVariable = 2;
console.log(myVariable);
```

```
undefined
2
```

하지만 이런 식으로 동작하는 방식은 코드의 흐름을 방해하기에 충분해 보이죠? 한 가지 주의해야 될 부분은, 함수를 선언할 때도 이 호이스팅이 적용됩니다.

```jsx
sayHi();

function sayHi() {
    console.log("hi");
}
```

```
hi
```

이런 현상은 함수를 한 번 선언하고 나면 어디서든 유연하게 사용할 수 있다는 장점이 있지만, 코드의 흐름에는 부정적인 영향을 끼칠 수 있습니다. 그래서 함수를 선언할 때는 가급적 코드 윗부분에 선언하거나, 호출을 항상 아래쪽에서 한다거나 나름대로 규칙을 세워서 코드를 작성하시기를 권장드립니다.
