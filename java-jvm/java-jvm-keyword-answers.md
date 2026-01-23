# Java / JVM 키워드 답변 정리
면접 답변 연습용 · 키워드 기반

---

## 1️⃣ JVM (Java Virtual Machine)

### 🎯 한 줄 핵심
- Java 프로그램을 실행하는 런타임 환경

### 🔑 키워드
- Bytecode
- 플랫폼 독립성
- Class Loader
- Runtime Memory
- GC

### 🗣 말하기 흐름
- “Java 코드를 바이트코드로 실행”
- “운영체제 위에서 동작”
- “메모리 관리와 GC를 JVM이 담당”

---

## 2️⃣ JVM 메모리 구조

### 🎯 한 줄 핵심
- JVM이 메모리를 영역별로 나누어 관리

### 🔑 키워드
- Heap
- Stack
- Method Area
- PC Register
- Native Stack

### 🗣 말하기 흐름
- “객체는 Heap”
- “메서드 실행 정보는 Stack”
- “Heap은 GC 대상, Stack은 스레드별”

---

## 3️⃣ Heap vs Stack

### 🎯 한 줄 핵심
- Heap은 객체 저장, Stack은 실행 흐름 저장

### 🔑 키워드
- 객체 인스턴스
- 스레드별 스택
- 공유 영역
- StackOverflowError
- OutOfMemoryError

### 🗣 말하기 흐름
- “Heap은 공유, Stack은 독립”
- “Heap 문제는 GC”
- “Stack 문제는 재귀나 스레드”

---

## 4️⃣ Garbage Collection (GC)

### 🎯 한 줄 핵심
- 사용하지 않는 객체를 자동으로 정리

### 🔑 키워드
- Young / Old
- Minor GC
- Major GC
- Stop-The-World
- Throughput / Latency

### 🗣 말하기 흐름
- “Heap 메모리 관리 방식”
- “Young에서 자주 GC”
- “GC는 성능과 직결”

---

## 5️⃣ Stop-The-World (STW)

### 🎯 한 줄 핵심
- GC 중 애플리케이션 실행이 멈추는 현상

### 🔑 키워드
- GC Pause
- Application Thread Stop
- Latency
- Full GC

### 🗣 말하기 흐름
- “GC 시점에 발생”
- “응답 지연 원인”
- “최소화가 목표”

---

## 6️⃣ GC 알고리즘 개요

### 🎯 한 줄 핵심
- GC 방식에 따라 성능 특성이 달라짐

### 🔑 키워드
- Serial GC
- Parallel GC
- CMS
- G1 GC
- ZGC (개념 수준)

### 🗣 말하기 흐름
- “Serial은 단순”
- “Parallel은 처리량”
- “G1은 균형”

---

## 7️⃣ JVM 튜닝 관점

### 🎯 한 줄 핵심
- JVM 옵션은 성능 특성에 맞게 조정

### 🔑 키워드
- Heap Size
- Xms / Xmx
- GC 로그
- Pause Time
- Throughput

### 🗣 말하기 흐름
- “무조건 크게 아님”
- “GC 로그 기반 조정”
- “응답 지연 기준 판단”

---

