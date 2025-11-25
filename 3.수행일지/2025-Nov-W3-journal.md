# [11월 3주차 프로젝트 수행 일지]

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

- **응답 결과 검증** - 담당자: 안규태
  - DB의 더미데이터를 통해 정상적으로 응답하는지 확인

#### 백엔드

- **기본 배송지 관리 기능 API** - 담당자: 백여랑
  - 기본배송지 조회 및 수정을 위한 엔드포인트 작성
  - Service 및 Repository 구성
  - References: [PR #73](https://github.com/Gamesung-Coding/a11y-market-server/pull/73), [Issue #67](https://github.com/Gamesung-Coding/a11y-market-server/issues/67), [요구 기능 명세서 #REQ-17](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)
- **판매자 계정 가입 신청 API** - 담당자: 신운용
  - 일반계정에서 판매자 계정으로 전환 신청 기능
  - 엔드포인트 및 기능 로직 구현
  - References: [PR #75](https://github.com/Gamesung-Coding/a11y-market-server/pull/75), [Issue #49](https://github.com/Gamesung-Coding/a11y-market-server/issues/49), [요구 기능 명세서 #REQ-40](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)
- **상품 등록 신청 API** - 담당자: 신운용
  - 판매자 계정의 회원이 상품등록을 신청하는 기능
  - 엔드 포인트 및 기능 로직 구현
  - References: [PR #77](https://github.com/Gamesung-Coding/a11y-market-server/pull/77), [Issue #38](https://github.com/Gamesung-Coding/a11y-market-server/issues/38), [요구 기능 명세서 #REQ-41](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)
- **결졔 정보 조회 기능 API** - 담당자: 김수민
  - 결제 준비 단계에서 결제 정보를 조회하는 기능 구현
  - `Order` Entity 구성
  - References: [PR #78](https://github.com/Gamesung-Coding/a11y-market-server/pull/78), [Issue #34](https://github.com/Gamesung-Coding/a11y-market-server/issues/34), [요구 기능 명세서 #REQ-87](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)
- **주문서 생성 기능 API** - 담당자: 김수민
  - 주문 시작 시, 해당 주문의 정보를 `order`, `order_items` 테이블에 저장
  - 배송지 및 장바구니 검증 후 총 금액을 계산하는 로직 구현
  - References: [PR #79](https://github.com/Gamesung-Coding/a11y-market-server/pull/79), [Issue #35](https://github.com/Gamesung-Coding/a11y-market-server/issues/35), [요구 기능 명세서 #REQ-87](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)
- **관리자 주문내역 전체 조회 기능 API** - 담당자: 백여랑
  - 관리자 유저가 주문내역 전체를 조회하는 기능 API
  - 각 요청에 대한 컴포넌트 작성
  - References: [PR #80](https://github.com/Gamesung-Coding/a11y-market-server/pull/80), [Issue #59](https://github.com/Gamesung-Coding/a11y-market-server/issues/59), [요구 기능 명세서 #REQ-51](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)
- **전체 백엔드 시스템에 대해 JWT 인증 방식으로 리팩토링** - 담당자: 안규태
  - 기능 파일의 접근 용이성을 위한 패키지 구조 변경
  - JWT 인증 기능 및 필터링 추가 후, 각 기능에서 `session` 대신 `UserDetails`를 사용하도록 리팩토링
  - Spring Boot Security의 CORS 허용 경로를 정확히 명시
  - 각 기능에서 Custom Exception을 사용하고 RestAdvice가 이를 처리하도록 핸들러를 추가
  - 각 DTO를 불변 객체인 record로 리팩토링
  - 각 패키지에 대해 불필요한 코드나 구조를 개선
  - 구현된 기능 별 기능 오류 또는 로직의 논리적 문제 개선
  - References: [PR #81](https://github.com/Gamesung-Coding/a11y-market-server/pull/81), [Issue #76](https://github.com/Gamesung-Coding/a11y-market-server/issues/76)
- **Swagger 설정 및 API 명세서 생성** - 담당자: 안규태
    - Swagger를 통해 현재 개발 완료된 API 엔드포인트를 명시하고, 테스트 할 수 있도록 구성
    - 각 기능 별 요청/응답 객체 구조 확인가능
    - References: [Commit #59f7aac](https://github.com/Gamesung-Coding/a11y-market-server/commit/59f7aaccbb1cb720a2ceefdc7846d53905ebefff), [Commit #dfe7d2b](https://github.com/Gamesung-Coding/a11y-market-server/commit/dfe7d2b62526f8a496e1bfbb05cdf779f0804240)
- **판매자 기능 - 내 상품 조회** - 담당자: 신운용
    - 내 상품 조회 엔드포인트 구현
    - JWT 인증 방식을 사용
    - References: [PR #82](https://github.com/Gamesung-Coding/a11y-market-server/pull/82), [Issue #47](https://github.com/Gamesung-Coding/a11y-market-server/issues/47), [요구 기능 명세서 #REQ-46](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)
- **판매자 기능 - 내 상품 수정 요청** - 담당자: 신운용
    - 내 상품 수정 요청(변경 내용을 관리자가 승인해야 함)하는 기능 API 구현
    - JWT 인증 방식을 사용
    - References: [PR #83](https://github.com/Gamesung-Coding/a11y-market-server/pull/83), [Issue #40](https://github.com/Gamesung-Coding/a11y-market-server/issues/40), [요구 기능 명세서 #REQ-46](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)

#### 프론트엔드

- 프론트엔드는 Figma에서 진행한 디자인을 기준으로 작성

- **공통 컴포넌트 작성** - 담당자: 안규태
  - 상단 네비게이션 컴포넌트 작성
  - 하단 푸터 컴포넌트 작성
  - 공통 컴포넌트를 최상위 레이아웃에 적용
  - References: [PR #54](https://github.com/Gamesung-Coding/a11y-market-web/pull/54), [PR #55](https://github.com/Gamesung-Coding/a11y-market-web/pull/55), [Issue #2](https://github.com/Gamesung-Coding/a11y-market-web/issues/2), [Issue #3](https://github.com/Gamesung-Coding/a11y-market-web/issues/3)
- **이메일 로그인 페이지 작성** - 담당자: 김수민
  - 이메일 로그인 페이지를 작성
  - References: [PR #56](https://github.com/Gamesung-Coding/a11y-market-web/pull/56), [Issue #6](https://github.com/Gamesung-Coding/a11y-market-web/issues/6), [요구 기능 명세서 #REQ-1](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)
- **장바구니 페이지** - 담당자: 장지훈
  - 장바구니 페이지 UI 레이아웃 구현
  - 판매자별 장바구니 카드 구조 추가
  - 선택/전체 삭제 및 결제 정보 박스 추가
  - 한계 금액 계산 로직 추가
  - References: [PR #57](https://github.com/Gamesung-Coding/a11y-market-web/pull/57), [Issue #23](https://github.com/Gamesung-Coding/a11y-market-web/issues/23), [Issue #24](https://github.com/Gamesung-Coding/a11y-market-web/issues/24), [Issue #25](https://github.com/Gamesung-Coding/a11y-market-web/issues/25), [Issue #26](https://github.com/Gamesung-Coding/a11y-market-web/issues/26), [요구 기능 명세서 #REQ-26  #REQ-32  #REQ-20](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)
- **메인 페이지 추가** - 담당자: 안규태
  - 메인 메이지 추가
  - References: [PR #59](https://github.com/Gamesung-Coding/a11y-market-web/pull/59), [Issue #4](https://github.com/Gamesung-Coding/a11y-market-web/issues/4)
- **회원 가입 페이지 추가** - 담당자: 김수민
  - 이메일을 통한 회원 가입 페이지 추가
  - References: [PR #60](https://github.com/Gamesung-Coding/a11y-market-web/pull/60), [Issue #10](https://github.com/Gamesung-Coding/a11y-market-web/issues/10), [요구 기능 명세서 #REQ-4](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)
- **배송지 관리 페이지 구현** - 담당자: 백여랑
  - 배송지 추가 및 관리 페이지 구현
  - 요소를 재사용가능한 컴포넌트로 구현
  - References: [PR #61](https://github.com/Gamesung-Coding/a11y-market-web/pull/61), [Issue #21](https://github.com/Gamesung-Coding/a11y-market-web/issues/21), [요구 기능 명세서 #REQ-17](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)
- **상품 목록 조회 및 필터링 UI 구현** - 담당자: 장지훈
  - 카테고리, 혜택, 판매자 등급, 가격에 따른 필터링 구현
  - 상품 그리드 레이아웃 구성
  - References: [PR #62](https://github.com/Gamesung-Coding/a11y-market-web/pull/62), [Issue #28](https://github.com/Gamesung-Coding/a11y-market-web/issues/28), [Issue #29](https://github.com/Gamesung-Coding/a11y-market-web/issues/29), [Issue #30](https://github.com/Gamesung-Coding/a11y-market-web/issues/30), [요구 기능 명세서 #REQ-33 #REQ-34 #REQ-35](https://ember-sting-f59.notion.site/29cde38d02db80fb8029df003f127638?v=29cde38d02db80e6a409000c9d00fe1a&source=copy_link)
- **관리자 페이지 - 대시보드** - 담당자: 백여랑
    - 내 상품 조회 엔드포인트 구현
    - JWT 인증 방식을 사용
    - References: [PR #64](https://github.com/Gamesung-Coding/a11y-market-web/pull/64), [Issue #46](https://github.com/Gamesung-Coding/a11y-market-web/issues/46)

### 1.2. 차주 프로젝트 수행 계획

- **Backend:**
    - 작성한 코드 및 리팩토링된 코드에 맞추어 테스트 코드 작성
    - 프론트엔드와의 연동 작업이 완료된 경우, 간편 로그인 구현
    - 판매자 및 주문 기능 작업을 유동적으로 분배하여 개발예정
- **Frontend:**
    - 백엔드 Swagger 기반 명세서를 기반으로 연동 시작
    - Figma에서 진행한 디자인을 기반으로 퍼블리싱
    - 진행 상황에 따라 팀장이 주도적으로 작업을 분배하여 개발 예정

---
## 2. 강사님 피드백
- 체계적으로 진행되고 있기 때문에 진척과 관련된 이슈는 없어보임
- 접근성이 프로젝트의 핵심 주제 이므로 해당 부분이 잘 표현되도록 기획에서 정의한 접근성 관련 부분을 숙지해서 개발에 반영 할 것
	- 기획단계에서 명확하게 정의 했으므로 기술적으로 리스크 없이 진행되도록 주의하면서 개발 진행하면 될 것 같음
