# Motivation

다수의 데이터 제공자들 사이에서 데이터를 공유하는 것이 robust한 ML 모델을 위해서 필요함

하지만 다음과 같은 문제가 있음

- 데이터 공유가 어려움 : 민감정보, 프라이버시 규제, 사업 경쟁자
- ML 모델은 학습데이터에 대한 정보를 유출 함
- 개인 데이터를 사용하여 예측을 하는 것은 민감한 일임

이를 방지하기 위해 Privacy-Preserving Machine Learning (PPML)이 필요

# Current approaches

## Centralized

Raw 데이터나 Aggregate 데이터를 중앙 DB로 전송하는 방식

중앙 DB의 보안을 이용하여 데이터를 보호하기 때문에 신뢰할 수 있는 중앙 서버가 필요함

## Decentralized

**Federated Learning** : 모델에 데이터를 전달하지 않고 데이터로 로컬 모델을 업데이트 하는 방식을 사용함

- 여전히 모델은 sensitive함
- Intermediate 모델 업데이트를 공유하는 것은 여러 프라이버시 문제를 일으킴 (Extracting parties' inputs)

## Privacy-Preserving Decentralized

**Differential Privacy** : 데이터 소유자들 사이에서 private intermediate value를 차별적으로 교환함

- Utility degradating
- High privacy budget
- The achieved practical level of privacy remains unclrea

**Multiparty Computation** : 다수의 서버 모델을 secret-sharing 기법을 이용하여 운영함

- Trust를 분리할 서버의 수에 제한이 있음
- 컴퓨팅 서버 사이에 다수가 honest하다고 가정함
- 높은 컴퓨팅 오버헤드가 발생함

# POSEIDON

Multiparty homomorphic encryption을 이용하여 training 데이터와 resulting 모델, querier's evaluation 데이터를 분산 세팅에서 End-to-End 프로텍션을 제공함 

# 참고자료

[Youtube](https://www.youtube.com/watch?v=kX6-PMzxZ3c)
