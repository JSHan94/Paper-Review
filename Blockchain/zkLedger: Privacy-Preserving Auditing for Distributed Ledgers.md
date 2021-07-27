# About Paper

Accepted in NSDI'18 

MIT 미디어랩에서 발표

# Motivation

은행과 같은 금융시스템 거래에서는 프라이버시가 중요함.

거래에 관련된 세부적인 정보(From, To, Amount)들이 포함되어있음.

이를 암호화하고 숨기고 싶지만, Regulator들은 이런 정보들을 활용하고 감시하기를 원함

정보를 암호화한 채 audit하는 기술이 필요함.

# zkLedger

A Privatem, auditable transaction ledger

Property 
- Privacy : 트랜잭션의 정보를 숨김
- Integerity with public verification :  누구나 well-formed된 트랜잭션을 검증하는 것이 가능함
- Auditing : Compute provably-correct linear functions over transactions

Auditor는 ledger contents에 대해서 올바른 대답을 얻을 수 있음

Ex. What fraction of your assets are in Euros? -> 3mil/100mil

zkLedger는 다음과 같은 것을 계산 가능함

- Ratio & percentaes of holdings
- Sums, Averages, variance, skew
- Outliers
- Approximations and orders of magnitude
- Changes over time
- Well-known financial risk measurements (Herfindahl-Hirschmann idex)

## Security goals

- Privacy : Auditor와 non-involved parties는 개별 트랜잭션이나 amount를 볼 수 없다.
- Completeness : Bank는 auditor에게 거짓말을 할 수 없고, transaction을 빼먹을 수 없다.
- Integrity : 은행은 Financial invariants를 위반 할 수 없다. 즉, honest한 은행은 auditor를 올바른 대답으로 항상 납득시켜야한다.
- Progress : Malicious 은행은 다른 은행의 transaction을 막을 수 없다.

## Treat model

다음과 같은 상황을 가정함

- 은행은 auditor에게 asset을 숨기거나, 조작하거나, 훔칠 수가 있다. 즉, malicious bank가 존재 가능하다.
- Banks can arbitrarily colludes
- Banks or the auditor는 트랜잭션 내용을 학습하려고 노력할 수도 있다.

이외에 다음과 같은 것은 다루지 않음 (Out of Scope)
- A ledger that omits transactions or is unvailable
- And adversary watching network traffic
- Banks leaking their own transactions

## zkLedger design

트랜잭션에서 values를 가리는 것은 꽤 쉬운 일임

예시로 Pedersen Commitments가 가능

&&
comm(v) = g^vh^r
&&


# IMHO

본 논문에서는 은행 시스템을 이용하여 zkLedger를 설명하는데,

아무래도 모든 개인 트랜잭션들에 대해서 본 시스템을 적용시키기에는 performance의 한계가 있는 것으로 생각 됨.



# 참고 자료

[발표영상](https://www.usenix.org/conference/nsdi18/presentation/narula)
[논문](https://www.usenix.org/system/files/conference/nsdi18/nsdi18-narula.pdf)
