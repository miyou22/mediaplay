# Design Document

## 1. 프로젝트 목적

영상 파일을 "보관"이 아니라
"관리"하기 위한 로컬 프로그램 제작.

파일 자체 이동보다
보유 여부 확인과 정보 관리에 초점.

---

## 2. 핵심 개념

### Library

영상 파일 목록

### Metadata

영상 정보 (제목, 코드, 배우 등)

### Actor Database

배우 정보 관리용 별도 DB

---

## 3. 기능 구조

### 1) 스캔

- 특정 폴더 수동 스캔
- 파일 경로 저장
- 파일명 분석
- 중복 체크

---

### 2) 데이터 구조

#### Video Table

- id
- filename
- filepath
- drive
- filesize
- added_date

#### Metadata Table

- video_id
- title_kr
- title_jp
- studio
- release_date

#### Actor Table

- actor_id
- name_kr
- name_jp
- alias

#### VideoActor Mapping

- video_id
- actor_id

---

### 3) UI 방향

- 단순 리스트 중심
- 빠른 검색
- 폴더 구조 의존 최소화
- 썸네일 선택적 표시

---

## 4. 메타데이터 전략

현재:

- 테이블만 생성
- 수동 입력

추후:

- 자동 수집
- 외부 사이트 연동 (접속 제한 고려)

---

## 5. 개발 단계

1. DB 구조 생성
2. 폴더 스캔 기능
3. 파일 리스트 UI
4. 배우 DB 연결
5. 메타데이터 입력 UI
6. EXE 빌드

---

## 6. 원칙

- 과설계 금지
- 기능 하나씩 완성
- 실제 사용 가능 상태 유지
