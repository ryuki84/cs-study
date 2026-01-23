# Java Concurrency 키워드 답변 정리
면접 답변 연습용 · 키워드 기반

---

## 1️⃣ Java 동시성의 본질

### 🎯 한 줄 핵심
- 여러 스레드가 동시에 실행될 때의 안전성과 성능을 다루는 영역

### 🔑 키워드
- Thread
- Shared Resource
- Race Condition
- Visibility
- Atomicity

### 🗣 말하기 흐름
- “여러 스레드가 동시에 자원에 접근하는 상황”
- “정합성과 성능 문제가 동시에 발생”
- “락과 메모리 가시성이 핵심”

---

## 2️⃣ synchronized

### 🎯 한 줄 핵심
- 객체 단위로 락을 걸어 동시 접근을 제어

### 🔑 키워드
- Intrinsic Lock
- Monitor
- Mutual Exclusion
- Blocking
- Performance Cost

### 🗣 말하기 흐름
- “한 번에 하나의 스레드만 접근”
- “간단하지만 블로킹 발생”
- “락 범위가 크면 성능 저하”

---

## 3️⃣ Lock 인터페이스 (ReentrantLock)

### 🎯 한 줄 핵심
- synchronized보다 유연한 락 제어 방식

### 🔑 키워드
- ReentrantLock
- tryLock
- Fair / Non-Fair
- Explicit Lock
- Deadlock Control

### 🗣 말하기 흐름
- “락 획득/해제를 명시적으로 제어”
- “타임아웃과 공정성 설정 가능”
- “복잡하지만 제어력 높음”

---

## 4️⃣ volatile

### 🎯 한 줄 핵심
- 변수의 메모리 가시성을 보장

### 🔑 키워드
- Visibility
- CPU Cache
- Memory Barrier
- Happens-Before
- No Atomicity

### 🗣 말하기 흐름
- “값 변경을 즉시 다른 스레드에 반영”
- “연산의 원자성은 보장하지 않음”
- “상태 플래그 용도로 사용”

---

## 5️⃣ Atomic 클래스

### 🎯 한 줄 핵심
- 락 없이 원자적 연산을 보장

### 🔑 키워드
- CAS
- AtomicInteger
- Lock-Free
- Compare-And-Swap
- Performance

### 🗣 말하기 흐름
- “CAS 기반 원자 연산”
- “락보다 성능 유리”
- “복잡한 로직에는 한계”

---

## 6️⃣ ThreadLocal

### 🎯 한 줄 핵심
- 스레드별 독립 데이터 저장

### 🔑 키워드
- Thread-Bound
- Transaction Context
- User Context
- Memory Leak Risk
- remove()

### 🗣 말하기 흐름
- “스레드마다 다른 값 유지”
- “Spring 트랜잭션/보안 컨텍스트와 연계”
- “반환 누락 시 메모리 누수 위험”

---

## 7️⃣ Thread Pool / Executor

### 🎯 한 줄 핵심
- 스레드를 재사용해 성능과 안정성을 확보

### 🔑 키워드
- ExecutorService
- Fixed Thread Pool
- Queue
- Thread Starvation
- Backpressure

### 🗣 말하기 흐름
- “스레드 생성 비용 절감”
- “풀 크기가 처리량 한계”
- “과도하면 GC/메모리 압박”

---

## 8️⃣ Blocking vs Non-Blocking (Java 관점)

### 🎯 한 줄 핵심
- 스레드가 대기하느냐, 다른 작업을 하느냐의 차이

### 🔑 키워드
- Blocking I/O
- Waiting Thread
- Async
- Resource Utilization
- Throughput

### 🗣 말하기 흐름
- “Blocking은 스레드를 묶음”
- “Non-Blocking은 효율적이지만 복잡”
- “설계 선택의 문제”

---
