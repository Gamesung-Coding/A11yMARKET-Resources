# [11월 4주차 프로젝트 수행 일지]

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

- 연동 작업이 미흡하여 간편 로그인 구현 일정 연기

- **접근성 설정 저장 및 조회 API** - 담당자: 김수민

  - 기존의 `a11y_profile` 테이블 대신 `usre-a11y-settings` 테이블 새로 작성
  - 프론트의 `localStorage` 외에도 계정 자체에 설정을 저장할 수 있도록 구성
  - 엔드포인트 구성
  - References: PR [#91](https://github.com.Gamesung-Coding/a11y-market-server/pull/91), Issue [#18](https://github.com/Gamesung-Coding/a11y-market-server/issues/18) [#19](https://github.com/Gamesung-Coding/a11y-market-server/issues/19), 요구 기능 명세서 [#REQ-4 #REQ-5](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)

- **관리자 기능 - 주문 상태 변경** - 담당자: 백여랑

  - 관리자가 특정 주문의 상태를 (강제적으로) 변경하는 기능 API 구현
  - 프론트와 연동과정에서 리팩토링 예정
  - References: PR [#92](https://github.com.Gamesung-Coding/a11y-market-server/pull/92), Issue [#61](https://github.com/Gamesung-Coding/a11y-market-server/issues/61), 요구 기능 명세서 [#REQ-51](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)

- **회원정보 기능 - 주문 내역 및 상세 조회** - 담당자: 김수민

  - 마이페이지 내 주문 목록 및 상세 조회 API 구현
  - 주문 내역 리스트 조회, 특정 주문 내역 조회 2개 엔드포인드 구성
  - References: PR [#93](https://github.com.Gamesung-Coding/a11y-market-server/pull/93), Issue [#20](https://github.com/Gamesung-Coding/a11y-market-server/issues/20) [#21](https://github.com/Gamesung-Coding/a11y-market-server/issues/21), 요구 기능 명세서 [#REQ-22 #REQ-59](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)

- **관리자 기능 - 판매자 가입 신청 관리 API** - 담당자: 백여랑

  - 관리자의 기능 중, 판매자 계정가입 신청을 승인 및 거절 하는 기능
  - 관리자의 상태를 `PENDING`에서 변경하여 논리적으로 승인/거절 처리
  - References: PR [#94](https://github.com.Gamesung-Coding/a11y-market-server/pull/94), Issue [#55](https://github.com/Gamesung-Coding/a11y-market-server/issues/55), 요구 기능 명세서 [#REQ-48](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)

- **판매자 기능 - 주문 클레임 처리 API** - 담당자: 신운용

  - 구매자가 제기한 클레임(취소/반품/교환)을 처리하는 기능 API
  - 논리적으로 상태를 변경하는 방식으로 구현
  - References: PR [#95](https://github.com.Gamesung-Coding/a11y-market-server/pull/95), Issue [#44](https://github.com/Gamesung-Coding/a11y-market-server/issues/44), 요구 기능 명세서 [#REQ-44](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)

- **판매자 기능 - 주문 클레임 조회** - 담당자: 신운용

  - 구매자가 제기한 클레임(취소/반품/교환)을 조회하는 기능 API
  - References: PR [#96](https://github.com.Gamesung-Coding/a11y-market-server/pull/96), Issue [#43](https://github.com/Gamesung-Coding/a11y-market-server/issues/43), 요구 기능 명세서 [#REQ-44](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)

- **주문 취소 요청 기능 API** - 담당자: 김수민

  - 배송 전 주문에 대해 취소하는 기능 API
  - References: PR [#97](https://github.com.Gamesung-Coding/a11y-market-server/pull/97), Issue [#22](https://github.com/Gamesung-Coding/a11y-market-server/issues/22), 요구 기능 명세서 [#REQ-22](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)

- **구매 확정 처리 기능 API** - 담당자: 김수민

  - 배송이 완료된 상품에 대해 구매를 확정처리하는 기능 API
  - References: PR [#98](https://github.com.Gamesung-Coding/a11y-market-server/pull/98), Issue [#45](https://github.com/Gamesung-Coding/a11y-market-server/issues/45), 요구 기능 명세서 [#REQ-84](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)

- **결제 검증 처리** - 담당자: 김수민

  - 주문 검증 기능 - 임시적으로 구현됨
  - References: PR [#99](https://github.com.Gamesung-Coding/a11y-market-server/pull/99), Issue [#36](https://github.com/Gamesung-Coding/a11y-market-server/issues/36), 요구 기능 명세서 [#REQ-65](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)

- **관리자 기능 - 판매자 정보 수정 기능 API** - 담당자: 백여랑

  - 관리자가 판매자의 정보를 (강제적으로) 수정하는 기능 API
  - 인증 및 권한 체크의 경우, Filter를 추가하거나 이후 리팩토링 예정
  - References: PR [#100](https://github.com.Gamesung-Coding/a11y-market-server/pull/100), Issue [#56](https://github.com/Gamesung-Coding/a11y-market-server/issues/56), 요구 기능 명세서 [#REQ-48](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)

- **판매자 기능 - 판매자 대시보드 정보 조회** - 담당자: 신운용

  - 대시보드 정보 조회 기능 API
  - View 테이블의 정보를 조회하여 반환
  - References: PR [#102](https://github.com.Gamesung-Coding/a11y-market-server/pull/102), Issue [#37](https://github.com/Gamesung-Coding/a11y-market-server/issues/37), 요구 기능 명세서 [#REQ-42](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)

- **프론트와의 API 연동 과정에서 응답 리팩토링** - 담당자: 안규태

  - 프론트엔드와 API 연동 시 누락되었거나 불필요한 컴포넌트 및 API 최적화
  - 몇몇 잘못된 동작 리팩토링
  - References: PR [#101](https://github.com.Gamesung-Coding/a11y-market-server/pull/101) [#103](https://github.com.Gamesung-Coding/a11y-market-server/pull/103)

#### 프론트엔드

- **판매자 - 상품 등록 페이지** - 담당자: 장지훈

  - 판매자 상품 등록 신청 페이지
  - References: PR [#70](https://github.com.Gamesung-Coding/a11y-market-web/pull/70), Issue [#38](https://github.com/Gamesung-Coding/a11y-market-web/issues/38), 요구 기능 명세서 [#REQ-41](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)

- **접근성 설정 오버레이 구현** - 담당자: 김수민

  - 접근성 오버레이 창 구현
  - 각 설정에 따른 일괄 CSS 적용 로직 구현
  - References: PR [#71](https://github.com.Gamesung-Coding/a11y-market-web/pull/71), Issue [#12](https://github.com/Gamesung-Coding/a11y-market-web/issues/12), 요구 기능 명세서 [#REQ-13](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)

- **localStorage를 활용한 접근성 설정 저장** - 담당자: 김수민

  - 접근성 설정을 `localStorage`에 저장 및 복원하는 로직 구현
  - References: PR [#73](https://github.com.Gamesung-Coding/a11y-market-web/pull/73), Issue [#72](https://github.com/Gamesung-Coding/a11y-market-web/issues/72), 요구 기능 명세서 [#REQ-89](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)

- **장바구니 페이지 리팩토링** - 담당자: 안규태

  - Figma를 기반으로 하여 디자인을 수정
  - 글자로 된 아이콘 대신 svg 기반의 아이콘으로 변경
  - API 기능 연동 완료
  - References: PR [#74](https://github.com.Gamesung-Coding/a11y-market-web/pull/74)

- **판매자 상품 수정 Form** - 담당자: 장지훈

  - 상품 정보 수정 폼 작성
  - References: PR [#75](https://github.com.Gamesung-Coding/a11y-market-web/pull/75), Issue [#40](https://github.com/Gamesung-Coding/a11y-market-web/issues/40), 요구 기능 명세서 [#REQ-46](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)

- **회원정보 - 주문 내역 조회** - 담당자: 김수민, 안규태

  - 주문 내역 정보 조회 페이지 작성 (김수민)
  - API 연동 및 응답 파싱 결과 수정 (안규태)
  - References: PR [#76](https://github.com.Gamesung-Coding/a11y-market-web/pull/76) [#78](https://github.com.Gamesung-Coding/a11y-market-web/pull/78), Issue [#16](https://github.com/Gamesung-Coding/a11y-market-web/issues/16) [#17](https://github.com/Gamesung-Coding/a11y-market-web/issues/17), 요구 기능 명세서 [#REQ-73 #REQ-59](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)

- **판매자 - 클레임 관리** - 담당자: 장지훈

  - 판매자 취소/반품/교환 신청 목록 및 상태를 관리하는 페이지 작성
  - References: PR [#77](https://github.com.Gamesung-Coding/a11y-market-web/pull/77), Issue [#43](https://github.com/Gamesung-Coding/a11y-market-web/issues/43) [#44](https://github.com/Gamesung-Coding/a11y-market-web/issues/44), 요구 기능 명세서 [#REQ-44](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)

- **회원정보 수정 페이지** - 담당자: 백여랑

  - 회원 정보를 수정하는 페이지 작성
  - 백엔드 API와 연동하여 기능 구현
  - References: PR [#79](https://github.com.Gamesung-Coding/a11y-market-web/pull/79), Issue [#20](https://github.com/Gamesung-Coding/a11y-market-web/issues/20), 요구 기능 명세서 [#REQ-16](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)

- **판매자 - 계정 신청 페이지** - 담당자: 장지훈

  - 판매자 계정 신청 페이지 작성
  - References: PR [#80](https://github.com.Gamesung-Coding/a11y-market-web/pull/80), Issue [#45](https://github.com/Gamesung-Coding/a11y-market-web/issues/45), 요구 기능 명세서 [#REQ-40](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)

- **판매자 - 내 상품 조회** - 담당자: 신운용

  - 판매자 자신의 상품을 조회하는 페이지 작성
  - API 연동 없이 Mock 데이터 기반으로 우선 구현
  - 이후 리팩토링 예정
  - References: PR [#81](https://github.com.Gamesung-Coding/a11y-market-web/pull/81), Issue [#39](https://github.com/Gamesung-Coding/a11y-market-web/issues/39), 요구 기능 명세서 [#REQ-46](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)

### 1.2. 차주 프로젝트 수행 계획

- **Backend:**
  - 작성한 코드 및 리팩토링된 코드에 맞추어 테스트 코드 작성
  - 간편 로그인 기능 구현
  - 프론트엔드에서 필요한 응답에 따라 DTO 등 수정
- **Frontend:**
  - 백엔드 Swagger 기반으로 지속적으로 연동 작업
  - 디자인/접근성 측면에서 모호한 스타일링 부분에 대해 재작업 예정
  - 일관성이 부족한 코드를 리뷰하여 리팩토링 예정
  - PG사의 테스트 결제를 사용할지 논의하여 구현/보류 예정

---

## 2. 강사님 피드백

- 프로젝트 막바지에 접어 들었으므로 선택과 집중을 할 시기 입니다
- 중심 컨텐츠에 집중해서 구현 완성 하시고 그 외 부가 기능은 차후 개발 하는 방향으로 진행하는걸 권장합니다
- 코드 리뷰나 리팩토링은 많은 경험과 배움을 진행할 수 있으니 모든 팀원들이 리뷰에 참여하고 경험하시면 좋을 것 같습니다
