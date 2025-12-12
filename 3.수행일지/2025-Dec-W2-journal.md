# [12월 2주차 프로젝트 수행 일지]

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

- 금주에는 리팩토링을 중점적으로 수행하였음.

#### 백엔드

- **카테고리 필터링 및 잘못된 응답 객체 수정** - 담당자: 안규태

  - 상품이 매우 많을 경우를 대비하여 1차적인 필터링을 서버에서 수행
  - 메인 화면에서 올바르지 않은 상품이 검색되는 문제 해결
  - 균일하지 않은 API 응답 객체 수정
  - References: PR [&#35;119](https://github.com/Gamesung-Coding/a11y-market-server/pull/119), Issues [&#35;116](https://github.com/Gamesung-Coding/a11y-market-server/issues/116) [&#35;117](https://github.com/Gamesung-Coding/a11y-market-server/issues/117) [&#35;118](https://github.com/Gamesung-Coding/a11y-market-server/issues/118)

- **상품 관리 API 향상** - 담당자: 안규태

  - 논리적으로 필요한 상품 상태 추가
  - 상품 수정 시에도 이미지를 받도록 수정
  - 이미지 변경 시, 삭제된 이미지를 S3에서 제거하도록 수정
  - References: PR [&#35;120](https://github.com/Gamesung-Coding/a11y-market-server/pull/120)

- **관리자의 상품 승인 기능의 DTO 구조 확장** - 담당자: 신운용

  - 상품 신청을 위한 필드 추가
  - 응답 필드 구성 정리 및 데이터 구조 보강
  - References: PR [&#35;121](https://github.com/Gamesung-Coding/a11y-market-server/pull/121)

- **관리자 대시보드 API 엔드포인트 추가** - 담당자: 안규태

  - 관리자 대시보드를 위한 API 엔드 포인트 추가
  - References: PR [&#35;122](https://github.com/Gamesung-Coding/a11y-market-server/pull/122)

- **카카오 로그인이 불가능한 버그 수정** - 담당자: 안규태

  - 카카오 계정 사용자의 비밀번호가 없는 경우 예외 처리 추가
  - References: PR [&#35;124](https://github.com/Gamesung-Coding/a11y-market-server/pull/124), Issues [&#35;123](https://github.com/Gamesung-Coding/a11y-market-server/issues/123)

- **기본 배송지 해제 로직 추가** - 담당자: 백여랑

  - References: PR [&#35;126](https://github.com/Gamesung-Coding/a11y-market-server/pull/126), Issues [&#35;125](https://github.com/Gamesung-Coding/a11y-market-server/issues/125)

- **Toss Payments 기능 추가** - 담당자: 안규태

  - 토스 페이먼츠를 사용하여 데모 결제 기능 연동
  - References: PR [&#35;127](https://github.com/Gamesung-Coding/a11y-market-server/pull/127)

#### 프론트엔드

- **메인 페이지 레이아웃 변경** - 담당자: 안규태

  - 임시로 구현한 메인 페이지의 레이아웃을 개편
  - 전체적인 코드 스타일 및 디자인 변경
  - API 연동 및 함수 구성
  - References: PR [&#35;100](https://github.com/Gamesung-Coding/a11y-market-web/pull/100)

- **마이페이지 API 연동** - 담당자: 안규태

  - 미연동 된 마이페이지 API 연동
  - References: PR [&#35;101](https://github.com/Gamesung-Coding/a11y-market-web/pull/101)

- **동적 카테고리 데이터** - 담당자: 안규태

  - 하드코딩된 카테고리 테이터를 서버에서 받아오도록 변경
  - References: PR [&#35;115](https://github.com/Gamesung-Coding/a11y-market-web/pull/115), Issues [&#35;112](https://github.com/Gamesung-Coding/a11y-market-web/issues/112) [&#35;113](https://github.com/Gamesung-Coding/a11y-market-web/issues/113) [&#35;114](https://github.com/Gamesung-Coding/a11y-market-web/issues/114)

- **마이페이지의 접근성 설정 페이지 리스타일** - 담당자: 김수민

  - References: PR [&#35;116](https://github.com/Gamesung-Coding/a11y-market-web/pull/116), Issues [&#35;102](https://github.com/Gamesung-Coding/a11y-market-web/issues/102)

- **관리자의 회원관리 페이지 미연동 API 연동 및 구조 개선** - 담당자: 장지훈

  - 관리자 - 회원 관리 페이지의 구조를 일관성 있게 변경
  - 권한 변경 등 API 로직 연동
  - References: PR [&#35;117](https://github.com/Gamesung-Coding/a11y-market-web/pull/117), Issues [&#35;106](https://github.com/Gamesung-Coding/a11y-market-web/issues/106)

- **상품 관리 페이지 API 기능 연동** - 담당자: 안규태

  - 상품 관리 페이지의 연동되지 않은 API 연동
  - 보고된 버그 해결
  - 잘못된 페이지 구조 수정
  - References: PR [&#35;118](https://github.com/Gamesung-Coding/a11y-market-web/pull/118), Issues [&#35;104](https://github.com/Gamesung-Coding/a11y-market-web/issues/104)

- **관리자 상품 승인 관리 페이지 API 연동** - 담당자: 신운용

  - 관리자 상품 승인 관리 페이지 API 연동
  - References: PR [&#35;119](https://github.com/Gamesung-Coding/a11y-market-web/pull/119), Issues [&#35;108](https://github.com/Gamesung-Coding/a11y-market-web/issues/108)

- **관리자 대시보드 추가** - 담당자: 안규태

  - 관리자 대시보드 추가 및 API 연동
  - References: PR [&#35;121](https://github.com/Gamesung-Coding/a11y-market-web/pull/121), Issues [&#35;105](https://github.com/Gamesung-Coding/a11y-market-web/issues/105),

- **색반전 접근성 설정 버그 및 보일러 코드 제거** - 담당자: 김수민

  - 접근성 설정 중 색반전이 적용되지 않는 문제 해결
  - References: PR [&#35;122](https://github.com/Gamesung-Coding/a11y-market-web/pull/122), Issues [&#35;120](https://github.com/Gamesung-Coding/a11y-market-web/issues/120)

- **배송지 관리 페이지 리팩토링** - 담당자: 백여랑

  - 배송지 관리 페이지의 스타일을 일관성 있게 수정
  - 연결되지 않거나 잘못된 API 연동 수정
  - References: PR [&#35;124](https://github.com/Gamesung-Coding/a11y-market-web/pull/124), Issues [&#35;103](https://github.com/Gamesung-Coding/a11y-market-web/issues/103)

- **장바구니 페이지 UI 개선** - 담당자: 김수민

  - 다크 모드가 적용되지 않던 문제 해결
  - 사움 이미지 클릭 시 상품 페이지로 이동 하도록 수정
  - 수량 및 선택 상품 변경 시 총 상품 금액에 반영되지 않던 문제 해경
  - 장바구니 상품 삭제 시 알림 추가
  - 상품 이미지 비율 개선
  - 수량이 음수로 내려가는 문제 해결
  - References: PR [&#35;125](https://github.com/Gamesung-Coding/a11y-market-web/pull/125), Issues [&#35;123](https://github.com/Gamesung-Coding/a11y-market-web/issues/123)

- **관리자의 판매자 관리 페이지 재구성** - 담당자: 안규태

  - 판매자 관리및 연관 기능 재구성
  - 연동되지 않은 API 연동
  - 일관성 있는 UI 스타일로 변경
  - 판매자 계정 신청 승인 페이지와 관리 페이지를 분리하여 추가
  - 접근성 인증 마크 부여 기능 병합
  - References: PR [&#35;126](https://github.com/Gamesung-Coding/a11y-market-web/pull/126), Issues [&#35;107](https://github.com/Gamesung-Coding/a11y-market-web/issues/107) [&#35;110](https://github.com/Gamesung-Coding/a11y-market-web/issues/110)

- **관리자의 주문 관리 페이지 API 연동** - 담당자: 신운용

  - 관리자의 시스템 전체 주문 관리 페이지를 API에 연동
  - References: PR [&#35;132](https://github.com/Gamesung-Coding/a11y-market-web/pull/132), Issues [&#35;109](https://github.com/Gamesung-Coding/a11y-market-web/issues/109)

- **필요하지 않은 페이지 삭제 및 페이지 구조 최적화** - 담당자: 안규태

  - 필요하지 않은 페이지 삭제
  - 몇몇 페이지를 컴포넌트로 전환하여 확장성 대폭 강화
  - References: PR [&#35;133](https://github.com/Gamesung-Coding/a11y-market-web/pull/133)

- **PG사 결제 연동** - 담당자: 안규태

  - Toss payments를 이용하여 결제 기능을 구현
  - 변경된 API 엔드포인트에 맞춰 연결점 변경
  - 토스 페이먼츠를 사용하여 결제 과정을 구현
  - 토스 페이먼츠의 위젝을 결제 화면에 포함하도록 구성
  - 배경색 문제로 다크모드가 적용되지 않는 문제 해결
  - 주문 취소, 부분 취소 문제를 해결
  - References: PR [&#35;136](https://github.com/Gamesung-Coding/a11y-market-web/pull/136)

#### 배포 전 QA 진행 중

- **`release/v1.0.0` 브랜치에 배포하여 QA 진행 중** - 담당자: 안규태, 김수민, 백여랑, 신운용, 장지훈

  - 전체 버그 및 누락된 기능을 확인하여 이슈 등록 및 해결
  - References: Issues [&#35;137](https://github.com/Gamesung-Coding/a11y-market-web/issues/137) [&#35;138](https://github.com/Gamesung-Coding/a11y-market-web/issues/138) [&#35;139](https://github.com/Gamesung-Coding/a11y-market-web/issues/139) [&#35;140](https://github.com/Gamesung-Coding/a11y-market-web/issues/140) [&#35;141](https://github.com/Gamesung-Coding/a11y-market-web/issues/141) [&#35;142](https://github.com/Gamesung-Coding/a11y-market-web/issues/142) [&#35;143](https://github.com/Gamesung-Coding/a11y-market-web/issues/143) [&#35;144](https://github.com/Gamesung-Coding/a11y-market-web/issues/144) [&#35;145](https://github.com/Gamesung-Coding/a11y-market-web/issues/145) [&#35;146](https://github.com/Gamesung-Coding/a11y-market-web/issues/146) [&#35;147](https://github.com/Gamesung-Coding/a11y-market-web/issues/147) [&#35;148](https://github.com/Gamesung-Coding/a11y-market-web/issues/148) [&#35;149](https://github.com/Gamesung-Coding/a11y-market-web/issues/149) [&#35;150](https://github.com/Gamesung-Coding/a11y-market-web/issues/150) [&#35;151](https://github.com/Gamesung-Coding/a11y-market-web/issues/151) [&#35;152](https://github.com/Gamesung-Coding/a11y-market-web/issues/152) [&#35;153](https://github.com/Gamesung-Coding/a11y-market-web/issues/153) [&#35;154](https://github.com/Gamesung-Coding/a11y-market-web/issues/154)
  - 현재 이슈 해결율: 83.3%

### 1.2. 차주 프로젝트 수행 계획

- 남은 QA 진행 후 master 브랜치 배포
- CI/CD 파이프라인 정리
- PPT, 포트폴리오 작성

---

## 2. 강사님 피드백

내용
