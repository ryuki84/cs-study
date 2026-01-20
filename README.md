# CS 기초 정리 (면접 대비)

이 레포지토리는 
운영체제, 네트워크, 데이터베이스, JVM 등  
CS 기초 개념을 **한글로 정리**한 학습 노트입니다.

단순 암기가 아닌,
- 개념을 스스로 설명할 수 있는지
- 실무 상황과 연결해 이해하고 있는지
- 면접 질문으로 바로 답변할 수 있는지

를 기준으로 정리합니다.

---

## 📌 정리 기준
각 문서는 아래 구조를 따릅니다.

1. 개념 정리  
2. 왜 중요한가  
3. 백엔드 실무 관점  
4. 트레이드오프 / 주의사항  
5. 예상 면접 질문 & 답변

---

## 📚 정리 대상 범위

### [운영체제 (Operating System)](operating-system/os-keyword-answers.md)
- [프로세스 vs 스레드](operating-system/process-vs-thread.md)
- [컨텍스트 스위칭](operating-system/context-switch.md)
- [동기화, 락, 데드락](operating-system/synchronization-lock-deadlock.md)
- [Blocking / Non-Blocking](operating-system/blocking-nonblocking.md)
- [CPU 스케줄링](operating-system/cpu-scheduling.md)
- [가상 메모리](operating-system/virtual-memory.md)

### [네트워크 (Network)](network/network-keyword-answers.md)
- [TCP vs UDP](network/tcp-vs-udp.md)
- [HTTP / HTTPS](network/http-vs-https.md)
- [Keep-Alive](network/keep-alive.md)
- [커넥션 풀](network/connection-pool.md)
- [네트워크 지연](network/network-latency.md)

### 데이터베이스 (Database)
- 인덱스
- 트랜잭션과 격리 수준
- 락, MVCC
- 쿼리 성능 최적화 기본 원리

### Java / JVM
- JVM 메모리 구조
- GC 기본 원리
- 멀티스레드 환경에서의 주의점

---

## 🧭 학습 원칙
- 짧게 쓰되, 말로 설명 가능하게 작성
- 문서마다 면접 질문 최소 1개 이상 포함
- 이론보다 **백엔드 실무 맥락** 우선
