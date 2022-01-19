# aggregator-readme

## Description

---

어그리게이터 프로젝트

<br/><br/>

## Common Package

---

| 패키지 명                    |           description            |                         repository | version                                                                                        |
| :--------------------------- | :------------------------------: | ---------------------------------: | ---------------------------------------------------------------------------------------------- |
|                              |
| **Aggregator Logger**        |          로깅 관련 모듈          |        cseongeun/aggregator-logger | ![Aggregator Logger](https://img.shields.io/badge/aggregator_logger-0.0.22-blue)               |
|                              |
| **Aggregator Util**          |             유틸리티             |          cseongeun/aggregator-util | ![Aggregator Util](https://img.shields.io/badge/aggregator_util-1.0.30-blue)                   |
|                              |
| **Aggregator Base**          | 공통 엔티디, 레포지토리, 상수 등 |          cseongeun/aggregator-base | ![Aggregator Base](https://img.shields.io/badge/aggregator_base-0.0.67-blue)                   |
|                              |
| **Aggregator Defi Protocol** |       디파이 프로토콜 모듈       | cseongeun/aggregator-defi-protocol | ![Aggregator Defi Protocol](https://img.shields.io/badge/aggregator_defi_protocol-0.0.37-blue) |
|                              |

<br><br/>

- 패키지 버전 업데이트 스크립트

  ```bash
  $ npm run deploy    // 1) npm run build  2) npm version patch 3) npm publish
  ```

<br><br/>

## Aggregator Task(어그리게이터 작업)

### 작업 단위 구조

> Module
>
> > Protocol ex) pancake-swap
> >
> > > Network ex) binance-smart-chain, polygon
> > >
> > > > Task ex) farm, nft
