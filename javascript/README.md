# Javascript

### 1. 변수(Variable)

변수란 상황에 따라서 변할 수 있는 값을 말한다. 다시말해 어떤 값에 대해서 이름(label)을 붙여준 것이 변수라고 이해하면 더 쉽다.

#### 변수의 선언

한번 선언한 변수를 다시 선언할 수 없다. myAge라는 값을 다시 선언해주면 에러가 발생한다.

`let myAge; // let을 이용해 myAge라는 변수를 선언`

#### 변수의 할당(assign)

여기서 =는 프로그래밍에서는 같다(equal)의 의미가 아닌 대입(assign)을 의미한다.

`myAge = '20'; //20이란 값을 myAge에 대입해줌, 이제 myAge는 20`

```javascript
let myAge = '20';
  선언    할당   
```

할당이 없는 변수는 undefined라는 값으로 출력되며 변수의 결과물은 다시 변수로 담을 수 있다. 변수명에는 공백을 금지하고 Camel case의 법칙에 따른다.

```javascript
//동일한 변수를 이용해 대입가능
let sum = 1;
sum = sum + 2;
sum = sum + 3;
sum = sum + 4;
```

수학적으로는 말이 안되는 과정이지만 오른쪽의 값을 왼쪽에 할당한다는 의미이므로 프로그래밍 상에서는 가능하다. 
sum이라는 변수를 할당해 줄 때 let을 한번만 사용한 것을 볼 수 있듯이 한번 선언한 변수는 다시 선언할 수 없다.

#### 변수의 타입

+ Number
+ String
+ Boolean
+ null
+ undefined


### 2. 조건문(conditional expression)

조건문은 어떠한 조건을 판별하는 기준을 만드는 것으로 조건으로는 반드시 비교연산자(comparison operator)가 필요하고 그 비교의 결과는 늘 boolean이어야 한다.

#### 비교연산자

```javascript
>    //미만
<    //초과
>=   //이하
<=   //이상
===  //같다
!==  //다르다 
```

==와 !=는 다른 타입의 변수를 엄밀히 비교하지 못하기 때문에 사용을 지양한다.

```javascript
'3' == 3  //true (string 3과 number 3을 비교했을 때 true가 return되는 오류가 발생)
'3' === 3 //false 
```

#### 조건문은 어떻게 쓸까?

조건에는 boolean으로 결과가 나오는 비교구문이 들어가야한다.

```javascript
if(조건1){
//조건1이 통과할 경우
} else if (조건2) {
//조건1이 통과하지 않고
//조건2가 통과할 경우
} else {
//모든 조건이 통과하지 않는 경우
}
```

#### 논리 연산자

두가지 조건이 한번에 적용되는 경우는 논리 연산자를 사용한다.

```javascript
isStudent && isFemale; //and연산자
isStudent || isFemale; //or연산자
!isStudent && isFemale; //not연산자 - truthy,falsy여부를 반전시킨다. 학생이 아니면서 여성일 때 true
```

```javascript
✔논리 연산자 not
!false //true
!(3>2) //false
!undefined //true
!'Hello' //false

✔논리 연산자 or
true||true
// true
true||false // true
false || false // false

✔논리 연산자 and
true && true // true
true && false //false
false && false // false
```

#### 기억해야 할 6가지 falsy 값

if문에서 false로 변환되므로 if구문이 실행되지 않는 경우

+ if(false)
+ if(null)
+ if(undefined)
+ if(0)
+ if(NaN)
+ if('') 빈스트링 즉, 값이 없는 문자열

### 3. 함수(function)

함수는 컴퓨터에게 일을 시키기 위한 지시사항의 묶음으로 입력(input)-함수(function)-출력(return)의 과정으로 이루어진다. 함수 이름과 입력(input)이 반드시 들어가야한다.

함수에서 사용하는 input값을 `매개변수(parameter)`라고 부른다.

```javascript
✔ 함수의 선언식
function myFunction(input){
//컴퓨터에게 시킬일
}

✔ 함수의 표현식 //변수를 이용해서 값을 계산하려고 할 때
let myFunction = function(input){
/컴퓨터에게 시킬일
}
let timeToGoHome = function(speed,distance){
let time = distance / speed;
console.log(time); //결과를 출력하는 것 
}
```

#### 함수의 실행

`전달인자(arguments)`와 함께 함수에 전달하여 함수를 실행한다.

함수 바깥으로 결과를 가져오려면 return값이 필요하다. 만약 아무것도 return 하지 않으면 함수 호출의 결과는 undefined로 나오게 된다.

```javascript
let timeToGoHome = function (speed, distance) {
let time = distance / speed ;
console.log(time);
}
let myTime = timeTOGoHome(20,100);
console.log(myTime); // undefined

function getAreaOfCircle(radius){
let pi = 3.141592;
let areaOfCircle = pi*radius*radius;
return areaOfCircle;
}
```

### 3. 배열(array)

배열은 순서가 있는 값으로 순서는 인덱스(index), 값은 요소(element)라고 칭한다. 배열의 인덱스는 0부터 번호를 매기며 인덱스를 통해서 배열의 값에 접근한다.

```javascript
let myNumber = [23,455,43,2];
myNumber[3]=43; //myNumber라는 배열의 2번째 인덱스를 조회 
myNumber[2]=200; //myNumber라는 배열의 3번째 인덱스 값을 변경

//배열 안에 배열을 넣을 수 있다.
let myNumber = [[23,45],[23,44],[44,24]];
//myNumber의 1번째 인덱스 값 
[23,44]
//myNumber의 1번째 인덱스의 0번째 값
myNumber[1][0]; //23
//배열의 길이를 알아낼 수 있다.
myNumber.**length**;//4

//배열의 제일 끝에 요소를 추가할 수 있다.
myNumber.**push**(96);

//배열의 마지막 요소를 삭제할 수 있다.
myNumber.**pop**(21);
```

### 4. 반복문(loop)

같거나 비슷한 코드를 여러번 실행시켜야 할 경우에 사용하는 구문

반복문을 만드는 과정 : 반복하는 내용을 먼저 코드로 작성하고, 조건을 코드로 작성한다.

```javascript
let sum=1;
sum = sum+2;
sum = sum+3;
sum = sum+4;
```

+ sum과 숫자(n)의 합을 sum에 대입하자. ➡ sum=sum+n;
+ 조건: n은 2부터 시작한다 ➡ let n=2;
+ n은 4가 될 때까지 반복한다. ➡ n<=4;
+ n은 1씩 증가한다. ➡ n=n+1;

#### for구문

```javascript
let sum = 1;
for(let n=2; n<=4; n=n+1) //반복할 조건을 `초기화`,`조건식`,`증감문` 순으로 넣어준다. {
sum = sum+n //반복할 내용을 중괄호 block안에 넣어준다. 
 }
console.log(sum);//10
```

#### 배열의 반복

배열과 반복문을 조합하는 경우가 많다.

```javascript
let myNum = [23,65,63,12];
for (let i=0; i<myNum.length; i++//증감연산자로 i=i+1과 같다) {
console.log(myNum[i]);
}

//myNum의 모든 요소를 누적해서 더하기 위해서 필요한 조건과 구문
let myNum = [10,20,40,10];
let sum = 0;
for(let n=0, n<myNumber.length, n++){
sum=sum+myNumber[n];
}
```




### 1. 변수

변수는 값을 담기 위해 이름을 붙인 상자. 변수는 컴퓨터 메모리에 일정한 크기의 영역으로 생성된다.

`var sum;`

변수를 선언하기만 하면 변수 안에는 정의되지 않았음을 뜻하는 undefined라는 값이 들어간다.

```javascript
var x;
console.log(x); // -> undefined
```

대입(=) 연산자를 사용하면 변수에 값을 대입할 수 있다.

`x = 2;`