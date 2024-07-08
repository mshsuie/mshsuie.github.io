---
layout: single
title:  "Function Basics"
categories: "객체지향프로그래밍"
tag: [C++, OOP, CS]
toc: true
---
너무 씨쁠쁠 팡션? 사용 하지 마세요.

![Don't Use Functions](https://raw.githubusercontent.com/mshsuie/mshsuie.github.io/master/assets/images/dont_use_functions.jpeg)

## 1. Void functions

Void 함수도 인자를 가질 수 있습니다. 함수의 반환 타입이 void라 하더라도, 여전히 인자를 통해 데이터를 전달받아 처리할 수 있습니다.

## 2. Random number generator (랜덤 숫자 생성기)

### 2.1. rand()

`rand()` 함수는 인자를 받지 않으며, 0과 RAND_MAX 사이의 값을 반환합니다.

### 2.2. Scaling (스케일링)

랜덤 숫자를 더 작은 범위로 압축하는 방법입니다. 예를 들어:

```cpp
rand() % 6
```

위 코드는 0부터 5 사이의 값을 반환합니다.

### 2.3. Shifting (시프팅)

랜덤 숫자의 범위를 이동시키는 방법입니다. 예를 들어:

```cpp
rand() % 6 + 1
```

위 코드는 1부터 6 사이의 값을 반환합니다. 이는 주사위 굴리기에 해당합니다.

### 2.4. Seed 사용

랜덤 숫자의 시퀀스를 변경하기 위해 "seed"를 사용합니다.

```cpp
srand(seed_value);
```

`srand()` 함수는 하나의 인자를 받으며, 시드 값을 설정합니다. 예를 들어 시스템 시간을 시드로 사용하려면:

```cpp
srand(time(0));
```

`time()` 함수는 시스템 시간을 숫자 값으로 반환하며, <ctime> 라이브러리에 포함되어 있습니다.

### 2.5. 예제

```cpp
(RAND_MAX – rand())/static_cast<double>(RAND_MAX) // 0.0~1.0 사이의 double

rand() % 6 + 1 // 1~6 사이의 int

rand() % 10 + 10 // 10~20 사이의 int
```

## 3. Function Declaration (함수 선언)

함수 선언은 컴파일러에게 함수에 대한 정보를 제공합니다. 이를 프로토타입이라고도 합니다.

```cpp
<return_type> FnName(<formal-parameter-list>);

double totalCost(int numberParameter, double priceParameter);
double totalCost(int, double); // 이렇게만 해도 되지만 파라미터 이름을 쓰는 것이 좋습니다.
```

함수 선언은 주로 `main()` 함수의 선언 공간이나 `main()` 함수 위의 전역 공간에 위치합니다.

## 4. Function Definition (함수 정의)

함수 정의는 실제 구현을 의미합니다. 이는 보통 `main()` 함수 이후에 작성합니다.

```cpp
double totalCost(int numberParameter, double priceParameter)
{
    const double TAXRATE = 0.05;
    double subTotal;
    subTotal = priceParameter * numberParameter;
    return (subTotal + subTotal * TAXRATE);
}
```

## 5. Function Call (함수 호출)

함수 호출은 제어를 함수로 전달합니다. 실제 인자(actual arguments)는 함수 호출 시 전달되는 실제 데이터입니다.

```cpp
bill = totalCost(number, price);
```

## 6. 파라미터와 아규먼트

파라미터(parameter)는 함수 선언 시 형식적 데이터 조각이고, 아규먼트(argument)는 함수 호출 시 전달되는 실제 데이터입니다.

## 7. Global declarations (전역 선언)

상수의 경우 전역 선언이 일반적입니다.

```cpp
const double TAXRATE = 0.05;
```

전역으로 선언하여 모든 함수에서 해당 상수를 사용할 수 있도록 합니다.

---

읽어주셔서 감사합니당.

다음 포스팅에서는 제가 가장 헷갈렸던 부분인 overloading에 대해 학습해보겠습니다!
