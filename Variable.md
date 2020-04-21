## 변수

### 변수란 무엇인가? 왜 필요한가?

- 변수는 데이터를 관리하기 위한 핵심 개념

- 애플리케이션은 데이터를 다룬다.  
- 보통 데이터를 **입력(input) ->  출력(output)**

```js
	10     +     20
// 좌변  연산자  우변 // 좌변가 우변의 숫자 값 = 피연산자
```

연산을 수행하기 위해서는 먼저 연산자의 좌변과 우변의 숫자 값 (= 피연산자) 를 기억해야 한다.



*컴퓨터는 메모리를 사용해 데이터를 기억한다*

**여기서 메모리란?**

=> 데이터를 저장할 수 있는 메모리 셀들의 집합체. 셀 하나의 크기는 1byte (8bit) 이며 컴퓨터는 셀의 크기, 즉 1byte 단위로 데이터를 저장(write)하거나 읽어(read)들인다. 컴퓨터는 **모든 데이터를 2진수로 처리한다.** 따라서 메모리에 저장되는 데이터는 종류와 상관없이 2진수다. 각각의 셀은 고유의 메모리주소를 갖는다. 메모리 주소는 공간의 위치를 나타내며 0부터 시작하여 메모리 크기만큼 정수로 표현된다. 

+++

위의 예제에서 

`10 + 20` 은 연산 결과가 필요하고 이를 사용해 무엇인가를 하겠다는 의도가 있었을텐데 연산결과인 30을 재사용할 수가 없다.  즉 연산 결과 30을 재사용하고 싶다면 메모리의 주소를 통해 결과 30이 저장된 메모리 공간에 직접 접근하여야 한다. 하지만 메모리에 직접접근하는 것은 치명적인 오류가 발생할 수도 있기 때문에 허용하지 않으며, 프로그래밍 언어를 기억하고 싶은 값을 메모리에 저장하고 저장된 값을 읽어 들여 재사용하기 위해서는 `변수`라는 메커니즘을 제공, 사용한다.



#### 변수 : 하나의 값을 저장하기 위해 확보한 메모리 공간 자체 또는 그 메모리 공간을 식별하기 위해 붙인 이름 (값의 위치를 가리키는 상징적인 이름)
