# 📚 librispace-api

**멀티 테넌시 기반 도서 관리 SaaS 백엔드 API**

> React 프론트엔드와 분리된 구조로 운영되며, 각 기관/조직(테넌트)별 도서, 회원, 대출 기능을 제공합니다.

## 🚀 주요 기능

- ✅ 테넌트 기반 사용자/도서/회원 데이터 격리
- ✅ JWT 기반 로그인 및 권한 인가
- ✅ 도서 등록/조회/대출/반납 기능
- ✅ Redis 기반 API Rate Limiting (요금제 적용 가능)
- ✅ Swagger UI로 API 문서 자동화
- ✅ Docker 기반 배포 환경 구성

## 🛠 기술 스택

| 영역 | 사용 기술 |
|------|-----------|
| 언어 | Java 17 |
| 프레임워크 | Spring Boot 3, Spring Security, Spring Data JPA |
| 인증 | JWT (jjwt), Spring Security |
| DB | MySQL |
| 캐시/속도제한 | Redis, Bucket4j |
| 문서화 | Swagger / SpringDoc |
| 배포 | Docker, GitHub Actions (예정) |

## 🧱 아키텍처 개요

```
[사용자] → [프론트엔드] → [Librispace API] → [DB (테넌트별)]  
                                ↓  
                            [Redis (Rate Limit)]
```

## 📦 프로젝트 구조 (예시)

```
com.librispace
├── config
├── controller
├── domain (book, member, loan, tenant, user 등)
├── dto
├── filter
├── repository
├── security
├── service
└── ...
```

## 🧪 실행 방법

### ✅ 1. 환경 설정

`application.yml` 파일 생성:

```yaml
spring:
  datasource:
    url: jdbc:mysql://localhost:3306/librispace
    username: root
    password: your_password
  jpa:
    hibernate:
      ddl-auto: update

jwt:
  secret: your_jwt_secret
```

### ✅ 2. 실행

```bash
./gradlew bootRun
```

## 📑 API 문서

Swagger UI: `http://localhost:8080/swagger-ui/index.html`

## 📄 라이선스

MIT License
