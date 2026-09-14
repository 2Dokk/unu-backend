# CNU&U Backend

서강대학교 학회 운영·활동 관리 서비스 **CNU&U**의 백엔드입니다.
학회원 관리, 활동 모집·신청, 출석, 공지, 예산 관리 API를 제공합니다.

## 기술 스택

- Java 21, Spring Boot 3.5
- Spring Data JPA, PostgreSQL
- Spring Security (JWT, `@PreAuthorize` 권한 제어)
- Apache POI (예산안 엑셀 내보내기·업로드)

## 실행

로컬 설정 파일 `src/main/resources/application-local.properties`에 DB 비밀번호와 JWT 시크릿을 넣은 뒤 실행합니다.
(이 파일은 저장소에 커밋하지 않습니다.)

```bash
SPRING_PROFILES_ACTIVE=local ./gradlew bootRun
```

## 주요 도메인

| 패키지 | 내용 |
|---|---|
| `activity`, `activity_participant` | 활동 개설, 모집, 신청, 수료 |
| `budget` | 월별 예산안(예상·실제), 스터디 보증금 원장, 지출 건별 내역, 엑셀 내보내기·업로드 |
| `applicant_notification` | 운영진·담당자용 신청자 알림 |
