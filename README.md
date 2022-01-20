# aggregator-readme

## Description

---

어그리게이터 프로젝트

<br/><br/>

## Common Package

| 패키지 명                    |           description            |                         repository | version                                                                                        |
| :--------------------------- | :------------------------------: | ---------------------------------: | ---------------------------------------------------------------------------------------------- |
|                              |
| **Aggregator-Logger**        |          로깅 관련 모듈          |        cseongeun/aggregator-logger | ![Aggregator Logger](https://img.shields.io/badge/aggregator_logger-0.0.22-blue)               |
|                              |
| **Aggregator-Util**          |             유틸리티             |          cseongeun/aggregator-util | ![Aggregator Util](https://img.shields.io/badge/aggregator_util-1.0.30-blue)                   |
|                              |
| **Aggregator-Base**          | 공통 엔티디, 레포지토리, 상수 등 |          cseongeun/aggregator-base | ![Aggregator Base](https://img.shields.io/badge/aggregator_base-0.0.67-blue)                   |
|                              |
| **Aggregator-Defi-Protocol** |       디파이 프로토콜 모듈       | cseongeun/aggregator-defi-protocol | ![Aggregator Defi Protocol](https://img.shields.io/badge/aggregator_defi_protocol-0.0.37-blue) |
|                              |

<br/><br/>

- 패키지 버전 업데이트 스크립트

  ```bash
  $ npm run deploy    // 1) npm run build  2) npm version patch 3) npm publish
  ```

<br/><br/>

## 어그리게이터 프로젝트 세팅

- 어그리게이터 데이터 베이스 세팅

```bash
$ git clone [aggregator-base repository]

$ cd aggregator-base

$ cp .env.example .env

********* .env 데이터 삽입 *******

$ npm i

$ npm run migration:generate init // 마이그레이션 생성

$ npm run migration:run  // 마이그레이션 진행

$ npm run seed:run   // 초기 시드 삽입
```

- 어그리게이터 작업 실행

```bash
$ git clone [aggregator-task]

$ cd aggregator-task

$ cp .env.example .env

********* .env 데이터 삽입 *******

$ npm i

$ npm run start
```

- 어그리게이터 스트림 작업 실행

```bash
$ git clone [aggregator-task-stream]

$ cd aggregator-task-stream

$ cp .env.example .env

********* .env 데이터 삽입 *******

$ npm i

$ npm run start
```

<br/> <br/>

## Aggregator Task(어그리게이터 작업)

<!-- ### 작업 단위 구조

> Module
>
> > Protocol ex) pancake-swap
> >
> > > Network ex) binance-smart-chain, polygon
> > >
> > > > Task ex) farm, nft -->

## Aggregator Task Stream(어그리게이터 스트림 작업)

### 플로우

![Aggregator-Task-Stream-동작원리](images/Aggregator-Task-Stream.작동원리.png)

`Interaction(인터렉션)?`

    **인터렉션은 특정 주소가 어떠 컨트랙트와 거래를 진행했는지 또는 컨트랙트의 몇 번째 pid에 대해 거래를 진행했는지 확인하기 위함<리소스 낭비 최소화>**

    1) 특정 주소가 지갑 내 자산 조회 요청을 진행할 경우
    과거 토큰 타입의 컨트랙트와 거래한 이력이 있으면 해당 컨트랙트 주소에 대해서만 잔액 조회를 진행하면됨

    2) 특정 주소가 팜의 스테이킹 수량과 리워드 수량 조회 요청을 진행할 경우 (렌딩 컨트랙트의 공급 수량과 대출 수량)
    과거 팜 타입의 컨트랙트에서 특정 pid에 대한 팜에 대해 특정 주소의 스테이킹 수량과 리워드 수량을 조회하면 됨
