---
layout: post
title: GNU 과학계산 라이브러리(GNU Scientific Library)
nav_order: 9
parent: Books
has_children: true
permalink: /docs/Books/GSL_Manual_Kor
---

GFDLv1.3
{: .label .label-orange}

1. TOC
{:toc}

# GSL library

**GSL 2.7 manual 한글 번역본 (Gnu Scientific Library Manual)**

본 책은 GNU Scientific Library(GSL) 2.7 manual과 관련 자료들을 한글로 번역한 책입니다. python 같은 경우는 한글 자료도 많지만, C로 짜여진 라이브러리는 한글 자료가 빈약하여 시작하게 되었습니다.

gsl 2.7 document를 기준으로 해서 번역합니다. 최대한 한글로 풀어쓰는 것을 목적으로 합니다. 원문 문서는 [web page](https://www.gnu.org/software/gsl/doc/html/index.html)로 보거나, pdf로 다운받을 수도 있습니다. [pdf](https://www.gnu.org/software/gsl/doc/latex/gsl-ref.pdf)


## 허가 조항

원 문서가 [GNU 자유 문서 사용 허가서(GNU FDL: GNU Free Documentation License)](https://www.gnu.org/licenses/fdl-1.3.html)에 따라 배포되고 있어 본 라이센스에 따라 이 책의 모든 내용은 GNU FDL 허가서 하에 배포 됩니다.

```
    Copyright (c)  2021  김현성.
    Permission is granted to copy, distribute and/or modify this document
    under the terms of the GNU Free Documentation License, Version 1.3
    or any later version published by the Free Software Foundation;
    with no Invariant Sections, no Front-Cover Texts, and no Back-Cover Texts.
    A copy of the license is included in the section entitled "GNU
    Free Documentation License".
```

## 번역 살피기

제목에 `[--]`이 들어간 경우 아직 번역이 끝나지 않거나, 누락된 내용이 있는 경우입니다. 만일, 없는 문서에서 누락된 사항을 발견한다면, (qwqwhsnote@gm.gist.ac.kr)에 연락해 주시길 바랍니다. 

### 완료 문서

* 소개
* GSL 설치
* 라이브러리 사용
* 오류 관리
* 수학 함수
* 복소수
* 다항식
* 특수 함수
* BLAS 지원
* 담금질 기법
* 수치미분
* 함수의 근 탐색
* 함수의 최소값 탐색
* 물리 상수
* GSL 기여자


### 부분 완료 문서 (60% 이상)

* GSL 디자인 문서
* 벡터와 행렬
* 고속 푸리에 변환
* IEEE 부동 소수 대수
* GNU 자유 문서사용 허가서

### 미번역 문서

* 순열
* 조합
* 중복 집합
* 정렬
* B-스플라인
* 선형대수학
* 고유공간
* 수치적분
* 난수 생성
* QUASI-RANDOM SEQUENCES
* 난수 분포
* 통계
* 통계 실행
* 통계 창 이동
* 디지털 필터링
* 히스토그램
* N-튜플
* 몬테카를로 적분
* 상미분 방정식
* 보간법
* 체비쇼프 근사
* Series acceleration
* Wavelet 변환
* 이산 한켈 변환
* 다변수 함수의 근 탐색
* 다변수 함수의 최소값 탐색
* 선형 최소 제곱법
* 비선형 최소 제곱 근사
* 희소 행렬
* 희소 연산의 BLAS 지원
* 희소 선형 대수학
* 수치해석 프로그램 디버깅
* GSL CBLAS 라이브러리
* Autoconf 매크로
* C 표준 라이브러리
* GNU 일반 공중사용 허가서

### 추가 자료

- 2.01  GSL 설치: Windows 버전 설치 가이드 추가하고, Linux 버전 제대로 점검, Mac 부분 가능하면 추가
-  C 표준 라이브러리: 표준 지정 기관 서술 및 자료 얻는 방법, 가격 서술, 주요 계산용 헤더파일 기술 및 예시 만들기
-  추가 라이브러리와 소프트웨어(*): 수치 해석 소프트웨어와 라이브러리 일부를 서술합니다.


##  gsl 2.7 변경점

본 문서의 번역은 2020년도에 시작했습니다. 21년도에 gsl2.6-2.7로 버전이 업데이트 되었습니다. 다음은 변경점 목록입니다.

* fixed doc bug for gsl_histogram_min_bin (lhcsky at 163.com)
* clarified documentation on interpolation accelerators (V. Krishnan)
* updated exponential fitting example for nonlinear least squares
* added banded LU decomposition and solver (gsl_linalg_LU_band)

```
New functions added to the library:
      - gsl_matrix_norm1
      - gsl_spmatrix_norm1
      - gsl_matrix_complex_conjtrans_memcpy
      - gsl_linalg_QL: decomp, unpack
      - gsl_linalg_complex_QR_* (thanks to Christian Krueger)
      - gsl_vector_sum
      - gsl_matrix_scale_rows
      - gsl_matrix_scale_columns
      - gsl_multilarge_linear_matrix_ptr
      - gsl_multilarge_linear_rhs_ptr
      - gsl_spmatrix_dense_add (renamed from gsl_spmatrix_add_to_dense)
      - gsl_spmatrix_dense_sub
      - gsl_linalg_cholesky_band: solvem, svxm, scale, scale_apply
      - gsl_linalg_QR_UD: decomp, lssolve
      - gsl_linalg_QR_UU: decomp, lssolve, QTvec
      - gsl_linalg_QR_UZ: decomp
      - gsl_multifit_linear_lcurvature
      - gsl_spline2d_eval_extrap
```

* gsl_sf_legendre_array_index() inline and documented
   gsl_sf_legendre_nlm()
