# Micro-Blogging POJO


## 이벤트 구조 설계
- SNS 메세지 발송을 주요 Event 로 두는 Server to Client 구조 서비스가 적절하다.
- 구현은 웹소켓/메세지큐/이벤트 브로커 등으로 구현할 수 있으며, 추상화를 통해 쉽게 구현체를 변경할 수 있도록 설계해야한다
- 메세징을 코어 비즈니스 로직과 분리하여 생각하자, Send / Receive Interface

## 헥사고날 아키텍처
- Core(=Business Logic)과 이를 이용하는 구현을 분리하자
- Core <-> Port <-> Adapter
- 비즈니스 문제를 해결하는 데 꼭 필요한 기능 = 코어
- 특정 기술에 종속된 기능이나 통신 = 어댑터