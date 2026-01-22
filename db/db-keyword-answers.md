# DB 키워드 답변 정리 (Database Keyword Answers)
면접 답변 연습용 · 키워드 기반

---

## 1️⃣ Index (인덱스)

### 🎯 한 줄 핵심
- 조회 성능을 높이기 위한 자료구조

### 🔑 키워드
- B-Tree
- Full Scan vs Index Scan
- WHERE / JOIN / ORDER BY
- 읽기 성능 향상
- 쓰기 비용 증가

### 🗣 말하기 흐름
- “인덱스는 테이블을 빠르게 찾기 위한 구조”
- “조회는 빨라지지만 쓰기 비용 발생”
- “조회 패턴 기준으로 설계가 중요”

---

## 2️⃣ Transaction (트랜잭션)

### 🎯 한 줄 핵심
- 논리적으로 하나의 작업 단위

### 🔑 키워드
- ACID
- 원자성
- 일관성
- 격리성
- 지속성

### 🗣 말하기 흐름
- “트랜잭션은 모두 성공하거나 모두 실패”
- “데이터 정합성 보장 목적”
- “금융/결제 시스템의 기본 단위”

---

## 3️⃣ Transaction Isolation Level (격리 수준)

### 🎯 한 줄 핵심
- 동시에 실행되는 트랜잭션 간 간섭 정도

### 🔑 키워드
- Read Uncommitted
- Read Committed
- Repeatable Read
- Serializable
- Dirty Read
- Non-repeatable Read
- Phantom Read

### 🗣 말하기 흐름
- “격리 수준이 높을수록 안전하지만 느려짐”
- “대부분 Read Committed 또는 Repeatable Read”
- “DB별 기본값 차이 존재”

---

## 4️⃣ Lock (DB Lock)

### 🎯 한 줄 핵심
- 동시성 제어를 위한 데이터 접근 제한

### 🔑 키워드
- Shared Lock
- Exclusive Lock
- Row Lock
- Table Lock
- Deadlock

### 🗣 말하기 흐름
- “동시 수정 방지를 위한 장치”
- “락이 길어지면 성능 저하”
- “잘못되면 데드락 발생”

---

## 5️⃣ MVCC (Multi Version Concurrency Control)

### 🎯 한 줄 핵심
- 락 없이 읽기 일관성을 제공하는 방식

### 🔑 키워드
- Snapshot
- Undo Log
- Read View
- Non-blocking Read

### 🗣 말하기 흐름
- “읽기와 쓰기를 분리”
- “읽기 시 락을 걸지 않음”
- “동시성 성능 향상”

---

## 6️⃣ Index vs Lock 관점 정리

### 🎯 한 줄 핵심
- 인덱스는 성능, 락은 안정성

### 🔑 키워드
- 인덱스 → 조회 성능
- 락 → 정합성
- 과도한 락 → 병목
- 잘못된 인덱스 → 풀 스캔

### 🗣 말하기 흐름
- “DB 성능 문제는 인덱스부터”
- “정합성 문제는 락 구조 확인”

---

