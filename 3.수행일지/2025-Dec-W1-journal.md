# [0월 0주차 프로젝트 수행 일지]

<div align="center">
  <table width="100%">
    <tbody>
      <tr>
        <th align="center">프로젝트 타이틀</th>
        <td colspan="3">A11yMARKET</td>
      </tr>
      <tr>
        <th>프로젝트 팀명</th>
        <td>겜성코딩</td>
        <th>프로젝트 팀원</th>
        <td>
          <span>(팀장) 안규태</span><br />
          <span>(팀원) 김수민, 백여랑, 신운용, 장지훈</span>
        </td>
      </tr>
    </tbody>
  </table>
</div>
  
---
## 1. 프로젝트 수행 계획 및 현황

### 1.1. 금주 프로젝트 수행 내용

- **QA** - Reviewer: 안규태
  - 각 PR의 코드 리뷰 및 코멘트

#### 백엔드

- **이미지 업로드 기능 추가** - 담당자: 안규태

  - AWS S3와 호환되는 방식의 이미지 업로드 구현
  - DB 테이블 구조를 조정하고 MinIO를 사용
  - References: PR [&#35;105](https://github.com/Gamesung-Coding/a11y-market-server/pull/105), Issues [&#35;38](https://github.com/Gamesung-Coding/a11y-market-server/issues/38), 요구 기능 명세서 [&#35;REQ-41](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)

- **a11y profile CRUD api 생성** - 담당자: 김수민

  - user_a11y_profiles 테이블 추가
  - 마이페이지에서 사용자 커스텀 접근성 설정을 불러오고 수정할 수 있도록 api 추가
  - References: PR [&#35;106](https://github.com/Gamesung-Coding/a11y-market-server/pull/106), Issues [&#35;19](https://github.com/Gamesung-Coding/a11y-market-server/issues/19), 요구 기능 명세서 [&#35;REQ-4](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)

- **회원 탈퇴 API** - 담당자: 안규태

  - 회원 탈퇴를 수행하는 APi 구현
  - 연관 테이블에 대해 cascade 또는 set null 적용
  - 각 테이블의 제약 조건 조정을 위한 SQL 및 JPA 쿼리문 수정
  - JPA 리포지토리에서 네이티브 쿼리 대신 쿼미 메소드 이름을 사용하도록 리팩토링
  - References: PR [&#35;107](https://github.com/Gamesung-Coding/a11y-market-server/pull/112), Issue [&#35;10](https://github.com/Gamesung-Coding/a11y-market-server/issues/10), 요구 기능 명세서 [&#35;REQ-9](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)

- **프론트와 연동될 이메일 중복 체크 API 추가** - 담당자: 김수민

  - References: PR [&#35;110](https://github.com/Gamesung-Coding/a11y-market-server/pull/110), Issues [&#35;108](https://github.com/Gamesung-Coding/a11y-market-server/issues/108)

- **카카오 인증 기능 API 구현** - 담당자: 안규태

  - OAuth2의 로그인 및 회원 가입 API 구현
  - 카카오 회원가입 시 필요한 null 허용 조건에 대해 DB 스키마에 적용
  - 임시 토큰을 발급하여 회원 가입을 진행하도록 구현
  - References: PR [&#35;111](https://github.com/Gamesung-Coding/a11y-market-server/pull/111), Issues [&#35;3](https://github.com/Gamesung-Coding/a11y-market-server/issues/3) [&#35;9](https://github.com/Gamesung-Coding/a11y-market-server/issues/3), 요구 기능 명세서 [&#35;REQ-3 &#35;REQ-12](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)

- **관리자 기능 - 시스템 전체 주문 내역 필터링 기능 추가** - 담당자: 백여랑

  - user_a11y_profiles 테이블 추가
  - 마이페이지에서 사용자 커스텀 접근성 설정을 불러오고 수정할 수 있도록 api 추가
  - References: PR [&#35;112](https://github.com/Gamesung-Coding/a11y-market-server/pull/112)

- **회원 가입 시 정보 중복 체크 엔드포인드 추가** - 담당자: 안규태

  - 이메일, 닉네임, 휴대폰 번호 등 DB에 등록된 데이타와의 중복 여부를 확인하도록 구성
  - References: PR [&#35;113](https://github.com/Gamesung-Coding/a11y-market-server/pull/113)

- **메인 페이지의 상품 조회 시 필요한 뷰 및 엔드포인트 추가** - 담당자: 안규태

  - 인기상품과 같은 상품 리스트 조회 시 필요한 뷰 테이블 추가
  - References: PR [&#35;114](https://github.com/Gamesung-Coding/a11y-market-server/pull/114)

- **상품 업로드 시 상품 요약 기능 추가** - 담당자: 안규태
  - 상품 업로드 시, 설명 사진을 기반으로 AI가 제품의 정보를 요약하는 기능 추가
  - 기타 엔드포인트 추가 및 코드 리팩토링
  - References: PR [&#35;115](https://github.com/Gamesung-Coding/a11y-market-server/pull/115)

#### 프론트엔드

- **관리자 페이지 - 사용자 리스트 조회** - 담당자: 백여랑

  - 관리자 기능의 회원 목록 조회 페이지 구현
  - API 연동 됨
  - References: PR [&#35;82](https://github.com/Gamesung-Coding/a11y-market-web/pull/82), Issues [&#35;50](https://github.com/GamesungCoding/a11y-market-web/issues/50), 요구 기능 명세서 [&#35;REQ-47](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)

- **판매자 페이지 - 대시보드 페이지** - 담당자: 신운용

  - 판매자의 대시보드 페이지 추가
  - References: PR [&#35;83](https://github.com/Gamesung-Coding/a11y-market-web/pull/83), Issues [&#35;37](https://github.com/GamesungCoding/a11y-market-web/issues/37), 요구 기능 명세서 [&#35;REQ-42](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)

- **판매자 페이지 - 주문 접수 및 배송 처리** - 담당자: 장지훈

  - 판매자의 주문 리스트 조회 및 접수, 배송 처리 페이지 작성
  - References: PR [&#35;85](https://github.com/Gamesung-Coding/a11y-market-web/pull/85), Issues [&#35;42](https://github.com/GamesungCoding/a11y-market-web/issues/42), 요구 기능 명세서 [&#35;REQ-43](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)

- **주문 취소 요청 기능** - 담당자: 김수민

  - 마이페이지의 주문 내역에서 주문 취소 요청 기능 UI 구현
  - References: PR [&#35;86](https://github.com/Gamesung-Coding/a11y-market-web/pull/86), Issues [&#35;18](https://github.com/GamesungCoding/a11y-market-web/issues/18), 요구 기능 명세서 [&#35;REQ-22](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)

- **판매자 접근성 인증 마크** - 담당자: 김수민

  - 판매자 접근성 인증 마크 구현
  - References: PR [&#35;87](https://github.com/Gamesung-Coding/a11y-market-web/pull/87), Issues [&#35;53](https://github.com/GamesungCoding/a11y-market-web/issues/53), 요구 기능 명세서 [&#35;REQ-66](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)

- **회원 탈퇴 페이지 작성** - 담당자: 장지훈

  - 회원 탈퇴 페이지 작성
  - References: PR [&#35;88](https://github.com/Gamesung-Coding/a11y-market-web/pull/88), Issues [&#35;14](https://github.com/GamesungCoding/a11y-market-web/issues/14), 요구 기능 명세서 [&#35;REQ-13](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)

- **관리자 - 상품 등록 신청 관리** - 담당자: 신운용

  - 상품 등록 신청을 관리하는 페이지 추가
  - References: PR [&#35;89](https://github.com/Gamesung-Coding/a11y-market-web/pull/89), Issues [&#35;47](https://github.com/GamesungCoding/a11y-market-web/issues/47), 요구 기능 명세서 [&#35;REQ-49](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)

- **관리자 - 회원 권한 관리** - 담당자: 신운용

  - 사용자의 권한을 일반 사용자, 판매자로 권한 조정
  - References: PR [&#35;90](https://github.com/Gamesung-Coding/a11y-market-web/pull/90), Issues [&#35;51](https://github.com/GamesungCoding/a11y-market-web/issues/51), 요구 기능 명세서 [&#35;REQ-50](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)

- **접근성 프로필 설정** - 담당자: 김수민

  - 마이페이지의 접근성 프로필 UI 구현
  - References: PR [&#35;91](https://github.com/Gamesung-Coding/a11y-market-web/pull/91), Issues [&#35;15](https://github.com/GamesungCoding/a11y-market-web/issues/15), 요구 기능 명세서 [&#35;REQ-19](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)

- **구매 확정 페이지 추가** - 담당자: 장지훈

  - 상품 구매 이후 구매 확정 페이지 추가
  - References: PR [&#35;92](https://github.com/Gamesung-Coding/a11y-market-web/pull/92), Issues [&#35;19](https://github.com/GamesungCoding/a11y-market-web/issues/19), 요구 기능 명세서 [&#35;REQ-84](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)

- **관리자: 전체 주문 관리 페이지** - 담당자: 백여랑

  - 시스템에 등록된 전체 주문 조회 및 관리 페이지
  - References: PR [&#35;94](https://github.com/Gamesung-Coding/a11y-market-web/pull/94), Issues [&#35;48](https://github.com/GamesungCoding/a11y-market-web/issues/48), 요구 기능 명세서 [&#35;REQ-51](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)

- **사용자 프로필 조회** - 담당자: 김수민

  - 마이페이지의 사용자 프로필 조회 페이지 추가
  - References: PR [&#35;95](https://github.com/Gamesung-Coding/a11y-market-web/pull/95), Issues [&#35;22](https://github.com/GamesungCoding/a11y-market-web/issues/22), 요구 기능 명세서 [&#35;REQ-6](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)

- **간편 로그인(카카오) 및 회원가입 구현** - 담당자: 안규태

  - 카카오 간편 로그인 및 간편 회원가입 구현
  - 회원 가입 폼을 더 접근성 있게 변경
  - API 연동됨
  - References: PR [&#35;96](https://github.com/Gamesung-Coding/a11y-market-web/pull/96), Issues [&#35;7](https://github.com/GamesungCoding/a11y-market-web/issues/7) [&#35;11](https://github.com/GamesungCoding/a11y-market-web/issues/11), 요구 기능 명세서 [&#35;REQ-3 &#35;REQ-12](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)

- **회원 가입 폼을 일관성 있게 수정** - 담당자: 안규태

  - 회원 가입 시 회원 가입 폼을 간편 회원 가입 UI와 동일하게 작성
  - 한번에 하나의 정보만 입력받아 접근성 있게 구현
  - References: PR [&#35;98](https://github.com/Gamesung-Coding/a11y-market-web/pull/98)

- **메인페이지, 인증 기능 페이지, 상품 등록 페이지 리팩토링 진행 중** - 담당자: 안규태

- API 연동 및 잘못된 레이아웃 수정
- 필요한 경우 API 재설계
- References: PR [&#35;98](https://github.com.Gamesung-Coding/a11y-market-web/pull/98) [&#35;100](https://github.com.Gamesung-Coding/a11y-market-web/pull/100) [&#35;101](https://github.com.Gamesung-Coding/a11y-market-web/pull/101)

### 1.2. 차주 프로젝트 수행 계획

- **Backend:**

  - 미작성된 테스트 코드 작성 또는 Swagger를 사용하여 API 응답 점검
  - Docker를 사용하여 배포 테스트 진행
  - QA 서버를 사용하여 기능 동작 점검
  - AWS EC2 환경에 배포
  - Docker, Traefik, MinIO, Oracle 21c XE를 사용하여 환경 구축
  - 페르소나 등에 맞춘 상품 데이터 삽입

- **Frontend:**
  - 미 연동된 API 연동 작업 수행
  - Vitest를 사용하여 로직 동작 점검
  - Docker 및 Github Action을 통한 배포 테스트 진행
  - QA 서버를 사용하여 기능 동작 점검
  - AWS EC2 환경에 배포
  - Docker, Traefik, Nginx를 사용하여 환경 구축

---

## 2. 강사님 피드백

내용
