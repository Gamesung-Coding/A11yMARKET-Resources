# [11월 2주차 프로젝트 수행 일지]
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
	- 작주 수행한 PR 코드 리뷰 및 코멘트
- **테이블 스키마 수정 및 SQL 작성** - 담당자: 안규태, 김수민
	- 테이블 스키마 SQL 작성 및 더미데이터 작성 완료
	- 잘못된 스키마(ERD) 수정
	- 뷰테이블(`seller_sales`) 작성
	- References: [PR #7](https://github.com/Gamesung-Coding/a11y-market-server/pull/7), [Commit(develop) 56e5c5e](https://github.com/Gamesung-Coding/a11y-market-server/commit/56e5c5e23561fc0af72cf0c22177c57b217a8432)
- **로그인/로그아웃 API 작성** - 담당자: 김수민
	- ApiDog를 활용하여 테스트 완료
	- References: [PR #6](https://github.com/Gamesung-Coding/a11y-market-server/pull/6)
- **상품 목록 조회 및 조건/키워드 검색 API 작성** - 담당자: 신운용
	- Seller 기능이 구현되지 않아 향후 리팩토링을 통해 기능 완성 예정
	- References: [PR #65](https://github.com/Gamesung-Coding/a11y-market-server/pull/65)
- **Frontend 디자인** - 담당자: 김수민, 백여랑, 신운용, 장지훈
	- 디자인 시안 완성
	- References: [별첨:5.기타자료 - Figma UI/UX Design](../5.기타자료)
- **Frontend 개발 환경 검토** - 담당자: 안규태
	- Vitest UI 및 test 커맨드 추가, 동작 테스트 완료
	- 프레임워크 동작 테스트 완료
	- GitHub Actions를 통한 CI/CD 환경 구축 완료

### 1.2. 차주 프로젝트 수행 계획
- 작성 중

---
## 2. 강사님 피드백
내용