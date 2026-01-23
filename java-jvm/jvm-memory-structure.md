# JVM Memory Structure (JVM 메모리 구조)

## 1. 개념 정리
JVM(JVM Memory Structure) 메모리 구조는
Java 애플리케이션 실행 중 사용되는 메모리를
역할에 따라 여러 영역으로 나누어 관리하는 구조이다.

JVM 메모리는 크게 다음 영역으로 구성된다.

- Method Area
- Heap
- Stack
- PC Register
- Native Method Stack

이 중 백엔드 개발자에게 가장 중요한 영역은
Heap과 Stack이다.

---

## 2. 왜 중요한가
JVM 메모리 구조를 이해하지 못하면:
- OutOfMemoryError 원인 분석 불가
- GC 동작 원리 이해 불가
- 메모리 누수 판단 어려움
- 운영 장애 시 원인 파악 실패

특히 장시간 실행되는 서버 애플리케이션에서는
메모리 문제 = 서비스 장애로 직결되기 때문에
JVM 메모리 구조는 필수 지식이다.

---

## 3. 백엔드 실무 관점
각 메모리 영역의 역할은 다음과 같다.

### Method Area
- 클래스 메타 정보 저장
- static 변수, 상수, 메서드 정보 저장
- 클래스 로딩 시 생성
- GC 대상이 아님 (또는 제한적)

### Heap
- 객체 인스턴스 저장
- 모든 스레드가 공유
- GC의 주요 대상
- Young / Old 영역으로 분리됨

### Stack
- 메서드 호출 시 생성되는 프레임 저장
- 지역 변수, 매개변수, 리턴 주소 관리
- 스레드별로 독립적
- 재귀 호출이 깊어지면 StackOverflowError 발생

### PC Register
- 현재 실행 중인 JVM 명령어 주소 저장
- 스레드별로 존재

### Native Method Stack
- JNI 기반 네이티브 코드 실행을 위한 스택
- C/C++ 코드 호출 시 사용

실무에서는:
- 메모리 이슈의 대부분이 Heap 문제
- Stack 문제는 재귀, 스레드 과다 생성 시 발생

하는 경우가 많다.

---

## 4. 트레이드오프 / 주의사항
- Heap을 크게 잡으면 GC 주기가 길어질 수 있다
- Stack 크기가 작으면 StackOverflowError 발생 가능
- static 객체는 GC 대상이 아니어서 메모리 누수 위험 존재
- 장시간 참조되는 객체는 Old 영역에 쌓여 Full GC 부담 증가

즉,
> JVM 메모리는 무조건 크게 잡는 것이 아니라,
> 서비스 특성에 맞게 균형 있게 설계해야 한다.

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
Stack은 스레드별로 메서드 실행 정보를 저장하는 독립 영역입니다.

---

### Q3. static 변수는 어디에 저장되나요?
A.
Method Area에 저장되며,
GC 대상이 아니기 때문에 메모리 누수에 주의해야 합니다.

---

## 6. 한 문장 요약 (면접용)
JVM 메모리 구조는
객체 저장과 실행 흐름을 분리해 관리하며,
백엔드 서버에서는 Heap과 GC 이해가 핵심이다.
