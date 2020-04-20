---
title: "Gaussian Mixture Model (GMM)과 Expection Maximization (EM)"
excerpt_separator: "<!--more-->"
categories:
  - Study
tags:
  - Gaussian Mixture Model (GMM)
  - Uncertainty
  - Expection-Maximization (EM)
---

GMM - Gaussian distribution이 여러개 혼합된 clustering 알고리즘
현실에 존재하는 복잡한 형태의 확률 분포를 K개의 Gaussian distribution을 혼합하여 표현하고자 하는 것이 GMM의 기본 아이디어
이때 K는 heuristic하게 정해줌

EM - 보이지 않는 잠재 변수 (latent variable)에 의존하는 확률 모델에서 parameter들의 최대 우도 추정치 (maximum likelihood estimates of parameters)를 찾고자 하는 알고리즘
expection 단계에서 잠재 변수의 기대치를 계산하고 maximization 단계에서 주어진 데이터와 기대치가 부여된 잠재 변수를 이용하여 모수들의 최대 우도 추정치를 계산함

GMM에서 distribution이 나오면 EM을 통해 최대 추정치를 계산하여 uncertainty에 대한 추정치를 output으로 계산해 낸다.
machine learning에서는 중요한 방법 중 하나이지만 minor한 문제인 (closed-form estimators가 존재할 때) mixing 분포가 알려져 있다면 각 구성요소가 뻔하게 추정될 수 있는 finite mixture of Gaussians의 최대 우도 추정이다.
