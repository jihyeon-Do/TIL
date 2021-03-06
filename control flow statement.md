## 제어문

### 1. 블록문

블록문 : 0개 이상의 문을 중괄호로 묶은 것으로 코드 블록 또는 블록이라고 부르기도 한다.

- 하나의 실행단위로 취급
- 제어문이나 함수를 정의할 때 사용하는 것이 일반적이다.
- 블록문 끝에는 세미콜론을 붙이지 않는다.

### 2. 조건문

조건문 : 주어진 조건식의 평가 결과에 따라 코드 블럭의 실행을 결정한다.

- 불리언 값으로 평가될 수 있는 표현식이다.
- if else 와 switch문을 제공한다.

	#### 	2.1 if else문

​	주어진 조건식의(불리언 값으로 평가될 수 있는 표현식) 평가결과 즉, 논리적 참 또는 거짓에 따라 실행할 코드블	록을 결정한다.

​	조건식의 평가결과 (불리언 값으로 평가되어야 한다.)

​	참(true)일 경우 :  `if `문 다음의 코드 블록이 실행

​	거짓(false) 일 경우 : `else`문 다음의 코드 블록이 실행된다.

	- 조건식이 불리언 값이 아닐경우 : 암묵적으로 데이터 타입이 불리언값으로 강제 변환되어 코드 블록을 결정한	  다.
	- 조건식을 추가하여 조건에 따라 실행될 코드 블록을 늘리고 싶으면 else if 문을 사용한다.
	- `else if `문과 `else`문은 옵션이다.
	- `if`문과 `else`문은 2번이상 사용할 수 없지만 `else if` 문은 여러 번 사용할 수 있다.
	- 만약 코드 블록 내의 문이 하나뿐이라면 중괄호를 생략할 수 있다.

```js
var num = 2;
var kind;

if(num > 0) 		kind = '양수';
else if (num < 0) 	kind = '음수';
else 				kind = '영';

consol.log(kind); //양수
```

- 대부분의 if else문은 삼항 조건 연산자로 바꿔 쓸 수 있다.

```js
var x = 2;
var result;
// x가 짝수이면 짝수를 반환하고 홀수이면 홀수를 반환한다.

if(x % 2) { // 2 % 2는 0이다. 이때 0은 false로 암묵적 강제 변환된다.
	result = '홀수';
} else {
	result = '짝수';
}

console.log(result); // 짝수
```

​	이걸 삼항조건연산자로 바꿔 쓴다면

```js
var x = 2;
// x가 짝수이면 문자열 짝수를 반환하고 홀수이면 홀수를 반환한다.

var result = x % 2 ? '홀수' : '짝수';

console.log(result); // 짝수 
```

​	위 예제는 두가지 경우의 수 ('홀수' 또는 '짝수')를 갖는 경우이다. 만약 세가지 경우의 수(양수, 음수, 영)를 갖는 	경우는 아래와 같이 바꿔 쓸 수 있다.

```js
var num = 2;

var kind = num ? (num > 0 ? '양수' : '음수') : '영';

console.log(kind); // 양수
```

​	`num > 0 ? '양수' : '음수'`는 표현식이다. 

​	삼항조건연산자 = 값으로 표현되는 표현식 = 변수에 할당할 수 있다.

​	if else = 표현식이 아닌 문 = 변수에 할당할 수 없다.

	#### 	2.2 switch문

​	 switch 문 : 주어진 표현식을 평가하여 그 값과 일치하는 표현식을 갖는 case문으로 실행 순서를 이동시킨다.

	- switch문의 표현식과 일치하는 표현식을 갖는 case 문이 없다면 실행순서는 default문으로 이동한다.
	- default문도 옵션이다.
	- 불리언 값보다는 숫자값인 경우가 더 많다. 
	- 다양한 상황에 따라 실행할 코드 블록을 결정할 때 사용한다.
	- case문 마다 break문을 사용해 주어야 한다.
	- default문에는 break문이 필요없다. ( break문 : 코드블록에서 탈출하는 역할 )

### 3. 반복문

반복문 : 조건식의 평가 결과가 참인 경우 코드 블럭을 실행한다. 그 후 조건식을 다시 검사하여 여전히 참인 경우
코드블럭을 다시 실행한다. 조건이 거짓일 때까지 반복

#### 	3.1 for문

​	조건식이 거짓으로 판별될때까지 코드블록을 반복실행

```js
for (변수 선언문 또는 할당문; 조건식; 증감식) {
	조건식이 참인 경우 반복 실행될 문;
}
```

	1. for문을 실행하면 가장 먼저 변수 `선언문`이 실행된다. 변수 `선언문은` 단 한번만 실행된다.
 	2. 변수 `선언문`의 실행이 종료되면 `조건식`으로 이동
 	3. `조건식`의 평가 결과가 true면 코드 블록으로 이동하여 실행, `증감문`으로 실행순서가 이동하는것이 아니다.
 	4. `코드 블록` 실행이 종료되면 이때 `증감식`으로 실행 순서 이동. `증감문`으로실행 순서가 이동하는 것이 아니라 `코드 블록`으로 실행 순서가 이동하는 것에 주의
 	5. `증감식` 실행이 종료되면 다시 `조건식`으로 실행 순서가 이동한다.
     - 변수` 선언문`으로 실행 순서가 이동하는 것이 아니라 `조건식`으로 실행 순서가 이동한다.
     - 변수 `선언문`은 단 한번만 실행된다.
	6. `조건식` 평가 결과가 true 이면 실행 순서가 `코드블록`으로 다시 이동하여 실행된다.
	7. `코드 블록` 실행이 종료되면 다시 `조건식`으로 실행순서가 이동한다. 
	8. `조건식`의 평가 결과가 false이므로 for문의 실행이 종료된다.



- for문의 변수 선언문, 조건식, 증감식은 모두 옵션
- for문 내에 for문을 중첩해 사용할 수 있다. 

```js
for (var i = 1; i < 7; i++) {
    for (var j = 1; j < 7; j++) {
        if( i + j === 6 ) console.log(`[${i}, ${j}]`);
    }
}
```

```js
// 출력결과
[1, 5]
[2, 4]
[3, 3]
[4, 2]
[5, 1]
```

#### 	3.2 while문

​	while문 : 조건식의 평가 결과가 참이면 코드 블록을 계속해서 반복실행. 조건문의 평가결과가 거짓이 되면 실행	을 종료

- 만약 조건식의 평가 결과가 불리언 값이 아니면 불리언 값으로 강제 변환
- 논리적 참, 거짓 구별

```js
var count = 0;

while (count < 3) {
    console.log(count);
    count++;
}
```

- 조건식의 평가 결과가 언제나 참이면 무한루프가 된다.
- 무한루프를 탈출하려면 코드블럭내에 if문으로 탈출 조건을 만들고 break문으로 코드 블럭을 탈출한다.

```js
var count = 0;

while(true) {
	console.log(count);
    count++;
   if (count === 3) break;
}
```

#### 	3.3 do while문

​	do while문 : 코드 블록을 먼저 실행하고 조건식을 평가한다. 코드블록은 무조건 한번 이상 실행된다!

```js
var count = 0;

// count가 3보다 작을 때까지 코드 블록을 계속 반복 실행한다.
do {
	console.log(count);
    count++;
} while (count < 3); // 0 1 2
```



### 4. break문

코드 블록을 탈출한다. 

레이블문, 반복문 ( for, for in, for of, while, do while ) 또는 switch문의 코드 블록을 탈출한다. 

레이블 문, 반복문, switch문의 코드 블록 이외에 break문을 사용하면 syntaxError가 발생한다

- 레이블 문이란 식별자가 붙은 문을 말한다.

```js
foo: console.log('foo')
// foo라는 레이블 식별자가 붙은 레이블 문
```

- 레이블 문은 프로그램의 실행순서를 제어하기 위해 사용한다. 
- 레이블 문을 탈출하려면 break문에 레이블 식별자를 지정한다.

```js
//foo라는 식별자가 붙은 레이블 블록문
foo: {
	console.log(1);
    break foo; // foo 레이블 블록문을 탈출한다.
    console.log(2);
}
console.log('Done!');
```

- 중첩된 for문의 내부 for문에서 break문을 실행하면 내부 for문을 탈출하여 외부 for문으로 진입한다.
  이때 내부 for문이 아닌 외부 for문을 탈출하려면 레이블 문을 사용한다.

```js
outer: for (var i = 0; i < 3; i++) {
	for (var j = 0; j < 3; j++) {
        if(i + j === 3) break outer;
        console.log('inner' + j);
    }
}

console.log('Done!');
```

- break문은 레이블 문 뿐만이 아니라 반복문, switch문에서도 사용할 수 있다. 이경우에는 break문에 레이블 식별자를 지정하지 않는다.
- 반복문을 더이상 진행하지 않아도 될 때 불필요한 반복을 회피할 수 있어 유용하다.

```js
var string = 'Hello World.';
var search = 'l';
var index;

//문자열은 유사배열이므로 for문으로 순회할 수 있다.
for (var i = 0; i < string.length; i++) {
    if(string[i] === search) {
        index = i;
        break; // 반복문을 탈출한다.
    }
}
console.log(index); // 2
```



### 5. continue문

continue 문 : 반복문의 코드 블록 실행을 현 지점에서 중단하고 반복문의 증감식으로 이동한다. break문처럼 반복문을 탈출하지는 않는다. 

```js
var string = 'Hello World.';
var search = 'l';
var count = 0;

// 문자열은 유사배열이므로 for 문으로 순회할 수 있다.
for(var i = 0; i < string.length; i++) {
    // 'l'이 아니면 현 지점에서 실행을 중단하고 반복문의 증감식으로 이동한다.
    if(string[i]) !== search) countinue;
    count++; // continue 문이 실행되면 이 문은 실행되지 않는다.
}

console.log(count); // 3
```





