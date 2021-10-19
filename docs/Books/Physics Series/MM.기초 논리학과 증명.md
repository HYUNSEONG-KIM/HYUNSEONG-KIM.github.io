---
layout: default
title: 기초 논리학과 증명
parent: Physics Series
nav_order: 1
permalink: /docs/Books/Physics_Series/Mathematical Methods/기초 논리학과 증명
---

이 단원에서는 기초적인 논리학과 증명에 대해 배운다. 수학을 공부할 때, 어떻게 정확히 타당한 수학적 논증(증명)을 만들어 내는지 이해하고 있어야한다. 이를 위해서는 논증에 사용되는 논리 규칙들과 명제들에 대한 공부가 먼저 선행되어야 한다. 논리 규칙들은 수학적 문장들의 의미를 좀 더 명료하게 하고, 이들에 대한 이해를 높여준다. 이 단원에서는 이를 위해 기초적인 명제/술어 논리학과 증명에 관해 다룰 것이다.

# 명제와 술어 논리

## 명제(Proposition)

**명제**(proposition)는 참/거짓을 **판정**할 수 있는 문장을 의미한다. 즉, 명제인 문장은 참이나 거짓 둘중 하나의 값을 가지게 된다. 이때, 둘 모두일 수는 없는데, 이러한 경우 판정할  수 없는 문장으로 명제가 아니게된다. 명제를 나타내는 변수를 **명제 변수**(proposition variable)라 부른다. 명제 변수는 일반적으로 소문자 ($p,q,r,s \dots$)를 사용한다. 

참/거짓을 진리값이라 하는 데, 일반적으로 참 (Truth)을 $\text{T}$, 거짓 (False)을 $\text{F}$로 표기한다. 

여러 명제들은 더 작은 명제들로 표현 될 수도 있다. 그러나, 더 작은 명제로 표현될 수 없는 명제도 존재하는 데, 이를 **원자 명제**(atomic proposition)라 한다. 이러한 명제들로 부터 새로운 명제들을 파생시킬수 있는데, 이렇게 만들어진 명제를 **복합 명제**(compound proposition), 기존 명제에 작용해 새로운 복합 명제를 만들어내는 것을 **논리 연산자**(logic operator)라 한다. 논리 연산자는 기존 명제에 새로운 의미를 연결한다고 해서 논리적 연결사(logical connective)라 표현을 쓰기도 한다. 이러한 명제들을 다루는 논리를 **명제 논리** (Propositional logic)이라 부른다.

논리 연산자를 소개하기에 앞서서 **진리표**(Truth table)를 소개하고 가자. 진리표는 어느 명제가 가질수 있는 진리 값을 모두 나열한 것으로 첫 행에는 표기할 명제들을, 아래 행에는 각 열의 첫번째 명제가 가질 수 있는 진리 값을 기술한다. 독립적인 명제들을 왼쪽에 오른쪽에 해당 명제들로 만들어진 복합 명제를 기술한다. 예를 들어서 두 개의 명제 $p, q$와 이 둘로 이루어진 복합 명제 $r$이 있다면, 다음과 같이 쓸 수 있다.

<center>

|$p$|$q$|$r$|
|:--:|:--:|:--:|
|T|T|-|
|T|F|-|
|F|T|-|
|F|F|-|

</center>

$r$이 있는 열의 각 행에는 $p,q$의 진리값에 따른 $r$의 진리값이 들어간다. 어느 한 복합 명제 $r$이 $p_1, p_2, p_3, \dots p_n$의 독립 명제들로 이루어져 있다면, 진리표는 총 $2^n+1$개의 행을 가지게 된다. [^진리표]따라서 진리표는 적은 독립 명제들을 가진 복합 명제의 판정에는 사용가능하지만, 많은 명제들을 가지고 있는 복합 명제의 판정에는 비효율적이다.

[^진리표]: 열은 최소 $n+1$에서 더 많아질 수도 있다. 복잡한 복합 명제는 하위 복합 명제를 중간열에 추가하기도 하기 때문이다.   

## 논리 연산자(Logic operator)

기초적인 논리 연산자에 **부정**(negation), **연언**(conjunction) 그리고 **선언**(disjunction)이 있다.

<table style="border-radius:8px;width:100%;">
<th style="text-align:center;background-color:rgb(0, 0, 0); color:white; border-top-left-radius: 10px;width:20%;">
Def</th>
<th style="text-align:left;">
부정 (Negation)</th>
<tr style="text-align:center;">
<td colspan="2">

명제 $p$에 대해, "$p$의 부정"은 $\neg p$로 표기하며, "$p$가 아닌 경우"를 의미한다. 
            
</td>
</tr>
</table>

<center>

|$p$|$\neg p$|
|:--:|:--:
|T|F|
|F|T|

</center>

부정 기호는 매우 다양하다. 정의에 쓰인 $\neg p$뿐만 아니라, $\sim p, !p, p', Np, -p, \overline{p}$들도 쓰인다. 단순히 $\text{not } p$로 표기하기도 한다. $\overline{p}$는 집합 기호에서 여집합이나 켤례 복소수의 표기에도 쓰이는 기호라 혼동의 우려가 있어 사용하지 않았다. $!p$는 프로그래밍 언어등에서 부정을 나타내는 데 흔히 쓰인다. 일반적으로 $NOT$ 연산자라 부른다.


<table style="border-radius:8px;width:100%;">
<th style="text-align:center;background-color:rgb(0, 0, 0); color:white; border-top-left-radius: 10px;width:20%;">
Def</th>
<th style="text-align:left;">
연언 (Conjuntion)</th>
<tr style="text-align:center;">
<td colspan="2">

명제 $p,q$에 대해, "$p,q$의 연언"은 $p \wedge q$로 표기하며, "$p$가 참이며, $q$도 참이다."를 의미한다. 
            
</td>
</tr>
</table>

<center>

|$p$|$q$|$p \wedge q$|
|:--:|:--:|:--:|
|T|T|T|
|T|F|F|
|F|T|F|
|F|F|F|

</center>

단순히, $p \text{ and } q$나 $p \& q$로 표기하기도 한다. 일반적으로 $AND$ 연산자라 부른다.

<table style="border-radius:8px;width:100%;">
<th style="text-align:center;background-color:rgb(0, 0, 0); color:white; border-top-left-radius: 10px;width:20%;">
Def</th>
<th style="text-align:left;">
선언 (disjuntion)</th>
<tr style="text-align:center;">
<td colspan="2">

명제 $p,q$에 대해, "$p,q$의 선언"은 $p \vee q$로 표기하며, "$p$가 참이거나 $q$가 참이다."를 의미한다. 
            
</td>
</tr>
</table>

<center>

|$p$|$q$|$p \vee q$|
|:--:|:--:|:--:|
|T|T|T|
|T|F|T|
|F|T|T|
|F|F|F|

</center>

단순히 $p \text{ or } q$로 표기하기도 한다. 일반적으로 "또는" 혹은 "or"로 번역하는 데, 논리학에서의 선언을 의미하는 "또는"과 "or"은 일상 언어에서의 의미와 차이가 있다. 일상 언어에서 해당 단어들은 **베타적**(exclusive) 의미를 가지고 있다. 예를 들어 "그 서버는 Windows이거나 Linux이다. "에서 "서버"는 Windows이면서 Linux일 수는 없다. 오직 한가지 경우만이 가능하다. 반면에, 위의 선언(disjunction)은 진리표에서 보이듯이 주어진 두 명제가 모두 참인 경우가 가능하다. 이러한 성질을 **포괄적**(inclusive)이라 부른다. 별도의 서술이 없을 경우 논리학에서 선언은 모두 포괄적으로 다루어진다. 베타적 의미의 선언은 따로 정의되어 있다. 일반적으로 $OR$ 연산자라 부른다.

<table style="border-radius:8px;width:100%;">
<th style="text-align:center;background-color:rgb(0, 0, 0); color:white; border-top-left-radius: 10px;width:20%;">
Def</th>
<th style="text-align:left;">
베타적 선언 (Exclusive disjunction)</th>
<tr style="text-align:center;">
<td colspan="2">

명제 $p,q$에 대해, "$p,q$의 베타적 선언"은 $p \oplus q$로 표기하며, "$p$나 $q$ 둘 중 하나만이 참이다."를 의미한다. 
            
</td>
</tr>
</table>

<center>

|$p$|$q$|$p \oplus q$|
|:--:|:--:|:--:|
|T|T|F|
|T|F|T|
|F|T|T|
|F|F|F|

</center>

$p \veebar q, p + q, p \text{ xor } q$로 쓰기도 한다. 별도의 베타적 선언 기호를 쓰지않고 포괄적 선언으로 표기할 수도 있다. 진리표를 기준으로 $p \oplus q$는 $(p \vee q) \wedge \neg(p \wedge q)$와 같다. 일반적으로 $XOR$ 연산자라 부른다.

### 조건문(Conditional Statement)

위의 기본 연산자들 외에 **조건문**이라는 방법으로 명제들을 결합할 수도 있다. 


<table style="border-radius:8px;width:100%;">
<th style="text-align:center;background-color:rgb(0, 0, 0); color:white; border-top-left-radius: 10px;width:20%;">
Def</th>
<th style="text-align:left;">
조건문 (Conditional statement)</th>
<tr style="text-align:center;">
<td colspan="2">

명제 $p,q$에 대해, 조건문 "$p \rightarrow q$"는 "만약, $p$이면, $q$이다."를 의미한다. $p \rightarrow q$는 $p$가 참인데, $q$가 거짓일 경우에 거짓이고, 나머지 경우에는 모두 참이다. $p \rightarrow q$에서 $p$는 전제(premise)라 하며, $q$는 결론(conclusion)이라 한다.
 
</td>
</tr>
</table>

<center>

|$p$|$q$|$p \rightarrow q$|
|:--:|:--:|:--:|
|T|T|T|
|T|F|F|
|F|T|T|
|F|F|T|

</center>
 
<!-- $p \rightarrow q$가 조건문이라 불리는 이유는 해당 명제가 참일 경우 $q$의 진리값이 $p$가 참인 조건 하에서 참이 되기 때문이다. -->  이 조건문을 나타내는 표현도 매우 다양한데 다음이 있다.

<center>

|$p \rightarrow q$| | | |
|:--:|:--:|:--:|:--:|
|if $p$, then $q$|if $p$, $q$|$p$ implies $q$| $p$ only if $q$|
|$p$ is sufficient for $q$|a necessary condtion for $p$ is $q$| ||
|$q$ if $p$| $q$ whenever $p$| $q$ when $p$| $q$ is necessary for $p$|
| a sufficient condition for $q$ is $p$| $q$ follows from $p$|$q$ unless $\neg p$|$ provided that $p$|

</center>

"$p$ only if $q$"란 표현이 조금 혼동이 올 수도 있는데, "$p \rightarrow q$"가 참임을 기본 전제로 두자, 이때, $q$가 참이 아니면, $p$도 절대로 참일 수 없다. $p$가 참이기 위해서는 $q$가 반드시 참이여만 한다. 때때로 "$p$ only if $q$"를 $q \rightarrow p$로 받아들이는 경우도 있는 데 완전히 반대로 해석한것이다. 자주 발생하는 실수이니 주의해야 한다. 많은 경우 수학적 정리와 문제들은 명제 기호로 쓰여있지 않다. 때문에 이를 해석할 때, 주어진 규칙에 맞게 해석했는지 유의해야 한다.

조건문과 같은 진리표를 가지는 복합 명제도 있는데, $p \rightarrow q$는 $\neg (p \wedge \neg q)$와 같은 진리 값을 가진다.

<center>

|$p$|$q$|$p \rightarrow q$|$\neg (p \wedge \neg q)$|
|:--:|:--:|:--:|:--:|
|T|T|T|T|
|T|F|F|F|
|F|T|T|T|
|F|F|T|T|

</center>

주어진 조건문 $p \rightarrow q$에 기반해, 명제의 순서를 바꾸거나 부정들을 이용해 새로운 명제들을 만들 수 있다. 이들을 각각 **역**(converse), **대우**(contrapositive), 그리고 **이**(inverse)라 부른다.

<center> 

| |역(converse)|대우(contrapositive)|이(inverse)|
|:--:|:--:|:--:|:--:|
|$p \rightarrow q$|$q \rightarrow p$|$ \neg q \rightarrow \neg p$| $\neg p \rightarrow \neg q$|

</center>

이 중 대우는 본래 명제와 같은 진리값을 가진다. 대우가 참이면 본 명제도 참이고, 대우가 거짓이면 본 명제도 거짓이다. 역이나 이는 이런 성질을 가지지 않는다. 일반적으로 역이나 이의 진리값이 정해진다고 해도, 이를 통해 본래 명제의 진리값을 판정할 수는 없다.

다음의 진리 표를 참조하자.


<center> 

| $p$|$q$|$p \rightarrow q$|$ \neg q \rightarrow \neg p$|$q \rightarrow p$|$\neg p \rightarrow \neg q$|
|:--:|:--:|:--:|:--:|:--:|:--:|
|T|T|T|T|T|T|
|T|F|F|F|T|T|
|F|T|T|T|F|F|
|F|F|T|T|T|T|


</center>
 
![](https://wikidocs.net/images/page/150317/conditionaldiagram.png)

다이어그램에서 보이다 시피, 대우는 조건문에 역과 이를 가한 것과 같다. 이때 순서는 상관없다.

조건문과 조건문의 대우는 서로 동일한 진리값을 공유하는 데, 이는 조건문을 이루는 두 명제 $p$와 $q$의 진리값에 관계없이 가지는 성질이다. 이렇듯 어떤 두 복합 명제가 구성하는 독립 명제들의 진리값과 상관없이 언제나 동일한 진리값을 가질 경우 이 두 명제가 **동치 관계**(equivalence relation)에 있다 한다. 조건문과 그 대우, 조건문의 역과 조건문의 이는 각각 동치 관계에 있다. 동치 관계는 나중에 선형 변환 부분에서 좀 더 명확한 정의를 보도록 하자.

어느 두 명제가 진리값을 공유함을 나타내는 복합 명제는 **쌍조건문**(biconditional statement)이라 한다.

<table style="border-radius:8px;width:100%;">
    <th style="text-align:center;background-color:rgb(0, 0, 0); color:white; border-top-left-radius: 10px;width:20%;">Def</th>
    <th style="text-align:left;">쌍조건문 (Biconditional statement) </th>
    <tr style="text-align:center;">
        <td colspan="2">
        
명제 $p, q$에 대해, 쌍조건문 $p \leftrightarrow q$는 $(p \rightarrow q) \wedge (q \rightarrow p)$을 의미한다. 쌍조건문은 두 명제 $p$와 $q$가 같은 진리값을 가질 때, 참을 다른 경우에 거짓이다.
            
        </td>
    </tr>
</table>

---

일반적인 영어 표현으로는 "$p$ if and only if $q$"라 표기한다. 

[논리 연산자 적용 순서]

[복합 명제의 성질]

tautology
contradiction
contingency

논리적 동치

satisfiable
unsatisfiable

## 술어 (Predicate)

명제만으로 수학의 모든 문장을 표현할 수 있다면 좋겠지만, 실제로는 불가능하다. 대표적으로 다음과 같은 문장들을 생각해보자.

* 유리수 집합에 $x^2 =3$을 만족하는 어떤 유리수 $x$가 존재한다.
* 모든 실수 $x$에 대해, 정수 $n$이 존재해, $n < x < n+1$을 만족한다.
* 모든 자연수 $n$에 대해, 

## 양화사(Quantifier)

보편 양화사 (Universal quantifier)

존재 양화사 (Existential quantifier)

### 양화사의 부정, 결합, 분배 규칙

<!-- 논리적 추론과 증명: 196-202 참고 -->

$$\neg (\exists x) Px \rightarrow (\forall x) \neg Px$$
$$\neg (\forall x) Px \rightarrow (\exists x) \neg Px$$


## 연역 추론 규칙


보편 양화사의 도입: 임의의 대상 $u$에 대해, A(u) 이다. -> $\forall x A(x)$
# 증명(Proof)

## 용어

공리(Axiom)는 참이라고 가정하는 명제를 의미한다. 공리계(Axiom system)는 이러한 공리들을 모아 놓은 것을 의미한다. 공리는 주어진 명제들에 대해, 참 거짓을 판정할 수 있는 전제로써 사용할 수 있다. 이때, 주어진 명제는 참/거짓으로 판정이 되거나 참/거짓 모두 불가능할 수도 있다. 참/거짓으로 판정된 명제는 정리(Theorem)라 불린다. 이러한 명제의 판정을 위한 논증을 증명(Proof)라 부른다. 이러한 증명의 과정에서 별개의 명제들을 판별해야 할 수도 있는데, 증명 과정에서 보조로 판정한 명제들을 보조 정리(Lemma)라 부른다. 어떤 명제가 주어진 공리계에서 참이라 판정되었다면, 다른 명제의 증명에서 공리계의 공리와 함께 증명 과정에서 사용가능하다. 별도의 추가적인 공리 없이 바로 증명된 정리에서 유도되는 정리가 있는데 이는 따름정리(Corollary)라 부른다.

## 직접증명(Direct proof)

## 간접증명(Indirect proof)
 
 ### 대우증명(Proof by contraposition)

 ### 모순증명(Proof by contradiction)

## 다른 증명 방법들

### 사례별증명(Exhaustive proof/Proof by cases)

진리표를 사용한 증명과 정확히 일치한다. 특정한 경우, 증명해야 하는 복합 명제의 경우가 유한하거나 무한하지만 범주를 나누어 무한한 경우에 대한 증명이 끝나고 유한한 경우만 남을 수도 있다. 이 경우 사례별로 증명을 할 수도 있다.

대표적인 사례가 4색 정리(Four color theorem)의 증명이다. 

**WLOG**: Without Loss Of Generality

존재성(Existence)
유일성(Uniqueness)

이곳에 서술한 증명이 모든 증명 전략은 아니다. 상황에 따라서 다양한 증명이 있을 수 있고, 각 수학 분야에서 쓰이는 또다른 증명법이 있기도 하며, 특정 문제에서 특이한 증명이 사용되기도 한다. 그러나 공통적으로 모두 논증의 타당성을 증명하는 과정일 뿐이다. 어느 단 하나의 올바른 증명이 있지는 않다. 증명의 각 단계가 논리적으로 옳다면 모두 올바른 증명이다. 위의 증명 방법들과 논리학에 대한 지식이 있다고 해서 증명을 잘할 수 있지는 않다. 증명에 있어 기계적 방법은 존재하지 않는다. 많은 연습을 통해서 익숙해지는 것밖에 없다.


mathematical induction은 적어도 고등학교 교육과정에서도 배우지만 이 단원에서는 생략했는 데, 정확한 서술을 위해서는 order와 자연수의 성질을 알고있어야하기 때문이다. 

<!--
다만 [리만 가설](https://namu.wiki/w/%EB%A6%AC%EB%A7%8C%20%EA%B0%80%EC%84%A4 "리만 가설")과 [스큐스 수](https://namu.wiki/w/%EC%8A%A4%ED%81%90%EC%8A%A4%20%EC%88%98 "스큐스 수")에서도 확인할 수 있듯이, 큰 수의 세계에서는 상상도 할 수 없는 일이 일어나곤 한다. 종래에는 [로그 적분 함수](https://namu.wiki/w/%EB%A1%9C%EA%B7%B8%20%EC%A0%81%EB%B6%84%20%ED%95%A8%EC%88%98 "로그 적분 함수")([로그함수](https://namu.wiki/w/%EB%A1%9C%EA%B7%B8%ED%95%A8%EC%88%98 "로그함수")의 역수를 [적분](https://namu.wiki/w/%EC%A0%81%EB%B6%84 "적분")한 함수)가 [소수 계량 함수](https://namu.wiki/w/%EC%86%8C%EC%88%98%20%EA%B3%84%EB%9F%89%20%ED%95%A8%EC%88%98 "소수 계량 함수")보다 항상 클 것이라고 예상했었고, 사람들이 계산할 수 있는 정도로 큰 수에서는 그것이 사실이었으나, [스큐스 수](https://namu.wiki/w/%EC%8A%A4%ED%81%90%EC%8A%A4%20%EC%88%98 "스큐스 수")를 기준으로 로그 적분 함수와 소수 계량 함수의 대소 관계가 역전되며, **심지어 대소 관계가 무한히 역전을 거듭한다!** 최초로 계산된 스큐스 수는 1010103410^{10^{10^{34}}}10101034 정도. 매우 큰 값의 수에서는 어떠한 일이 일어날지 확인할 수 없으며, 귀납법의 가장 치명적이고 원시적인 약점이기도 하다. [초월수](https://namu.wiki/w/%EC%B4%88%EC%9B%94%EC%88%98 "초월수") 인정이 어려운 이유 중 하나이기도 하다.] <- 나무위키에서 읽었는데 확인 필요 및 논문 찾자 -->


# 귀납의 문제와 과학적 방법론


과학적 방법론은 귀납-연역적 방법을 모두 사용하는 방법이다. 한가지 문제는 우리가 자연에 대한 정보를 얻는 방법이 근본적으로 귀납적인 절차라는 점이고 우리가 세운 가설을 검증하는 방법 또한 귀납적인 절차라는 점이다. 때문에 실제 자연과학의 이론은 **입증**될 수 없다는 표현을 쓰는 학자들도 많다. 오로지 **반증**만이 가능하다. 이러한, 


본질적으로, 반증되지 않는다면 참으로 가정한다.