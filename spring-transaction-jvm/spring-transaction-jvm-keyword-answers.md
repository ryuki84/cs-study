# Spring Transaction & JVM 연계 키워드 답변 정리
면접 답변 연습용 · 키워드 기반

---

## 1️⃣ @Transactional의 역할

### 🎯 한 줄 핵심
- 서비스 로직을 트랜잭션 경계로 묶어 정합성을 보장

### 🔑 키워드
- AOP Proxy
- Transaction Boundary
- Commit / Rollback
- Connection Bind (Thread-bound)
- PlatformTransactionManager

### 🗣 말하기 흐름
- “@Transactional은 프록시 기반으로 트랜잭션 경계를 만든다”
- “트랜잭션 동안 DB 커넥션이 스레드에 바인딩된다”
- “정합성은 보장되지만, 길어지면 동시성이 떨어진다”

---

## 2️⃣ 트랜잭션과 DB 커넥션 풀의 관계

### 🎯 한 줄 핵심
- 트랜잭션이 길어지면 커넥션 점유 시간이 늘어 병목이 된다

### 🔑 키워드
- HikariCP
- Connection Pool Exhaustion
- Waiting Threads
- Timeout
- Backpressure

### 🗣 말하기 흐름
- “트랜잭션 시작 시 커넥션을 점유한다”
- “커넥션이 부족하면 요청 스레드가 대기한다”
- “대기 증가 → 응답 지연 → 타임아웃/장애 확산”

---

## 3️⃣ 트랜잭션과 JVM/GC의 관계

### 🎯 한 줄 핵심
- DB 대기(Blocking)가 늘면 스레드가 쌓이고 메모리/GC 압박이 증가한다

### 🔑 키워드
- Thread Blocked / Waiting
- Request Queueing
- Object Allocation Increase
- GC Pressure
- Stop-The-World 영향

### 🗣 말하기 흐름
- “DB 병목으로 스레드가 묶이면 요청이 쌓인다”
- “요청/응답 객체가 쌓여 Heap 사용이 증가한다”
- “Heap 증가 → GC 빈도/지연 증가 → 응답 지연이 더 커진다”

---

## 4️⃣ 트랜잭션 범위 설계 원칙

### 🎯 한 줄 핵심
- 트랜잭션은 ‘짧게’, 외부 호출은 ‘밖으로’

### 🔑 키워드
- Short Transaction
- External API out of TX
- Lock Duration
- Deadlock Risk
- Read-only TX

### 🗣 말하기 흐름
- “트랜잭션 범위를 최소화해 락/커넥션 점유를 줄인다”
- “외부 API는 트랜잭션 밖에서 수행해 장애 전파를 막는다”
- “조회는 readOnly로 최적화한다”

---

## 5️⃣ 전파(Propagation)와 격리(Isolation) 실무 포인트

### 🎯 한 줄 핵심
- 전파는 트랜잭션 경계 결합, 격리는 동시성 수준 제어

### 🔑 키워드
- REQUIRED / REQUIRES_NEW
- Isolation Level
- Consistency vs Concurrency
- Retry/Compensation
- Idempotency

### 🗣 말하기 흐름
- “REQUIRED는 기존 트랜잭션에 참여한다”
- “REQUIRES_NEW는 분리해 커밋/롤백을 독립시킨다”
- “격리는 정합성과 성능의 균형이다”

---

## 6️⃣ 대표 장애 시나리오(한 줄로 설명)

### 🎯 한 줄 핵심
- DB 지연 → 커넥션 풀 고갈 → 스레드 대기 → Heap 증가 → GC 지연 → 전체 응답 지연

### 🔑 키워드
- Latency Spike
- Pool Exhaustion
- Thread Starvation
- GC Pause
- Cascading Failure

### 🗣 말하기 흐름
- “병목이 DB에서 시작돼 WAS와 JVM까지 연쇄 영향”
- “해결은 트랜잭션 범위 축소, 커넥션/스레드/타임아웃 설계”

---

