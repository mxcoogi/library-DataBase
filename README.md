<!DOCTYPE html>
<html>
<head>
<title>데이터베이스프로그래밍 01</title>
<meta http-equiv="Content-type" content="text/html;charset=UTF-8">

<style>
/* https://github.com/microsoft/vscode/blob/master/extensions/markdown-language-features/media/markdown.css */
/*---------------------------------------------------------------------------------------------
 *  Copyright (c) Microsoft Corporation. All rights reserved.
 *  Licensed under the MIT License. See License.txt in the project root for license information.
 *--------------------------------------------------------------------------------------------*/

body {
	font-family: var(--vscode-markdown-font-family, -apple-system, BlinkMacSystemFont, "Segoe WPC", "Segoe UI", "Ubuntu", "Droid Sans", sans-serif);
	font-size: var(--vscode-markdown-font-size, 14px);
	padding: 0 26px;
	line-height: var(--vscode-markdown-line-height, 22px);
	word-wrap: break-word;
}

#code-csp-warning {
	position: fixed;
	top: 0;
	right: 0;
	color: white;
	margin: 16px;
	text-align: center;
	font-size: 12px;
	font-family: sans-serif;
	background-color:#444444;
	cursor: pointer;
	padding: 6px;
	box-shadow: 1px 1px 1px rgba(0,0,0,.25);
}

#code-csp-warning:hover {
	text-decoration: none;
	background-color:#007acc;
	box-shadow: 2px 2px 2px rgba(0,0,0,.25);
}

body.scrollBeyondLastLine {
	margin-bottom: calc(100vh - 22px);
}

body.showEditorSelection .code-line {
	position: relative;
}

body.showEditorSelection .code-active-line:before,
body.showEditorSelection .code-line:hover:before {
	content: "";
	display: block;
	position: absolute;
	top: 0;
	left: -12px;
	height: 100%;
}

body.showEditorSelection li.code-active-line:before,
body.showEditorSelection li.code-line:hover:before {
	left: -30px;
}

.vscode-light.showEditorSelection .code-active-line:before {
	border-left: 3px solid rgba(0, 0, 0, 0.15);
}

.vscode-light.showEditorSelection .code-line:hover:before {
	border-left: 3px solid rgba(0, 0, 0, 0.40);
}

.vscode-light.showEditorSelection .code-line .code-line:hover:before {
	border-left: none;
}

.vscode-dark.showEditorSelection .code-active-line:before {
	border-left: 3px solid rgba(255, 255, 255, 0.4);
}

.vscode-dark.showEditorSelection .code-line:hover:before {
	border-left: 3px solid rgba(255, 255, 255, 0.60);
}

.vscode-dark.showEditorSelection .code-line .code-line:hover:before {
	border-left: none;
}

.vscode-high-contrast.showEditorSelection .code-active-line:before {
	border-left: 3px solid rgba(255, 160, 0, 0.7);
}

.vscode-high-contrast.showEditorSelection .code-line:hover:before {
	border-left: 3px solid rgba(255, 160, 0, 1);
}

.vscode-high-contrast.showEditorSelection .code-line .code-line:hover:before {
	border-left: none;
}

img {
	max-width: 100%;
	max-height: 100%;
}

a {
	text-decoration: none;
}

a:hover {
	text-decoration: underline;
}

a:focus,
input:focus,
select:focus,
textarea:focus {
	outline: 1px solid -webkit-focus-ring-color;
	outline-offset: -1px;
}

hr {
	border: 0;
	height: 2px;
	border-bottom: 2px solid;
}

h1 {
	padding-bottom: 0.3em;
	line-height: 1.2;
	border-bottom-width: 1px;
	border-bottom-style: solid;
}

h1, h2, h3 {
	font-weight: normal;
}

table {
	border-collapse: collapse;
}

table > thead > tr > th {
	text-align: left;
	border-bottom: 1px solid;
}

table > thead > tr > th,
table > thead > tr > td,
table > tbody > tr > th,
table > tbody > tr > td {
	padding: 5px 10px;
}

table > tbody > tr + tr > td {
	border-top: 1px solid;
}

blockquote {
	margin: 0 7px 0 5px;
	padding: 0 16px 0 10px;
	border-left-width: 5px;
	border-left-style: solid;
}

code {
	font-family: Menlo, Monaco, Consolas, "Droid Sans Mono", "Courier New", monospace, "Droid Sans Fallback";
	font-size: 1em;
	line-height: 1.357em;
}

body.wordWrap pre {
	white-space: pre-wrap;
}

pre:not(.hljs),
pre.hljs code > div {
	padding: 16px;
	border-radius: 3px;
	overflow: auto;
}

pre code {
	color: var(--vscode-editor-foreground);
	tab-size: 4;
}

/** Theming */

.vscode-light pre {
	background-color: rgba(220, 220, 220, 0.4);
}

.vscode-dark pre {
	background-color: rgba(10, 10, 10, 0.4);
}

.vscode-high-contrast pre {
	background-color: rgb(0, 0, 0);
}

.vscode-high-contrast h1 {
	border-color: rgb(0, 0, 0);
}

.vscode-light table > thead > tr > th {
	border-color: rgba(0, 0, 0, 0.69);
}

.vscode-dark table > thead > tr > th {
	border-color: rgba(255, 255, 255, 0.69);
}

.vscode-light h1,
.vscode-light hr,
.vscode-light table > tbody > tr + tr > td {
	border-color: rgba(0, 0, 0, 0.18);
}

.vscode-dark h1,
.vscode-dark hr,
.vscode-dark table > tbody > tr + tr > td {
	border-color: rgba(255, 255, 255, 0.18);
}

</style>

<style>
/* Tomorrow Theme */
/* http://jmblog.github.com/color-themes-for-google-code-highlightjs */
/* Original theme - https://github.com/chriskempson/tomorrow-theme */

/* Tomorrow Comment */
.hljs-comment,
.hljs-quote {
	color: #8e908c;
}

/* Tomorrow Red */
.hljs-variable,
.hljs-template-variable,
.hljs-tag,
.hljs-name,
.hljs-selector-id,
.hljs-selector-class,
.hljs-regexp,
.hljs-deletion {
	color: #c82829;
}

/* Tomorrow Orange */
.hljs-number,
.hljs-built_in,
.hljs-builtin-name,
.hljs-literal,
.hljs-type,
.hljs-params,
.hljs-meta,
.hljs-link {
	color: #f5871f;
}

/* Tomorrow Yellow */
.hljs-attribute {
	color: #eab700;
}

/* Tomorrow Green */
.hljs-string,
.hljs-symbol,
.hljs-bullet,
.hljs-addition {
	color: #718c00;
}

/* Tomorrow Blue */
.hljs-title,
.hljs-section {
	color: #4271ae;
}

/* Tomorrow Purple */
.hljs-keyword,
.hljs-selector-tag {
	color: #8959a8;
}

.hljs {
	display: block;
	overflow-x: auto;
	color: #4d4d4c;
	padding: 0.5em;
}

.hljs-emphasis {
	font-style: italic;
}

.hljs-strong {
	font-weight: bold;
}
</style>

<style>
/*
 * Markdown PDF CSS
 */

 body {
	font-family: -apple-system, BlinkMacSystemFont, "Segoe WPC", "Segoe UI", "Ubuntu", "Droid Sans", sans-serif, "Meiryo";
	padding: 0 12px;
}

pre {
	background-color: #f8f8f8;
	border: 1px solid #cccccc;
	border-radius: 3px;
	overflow-x: auto;
	white-space: pre-wrap;
	overflow-wrap: break-word;
}

pre:not(.hljs) {
	padding: 23px;
	line-height: 19px;
}

blockquote {
	background: rgba(127, 127, 127, 0.1);
	border-color: rgba(0, 122, 204, 0.5);
}

.emoji {
	height: 1.4em;
}

code {
	font-size: 14px;
	line-height: 19px;
}

/* for inline code */
:not(pre):not(.hljs) > code {
	color: #C9AE75; /* Change the old color so it seems less like an error */
	font-size: inherit;
}

/* Page Break : use <div class="page"/> to insert page break
-------------------------------------------------------- */
.page {
	page-break-after: always;
}

</style>

<script src="https://unpkg.com/mermaid/dist/mermaid.min.js"></script>
</head>
<body>
  <script>
    mermaid.initialize({
      startOnLoad: true,
      theme: document.body.classList.contains('vscode-dark') || document.body.classList.contains('vscode-high-contrast')
          ? 'dark'
          : 'default'
    });
  </script>
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
