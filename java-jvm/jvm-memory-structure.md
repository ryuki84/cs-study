# JVM Memory Structure (JVM 메모리 구조)

## 1. 개념 정리
JVM(Java Virtual Machine)은
Java 애플리케이션을 실행하기 위한 가상 머신으로,
프로그램 실행 중 필요한 메모리를 여러 영역으로 나누어 관리한다.

JVM 메모리는 크게 다음과 같이 구성된다.

- Method Area
- Heap
- Stack
- PC Register
- Native Method Stack

이 중 백엔드 개발자가 가장 중요하게 이해해야 할 영역은
Heap과 Stack이다.

---

## 2. 왜 중요한가
JVM 메모리 구조를 이해하지 못하면:
- OutOfMemoryError 원인 분석 불가
- 메모리 누수 판단 어려움
- GC 튜닝 개념 이해 불가
- 장애 상황에서 원인 파악 실패

특히 장시간 실행되는 백엔드 서버에서는
메모리 관리 문제가 곧 서비스 장애로 이어질 수 있다.

---

## 3. 백엔드 실무 관점
각 메모리 영역의 역할은 다음과 같다.

- Method Area
  - 클래스 정보, static 변수, 상수 저장
  - 클래스 로딩 시 생성

- Heap
  - 객체 인스턴스 저장
  - GC의 주요 대상
  - Young / Old 영역으로 분리됨

- Stack
  - 메서드 호출 시 생성되는 프레임 저장
  - 지역 변수, 매개변수, 리턴 주소 관리
  - 스레드별로 독립적

- PC Register
  - 현재 실행 중인 JVM 명령어 주소 저장

- Native Method Stack
  - JNI 기반 네이티브 코드 실행용

실무에서는:
- 메모리 이슈의 대부분이 Heap 문제
- Stack은 재귀 오류나 과도한 스레드 생성 시 문제 발생

하는 경우가 많다.

---

## 4. 트레이드오프 / 주의사항
- Heap을 크게 잡으면 GC 주기가 길어질 수 있다
- Stack 크기가 작으면 StackOverflowError 발생
- static 객체는 GC 대상이 아니어서 메모리 누수 위험 존재

즉,
> JVM 메모리는 무조건 크게가 아니라,
> 서비스 특성에 맞게 설계해야 한다.

라는 트레이드오프가 존재한다.

---

## 5. 예상 면접 질문 & 답변 연습

### Q1. JVM 메모리 구조를 설명해 주세요.
A.
JVM 메모리는 Method Area, Heap, Stack, PC Register, Native Method Stack으로 구성되며,
객체는 Heap에 저장되고 메서드 실행 정보는 Stack에 저장됩니다.

---

### Q2. Heap과 Stack의 가장 큰 차이는 무엇인가요?
A.
Heap은 객체 인스턴스를 저장하는 공유 영역이고,
Stack은 스레드별로 메서드 호출 정보를 저장하는 독립 영역입니다.

---

### Q3. static 변수는 어디에 저장되나요?
A.
Method Area에 저장되며,
GC 대상이 아니기 때문에 메모리 누수에 주의해야 합니다.

---

## 6. 한 문장 요약 (면접용)
JVM 메모리 구조는
객체와 실행 흐름을 분리해 관리하며,
백엔드 서버에서는 Heap 관리와 GC 이해가 핵심이다.
