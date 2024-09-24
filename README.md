<!DOCTYPE html>
<html>
<body>
<hr>
<h2 id="%EB%8D%B0%EC%9D%B4%ED%84%B0%EB%B2%A0%EC%9D%B4%EC%8A%A4%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D-%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8-01">데이터베이스프로그래밍 프로젝트 01</h2>
<p>팀플 : 도서관리시스템 DB 프로젝트</p>
<p>팀명 : 정미</p>
<p>팀원 : 김국민 , 이윤석</p>
<p>도서관리시스템 DB 프로젝트 계획서</p>
<h4 id="1-%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8-%EA%B0%9C%EC%9A%94">1. 프로젝트 개요</h4>
<ul>
<li><strong>프로젝트명</strong>: 도서관리시스템</li>
<li><strong>목표</strong>: 도서 대출, 반납, 등록 및 관리 기능을 제공하여 도서관 운영의 효율성을 높인다.</li>
<li><strong>주요 기능</strong>:
<ul>
<li>도서 등록 및 삭제</li>
<li>도서 대출 및 반납 관리</li>
<li>사용자 관리</li>
<li>도서 검색 및 필터링</li>
<li>대출 내역 조회</li>
</ul>
</li>
</ul>
<h4 id="2-%EC%9A%94%EA%B5%AC-%EC%82%AC%ED%95%AD-%EB%B6%84%EC%84%9D">2. 요구 사항 분석</h4>
<ul>
<li><strong>기능 요구 사항</strong>:
<ul>
<li>관리자 계정으로 도서 등록 및 삭제 가능</li>
<li>사용자 계정으로 대출 및 반납 요청</li>
<li>도서 제목, 저자, ISBN으로 검색 가능</li>
<li>대출 가능 여부 확인 기능</li>
</ul>
</li>
<li><strong>비기능 요구 사항</strong>:
<ul>
<li>데이터의 무결성 유지</li>
<li>사용자 인터페이스의 직관성</li>
<li>시스템의 안정성 및 성능</li>
</ul>
</li>
</ul>
<h4 id="3-%EC%8B%9C%EC%8A%A4%ED%85%9C-%EC%84%A4%EA%B3%84">3. 시스템 설계</h4>
<ul>
<li><strong>DB 설계</strong>:
<ul>
<li><strong>도서 테이블</strong>: 도서 ID, 제목, 저자, ISBN, 출판사, 장르, 대출 가능 여부</li>
<li><strong>사용자 테이블</strong>: 사용자 ID, 이름, 연락처, 이메일, 대출한 도서 ID</li>
<li><strong>대출 기록 테이블</strong>: 대출 ID, 사용자 ID, 도서 ID, 대출 날짜, 반납 날짜</li>
</ul>
</li>
</ul>
<h4 id="4-%EA%B8%B0%EC%88%A0-%EC%8A%A4%ED%83%9D">4. 기술 스택</h4>
<ul>
<li><strong>프로그래밍 언어</strong>: Python, JavaScript</li>
<li><strong>프레임워크</strong>:Flask(백엔드), React</li>
<li><strong>DBMS</strong>: MySQL</li>
<li><strong>기타 도구</strong>: Git, Docker</li>
</ul>
<h4 id="5-%ED%94%84%EB%A1%9C%EC%A0%9D%ED%8A%B8-%EC%9D%BC%EC%A0%95">5. 프로젝트 일정</h4>
<table>
<thead>
<tr>
<th>단계</th>
<th>기간</th>
<th>주요 작업</th>
</tr>
</thead>
<tbody>
<tr>
<td>요구 사항 분석</td>
<td>1주</td>
<td>기능 및 비기능 요구 사항 정의</td>
</tr>
<tr>
<td>DB 설계</td>
<td>1주</td>
<td>테이블 및 관계 설계, ERD 작성</td>
</tr>
<tr>
<td>프론트엔드 개발</td>
<td>2주</td>
<td>사용자 인터페이스 개발</td>
</tr>
<tr>
<td>백엔드 개발</td>
<td>2주</td>
<td>API 및 데이터 처리 로직 구현</td>
</tr>
<tr>
<td>통합 테스트</td>
<td>1주</td>
<td>기능 통합 및 버그 수정</td>
</tr>
<tr>
<td>배포</td>
<td>1주</td>
<td>서버에 배포 및 최종 검토</td>
</tr>
</tbody>
</table>
<h4 id="6-%EA%B8%B0%EB%8C%80-%ED%9A%A8%EA%B3%BC">6. 기대 효과</h4>
<ul>
<li>도서 대출 및 반납 프로세스의 간소화</li>
<li>도서관 자원의 효율적인 관리</li>
<li>사용자 친화적인 인터페이스 제공으로 이용자 만족도 향상</li>
</ul>

</body>
</html>
