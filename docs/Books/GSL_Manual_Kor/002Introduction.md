---
layout: default
title: 소개
parent: GSL 과학계산 라이브러리
grand_parent: Books
nav_order: 2
use_math: true
---

GSL
{: .label }
C
{: .label .label-grey}
Kor
{: label .label-blue}

GNU Scientific Library (GSL)은 수치 계산을 위한 라이브러리로 C로 작성되었습니다. 기본적으로 C-api를 제공하며, 다른 고급언어를 위한 인터페이스도 존재합니다. 또 이러한 인터페이스의 작성도 허용됩니다. 이 라이브러리의 코드는 **GNU 일반 공중  사용 허가서** 하에 베포됩니다.

## GSL의 기능

본 라이브러리는 수치 계산의 다양한 분야를 지원합니다. 다음은 GSL에서 제공하는 수치해석 기능들입니다.



|  |  | |
|--|--|--|
|Complex numbers|Roots of polynomials|Special Functions|
|Vectors and Martices| Permutations|Combinations|
|Sorting|BLAS Support|Linear Algebra|
|CBLAS Library|Fast Fourier Transforms|Eigensystems|
|Random numbers|Quadrature|Random Distribution|
|Quasi-Random Sequences|Histograms|Statistics|
|Monte Carlo Integration|N-Tuples|Differential Equations|
|Simulated Annealing|Numerical Differentiation|Interpolation|
|Series Acceleratio|Chebyshev Approximations|Root-Finding|
|Discrete Hankel Transforms|Least-Squares Fitting|Minimization|
|IEEE Floating-Point|Physical Constants|Basis Splines|
|Wavelets|Sparse BLAS Support|Sparse Linear Algebra|



이러한 기능들을 GSL에서 제공합니다. 이 책의 각 단원들은 해당 단원에서 제공하는 기능들에 대해, 함수의 상세한 정의, 예시 프로그램과 기반이 되는 알고리즘의 참고 문헌들을 제공합니다.

몇몇 구현체들은 **FFTPACK**이나 **QUADPACK**등과 같이 공공 패키지에 기반하기도합니다. GSL의 개발자들은 이러한 패키지들을 현대적인 코딩 규약으로 재구성하기도 했습니다. 

## 자유 소프트웨어

GNU Scientific Library의 하위 프로그램들은  "자유 소프트웨어"입니다. 이 말은 이러한 프로그램들의 사용과 배포를 자유롭게 할 수 있다는 뜻입니다. 그러나 이 라이브러리는 **퍼블릭 도메인** [^public] 이 아닙니다. 엄연히 저작권이 존재하며, 배포와 사용에서 특정한 조건을 만족해야 합니다.

GSL의 저작권은 여러 기여자들의 협동과 같은 긍정적인 행위들을 보호하고 권장할 수 있도록 고안되었습니다. 이 저작권 아래에서 다른 사람들이 당신이 GSL을 이용해 작성한 소프트웨어의 어떠한 버전도 얻지 못하도록 하는 행위는 금지됩니다. 

구체적으로 GNU 과학 라이브러리를 사용하는 프로그램의 복사본의 공유 가능성, 소스 코드를 원하면 받을 수 있는지의 유무, 이러한 프로그램의 변경, 새로운 무료 프로그램에서의 사용 등을 의미하며, 이러한 행위들이 모두 허용되고 제공되어야합니다.

모두가 이러한 권리를 가지기 위해, 다른 이들로 부터 이 권리를 박탈하는 행위를 금지합니다. 예시로 GNU 과학 라이브러리를 사용하는 모든 코드의 복사본을 베포하는 경우, 당신이 짠 코드를 받는 사람은 당신이 GNU 과학 라이브러리를 사용할 때 받은 모든 권한을 주어야하고 (소스코드를 받을 수 있는 지), 이러한 권리를 알려야함을 의미합니다. 다시말해 이 라이브러리는 독점 프로그램에 재분배 되어서는 안된다는 것을 의미합니다. [^right]

그리고 분명히 하고 넘어가야 할 점은 GNU Scientific Library는 어떠한 보증 같은 것이 존재하지 않습니다. 만약 프로그램들이 누군가에 의해 수정되고 배포될 경우, 그 작업물을 받는 사람들은 GNU 공식 베포가 아닌 것을 알고 있어야 합니다. 그러므로 다른 수정에 의한 문제들은 본 라이브러리에 반영 되지 않을 것입니다. 

GNU Scientific Library와 관련된 소프트웨어의 배포에 관한 정확한 조건은 [GNU General Public License](https://www.gnu.org/software/gsl/doc/html/#GNU-General-Public-License)에서 찾을 수 있습니다. 좀 더 자세한 정보를 얻고 십다면 GNU 프로젝트의 웹페이지에서 [GNU GPL에 자주 묻는 질문들](https://www.gnu.org/software/gsl/doc/html/#GNU-General-Public-License)을 참고하세요.

자유소프트웨어 재단 또한 상업 이용을 위한 저작권 컨설팅을 제공합니다. (자세한 사항은 [FSF](https://www.fsf.org/)에서 확인하세요.


## GSL 얻기

라이브러리의 소스코드는 다양한 방법으로 얻을 수 있습니다. 친구로부터 복사하거나, CDROM을 구입 아니면 인터넷에서 다운로드 할 수도 있습니다. GNU 웹사이트에서는 이러한 소스코드들을 다운 받을 수 있는 FTP 서버들의 목록을 제공하고 있습니다. <http://www.gnu.org/software/gsl/>

이 라이브러리를 위해 사전에 GNU 시스템을 이용하는 것을 권장합니다. GNU C complier와 GNU C Library에서 본 라이브러리는 몇가지 추가 기능들을 활용할 수 있습니다. 그러나 이 라이브러리는 완전히 이식 가능도록 구현되었기 때문에 굳이 해당하는 시스템을 사용하지 않더라도, C 컴파일러가 있는 대부분의 시스템에서 사용가능합니다.

새로운 배포, 업데이트 그리고 다른 관련 이벤트들은 <info-gsl@gnu.org>에서 알림을 받을 수 있습니다. 이메일을 통해 알림을 받고 싶으시다면, 다음과 같은 형식으로 이메일을 보내면 됩니다.

```
To: info-gsl-request@gnu.org
Subject: subscribe
```

보내고 나면 구독 요청 확인 답장이 올 것입니다.


## 비보증성

이 메뉴얼에서 설명하고 있는 소프트웨어는 어떤 보증도 존재하지 않습니다. 이 소프트웨어는 "있는 그대로" 제공됩니다. 상업 베포자로 부터의 유료 보증 서비스의 이용, 제공된 코드의 정확한 사용, 루틴의 확인 등은 모두 본인의 책임입니다. 자세한 내용은 [GNU 공중 사용 허가서](https://www.gnu.org/software/gsl/manual/html_node/GNU-General-Public-License.html#GNU-General-Public-License)를 확인하세요.

## 버그 보고

알려진 버그들의 목록은 GSL 배포판의 `BUGS` 파일이나 온라인 GSL 버그 추척기에서 찾을 수 있습니다.[^BugTracker] 컴파일 문제에 대한 자세한 내용은 `INSTALL` 파일에서 찾을 수 있습니다.

[^BugTracker]: <http://savannah.gnu.org/bugs/?group=gsl>

만약, 이러한 버그 목록에 없는 버그를 발견 했을 경우 <bug-gsl@gnu.org>로 보고해주시기를 바랍니다.

모든 버그 보고는 다음을 포함하고 있어야합니다.

* GSL의 버전 숫자
* 하드웨어와 운영체제
* 사용된 컴파일러와 컴파일러의 버전, 컴파일 옵션
* 버그를 만드는 짧은 프로그램

같은 문제가 라이브러리를 최적화 없이 컴파일 할 때 발생하는지, 아닌지를 확인해 준다면 더욱 유용합니다.

감사합니다.

본 설명서의 오류나 누락도 같은 주소로 보고할 수 있습니다.

## 자세한 정보


본 메뉴얼의 온라인 복사본과 더 자세한 정보, 관련된 프로젝트, 이메일 리스트들은 언급한 사이트들에서 찾을 수 있습니다.

어떤 질문이나 라이브러리 설치에 관한 것들은 <help-gsl@gnu.org>에서 주는 목록에 물어 볼 수 있습니다. 본 리스트를 구독하려면 다음과 같이 이메일을 보내면 됩니다.
```
To: help-gsl-request@gnu.org
Subject: subscribe
```

본 이메일 리스트는 이 메뉴얼에서 다루지 않는 내용에 대해 묻거나 라이브러리 개발자들과 연락하는 데 쓸 수 있습니다.

만약 GNU Scientific Library를 저널의 문서에 참고문헌으로 넣고싶다면, 본 메뉴얼을 넣는 것을 추천합니다. 예시로:
```
M. Galassi et al, GNU Scientific Library Reference Manual (3rd Ed.), ISBN  0954612078
```

만약, 주소를 넣고 싶다면, <http://www.gnu.org/software/gsl/>를 사용하십시오.

## 메뉴얼 규약

본 메뉴얼에서는 키보드로 작성해야하는 많은 예시들을 포함하고 있습니다. 터미널에서 작성해야하는 경우 다음과 같이 작성됩니다.
```
$ command
```
줄의 첫번째 문자는 터미널 프롬프트를 나타내고 명령어를 작성할 때 작성하지 말아야 할 부분입니다. 어떤 시스템에서는 다른 기호를 사용하기도 하지만, **$** 는 터미널 프롬프트의 표준 기호로 본 메뉴얼에서 쓰입니다. 

원본 메뉴얼은 라이브러리의 사용에 필요한 상세한 내용을 전부 기술하고 있지는 않습니다. 필요에 따라 본래 메뉴얼에 없는 추가적인 정보들을 단락이나, 단원에 넣을 것 입니다. 그러한 정보들은 끝에 다음과 같은 기호 '(\*)'를 써서 나타낼 것입니다. (\*)

```
Additional Contents (*)
#.# Additional Contents Chapter (*)
``` 

본 문서에서 GNU Scientific Library는 앞으로 `GSL`이란 단어로 쓰입니다.




[^public]: 퍼블릭 도메인(Public domain)은 저작권이 소멸 되었거나 저작자가 저작권을 포기한 저작물을 말합니다. 
[^right]: 상업적 이용은 이 문건과 관계 없습니다. 많은 상업 프로그램들이 GNU 공중 사용 허가서로 베포되는 코드를 포함하고 있으며, 그들의 경우 소스 코드를 다운받을 수 있는 방안들을 제공해 GNU 공중 사용 허가서를 따르고 있습니다. 