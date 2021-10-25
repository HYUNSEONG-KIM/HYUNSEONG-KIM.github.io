---
layout: default
title: NC001:Error Analysis
parent: Numerical analysis and Computational physics
grand_parent: Books
nav_order: 1
use_math: true
---

## 오차 

### 정밀도와 정확도

### 오차의 전파

$$x \pm \delta x$$

### 실험에서의 오차

## 컴퓨터 계산의 정밀도
---

실제 컴퓨터는 정수 연산은 아주 훌륭하게 해냅니다. 정수 연산의 구현은 많은 계산 비용을 잡아먹지도 않고, 정확한 값을 계산해 낼 수 있는 구조로 이루어져 있습니다. 그러나 이제 실수의 연산으로 가면 이야기가 달라집니다. 실수 연산은 정수 연산에 비해 매우 많은 연산 비용을 요구합니다. 이 때문에, Arduino 같이 한정된 계산 용량을 가진 시스템에서 많은 실수 연산을 사용하면 경우, 전체 계산 속도가 급속도로 하락합니다. 이러한 경우 해당 값들을 밖으로 빼내어 Raspberry Pi와 같은 상대적으로 고성능인 기기에서 처리한 후 결과를 전송하는 것이 권장되고 있습니다. 요점은 컴퓨터의 실수 연산은 본질적으로 큰 연산 비용을 소모한다는 점입니다. 그리고 이에 더해 그 자체적으로 오류가 있습니다. 가장 간단하게, 공학 계산기나 컴퓨터로 $1$을 $3$으로 나누고 다시 $3$을 곱해봅시다, Wolfram language와 같은 symbolic 연산기능을 사용하면 $1$을 얻을 수 있지만, 공학 계산기, OS 내장 계산기, C, Python 등등에서 대부분 $0.999999 \dots $와 같은 값을 내놓습니다. 

컴퓨터의 실수의 표현은 **IEEE**에서 정한 표준을 사용합니다. **IEEE** 표준은 다음에서 확인가능 합니다.

이러한 오차로 인해 실제 계산 프로그램을 작성할 때, 실수 값의 비교는 정수와 다른 방법을 사용해야 합니다. 우리가 요구하는 지점까지의 정밀도가 같으면 이를 실질적으로 같다라고 두고 연산을 적용한다. 예로 $C$를 보면,

```C
#include <stdio.h>
#include <float.h>

int main()
{
    double a =1.0;
    double b= 1.0+10*DBL_EPSILON;
    
    printf("%f,%f\n",a,b);
    printf("Float epsilon compare: %d\n",(b-a)<FLT_EPSILON);
    printf("Double epsilon compare: %d\n",(b-a)<DBL_EPSILON);

    return 0;
}
```

다음은 위 프로그램의 결과값입니다. $C$에서는 `True` 값으로 `1`을, `False` 값으로 `1`을 사용합니다.

```
1.000000,1.000000
Float epsilon compare: 1
Double epsilon compare: 0
```


---


때문에 실수의 연산은 불필요할 경우 줄이는 것이 좋습니다. 많약 기본 정밀도 이상의 정밀도를 필요로 하는 계산프로그램을 작성한다면, 프로그램언어에서 제공하는 기초 수학 자료형이 아닌 별도의 방법을 구현해야 합니다. 예로 $C$에서 **GMPL** 라이브러리가 있습니다.

