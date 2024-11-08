# 이벤트 선착순 쿠폰 시스템

## 📖 Background
네고왕 선착순 쿠폰 이벤트는 한정된 수량의 쿠폰을 먼저 신청한 사용자에게 제공하는 이벤트입니다.

## 📋 Requirements
- **이벤트 기간 내 발급 가능**: 예를 들어, 2023-11-03일 오후 1시 ~ 2023-11-04일 오후 1시 사이에만 발급이 가능합니다.
- **유저당 1번의 쿠폰 발급**: 선착순 이벤트는 사용자당 한 번만 쿠폰이 발급될 수 있습니다.
- **최대 쿠폰 발급 수량 설정 가능**: 선착순 쿠폰의 최대 발급 수량을 설정할 수 있어야 합니다.

## ⚙️ Architecture
- **비동기 쿠폰 발급 요청 처리 구조**
- **캐시 데이터 기반 Validation**

## 🛠️ Tech Stack

### Infra
- **AWS EC2**
- **AWS RDS**
- **AWS Elastic Cache**

### Server
- **Java 17**
- **Spring Boot 3.1**
- **Spring MVC**
- **JPA**
- **QueryDSL**

### Database
- **MySQL**
- **Redis**
- **H2**

### Monitoring
- **AWS CloudWatch**
- **Spring Actuator**
- **Prometheus**
- **Grafana**

### Etc
- **Locust**
- **Gradle**
- **Docker**

## 📌 Main Feature
1. **쿠폰 발급 검증**
   - 발급 기한 확인
   - 발급 수량 확인
   - 중복 발급 방지
2. **쿠폰 발급 수량 관리**
   - Redis `Set` 기반 재고 관리
3. **비동기 쿠폰 발급**
   - Redis `List` (발급 Queue)
   - Queue Polling Scheduler
