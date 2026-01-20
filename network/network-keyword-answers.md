# 네트워크 키워드 답변 정리 (Network Keyword Answers)

---

## 1️⃣ TCP vs UDP

### 🎯 한 줄 핵심
- **신뢰성(TCP) vs 속도(UDP)**

### 🔑 키워드
- TCP
  - 연결 지향
  - 3-way handshake
  - 순서 보장
  - 재전송
- UDP
  - 비연결
  - 빠름
  - 손실 가능
- 선택 기준
  - 데이터 중요도
  - 실시간성

### 🗣 말하기 가이드
- “TCP는 신뢰성, UDP는 속도”
- “금융/HTTP는 TCP”
- “스트리밍/게임은 UDP”

---

## 2️⃣ HTTP / HTTPS

### 🎯 한 줄 핵심
- **HTTP는 평문, HTTPS는 암호화**

### 🔑 키워드
- HTTP
  - Stateless
  - 요청/응답
- HTTPS
  - TLS
  - 인증서
  - 암호화
- 영향
  - 보안
  - 성능 비용

### 🗣 말하기 가이드
- “HTTPS는 TLS로 통신 암호화”
- “초기 핸드셰이크 비용 존재”
- “현대 서버에서는 필수”

---

## 3️⃣ Keep-Alive / Connection

### 🎯 한 줄 핵심
- **연결 재사용으로 성능 개선**

### 🔑 키워드
- Connection 생성 비용
- Keep-Alive
- Connection Pool
- RTT 감소

### 🗣 말하기 가이드
- “매 요청마다 연결 생성은 비효율”
- “Keep-Alive로 연결 재사용”
- “응답 시간과 서버 부하 감소”

---

## 4️⃣ 네트워크 지연과 서버 성능

### 🎯 한 줄 핵심
- **네트워크는 항상 느리다**

### 🔑 키워드
- RTT
- Latency
- Timeout
- 외부 API 호출
- 장애 전파

### 🗣 말하기 가이드
- “네트워크 지연은 피할 수 없음”
- “외부 호출이 서버 병목”
- “Timeout/Retry 설계 중요”

---

## 🎤 네트워크 답변 공식

