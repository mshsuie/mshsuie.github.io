---
layout: single
title:  "Flow of Control"
categories: "객체지향프로그래밍"
tag: [C++, OOP, CS]
toc: true
---

지난 포스팅에 이어 C++ 기본 문법을 정리해보겠습니다.

C++의 흐름 제어를 바탕으로 다양한 조건문과 loop을 사용하여 프로그램을 더 유연하게 작성할 수 있습니다.


## 1. Precedence

연산자 우선순위를 이해하는 것은 매우 중요합니다. 특히 증가 연산자(increment operators)를 사용할 때 주의해야 합니다!

```cpp
(x > 1) && (y++) // 이 조건문이 거짓이라도 y가 증가할 수 있다.
```

### 1.1. Boolean

1. **0이 아닌 모든 값**은 참(True)으로 간주됩니다.
2. **0**은 거짓(False)으로 간주됩니다.

## 2. if-else

조건문은 프로그램의 흐름을 제어하는 중요한 도구입니다. if-else 문은 조건에 따라 다른 명령을 실행합니다.

### 2.1. 간단한 구문

```cpp
if (hrs > 40)
    grossPay = rate * 40 + 1.5 * rate * (hrs - 40);
else
    grossPay = rate * hrs;
```

### 2.2. 복합문 (compound statement)

```cpp
if (myScore > yourScore)
{
    cout << "win
";
    wager += 100;
}
else
{
    cout << "golf
";
    wager = 0;
}
```

### 2.3. else는 선택적입니다

else 구문은 필요하지 않을 때 생략할 수 있습니다.

### 2.4. 다중 조건문 (multiway)

```cpp
if (Boolean_expression_1)
    statement_1;
else if (Boolean_expression_2)
    statement_2;
else if (Boolean_expression_3)
    statement_3;
else
    Statement_for_나머지;
```

## 3. Switch

if문으로도 표현할 수 있지만, switch문이 더 편리할 때가 많습니다.

```cpp
switch (Controlling_expression)
{
    case constant_1:
        statement_1;
        break;
    case constant_2:
        statement_2;
        break;
    default:
        default_statement_sequence;
}
```

### 3.1. 실행은 break를 만날 때까지 계속됩니다 (execution falls thru until break)

```cpp
case 'A':
case 'a':
    cout << "Excellent: you got an 'A'!
";
    break;
case 'B':
case 'b':
    cout << "Good: you got a 'B'!
";
    break;
```

### 3.2. break를 사용하지 않으면 에러가 발생하지 않으므로 주의가 필요합니다

## 4. Conditional Operator

조건 연산자는 삼항 연산자(ternary operator)라고도 하며, if-else를 간단히 표현할 수 있습니다.

```cpp
if (n1 > n2)
    max = n1;
else
    max = n2;

// 위의 코드를 짧게 표현하면

max = (n1 > n2) ? n1 : n2;
```

## 5. Loops

loop은 코드 블록을 여러 번 실행할 수 있게 해줍니다. C++에는 세 가지 주요 loop이 있습니다: while, do-while, for.

### 5.1. while

while loop은 가장 유연한 loop입니다. 조건을 검사하고, 조건이 참인 동안 loop 본문을 실행합니다.

```cpp
count = 0; // Initialization
while (count < 3) // Loop Condition
{
    cout << "Hi "; // Loop Body
    count++; // Update expression
}
```

### 5.2. do-while

do-while loop은 적어도 한 번은 loop 본문을 실행합니다. 조건은 본문이 실행된 후에 검사됩니다.

```cpp
count = 0; // Initialization
do
{
    cout << "Hi "; // Loop Body
    count++; // Update expression
} while (count < 3); // Loop Condition

// body 3번 실행
```

### 5.3. for

for loop은 자연스러운 카운팅 loop입니다. 초기화, 조건 검사, 업데이트 표현식을 한 줄에 포함합니다.

```cpp
for (count=0; count<3; count++)
{
    cout << "Hi "; // Loop Body
}
// 3 times body 실행
```

### 5.4. loop 주의사항

1. while 문에 세미콜론을 바로 붙이면 {} 안의 코드가 실행되지 않습니다.
2. **break**;를 사용하면 즉시 loop을 종료합니다.
3. **continue**;를 사용하면 loop 본문의 나머지 부분을 건너뛰고 다음 반복을 시작합니다.

---

읽어주셔서 감사합니다.
다음 포스팅에서는 function에 대해 다루어보겠습니다.