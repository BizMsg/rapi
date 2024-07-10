# 브랜드 관리

### 브랜드 연동

* 해당 파트너에 브랜드를 연동합니다.
* **POST** /rcsapi/v1/brand/link
* Content-Type: application/json; charset=utf-8



**Request**

<table data-header-hidden><thead><tr><th width="177" align="center">Text</th><th width="150" align="center"></th><th width="150" align="center">필수</th><th width="424" align="center"></th></tr></thead><tbody><tr><td align="center"><strong>키</strong></td><td align="center"><strong>타입</strong></td><td align="center"><strong>필수</strong></td><td align="center"><strong>설명</strong></td></tr><tr><td align="center">brandId</td><td align="center">String</td><td align="center">O</td><td align="center">BizCenter에서 생성한 브랜드 ID</td></tr><tr><td align="center">brandKey</td><td align="center">String</td><td align="center">O</td><td align="center">BizCenter에서 기업 관리자가 발급하여 대행사에 전달한<br>브랜드 Key</td></tr></tbody></table>

**Response**

<table data-header-hidden><thead><tr><th align="center">Text</th><th width="167.33333333333331" align="center"></th><th align="center"></th></tr></thead><tbody><tr><td align="center"><strong>키</strong></td><td align="center"><strong>타입</strong></td><td align="center"><strong>설명</strong></td></tr><tr><td align="center">code</td><td align="center">String</td><td align="center">결과 코드</td></tr><tr><td align="center">message</td><td align="center">String</td><td align="center">실패 시 결과 메시지</td></tr><tr><td align="center">data</td><td align="center"></td><td align="center">브랜드 상세 조회<br>(브랜드 연동 상세조회 반환 값 참조)</td></tr><tr><td align="center">pagination</td><td align="center"></td><td align="center">페이지 상세 조회<br>(브랜드 연동 상세조회 반환 값 참조)</td></tr></tbody></table>

### 브랜드 연동 상세 조회

* 해당 파트너와 연동된 브랜드를 조회합니다.
* **GET** /rcsapi/v1/brand
* Query Parameter



**Request**

<table data-header-hidden><thead><tr><th width="177" align="center">Text</th><th width="150" align="center"></th><th width="150" align="center">필수</th><th width="424" align="center"></th></tr></thead><tbody><tr><td align="center"><strong>키</strong></td><td align="center"><strong>타입</strong></td><td align="center"><strong>필수</strong></td><td align="center"><strong>설명</strong></td></tr><tr><td align="center">brandId</td><td align="center">String</td><td align="center">O</td><td align="center">BizCenter에서 생성한 브랜드 ID</td></tr></tbody></table>



**Response**

<table data-header-hidden><thead><tr><th width="150" align="center"></th><th align="center"></th><th width="150" align="center"></th><th width="372" align="center"></th></tr></thead><tbody><tr><td align="center"><strong>키</strong></td><td align="center"></td><td align="center"><strong>타입</strong></td><td align="center"><strong>설명</strong></td></tr><tr><td align="center">code</td><td align="center"></td><td align="center">String</td><td align="center">결과 코드</td></tr><tr><td align="center">message</td><td align="center"></td><td align="center">String</td><td align="center">실패 시 결과 메시지</td></tr><tr><td align="center">data</td><td align="center"></td><td align="center">Array</td><td align="center">성공 시 데이터</td></tr><tr><td align="center"></td><td align="center">brandId</td><td align="center">String</td><td align="center">BizCenter에서 생성한 브랜드 ID</td></tr><tr><td align="center"></td><td align="center">brandKey</td><td align="center">String</td><td align="center">BizCenter에서 기업 관리자가 발급하여 대행사에 전달한 브랜드 Key</td></tr><tr><td align="center"></td><td align="center">chatbotDate</td><td align="center">String</td><td align="center">챗봇 최종 수정일시</td></tr><tr><td align="center"></td><td align="center">linkDate</td><td align="center">String</td><td align="center">파트너 연동일시</td></tr><tr><td align="center"></td><td align="center">messagebaseDate</td><td align="center">String</td><td align="center">템플릿 최종 수정일시</td></tr><tr><td align="center"></td><td align="center">name</td><td align="center">String</td><td align="center">브랜드 명</td></tr><tr><td align="center"></td><td align="center">partnerId</td><td align="center">String</td><td align="center">파트너 아이디</td></tr><tr><td align="center"></td><td align="center">registerDate</td><td align="center">String</td><td align="center">브랜드 등록일시</td></tr><tr><td align="center"></td><td align="center">status</td><td align="center">String</td><td align="center">브랜드 상태</td></tr><tr><td align="center"></td><td align="center">updateDate</td><td align="center">String</td><td align="center">브랜드 최종 수정일시</td></tr><tr><td align="center">pagination</td><td align="center"></td><td align="center"></td><td align="center"></td></tr><tr><td align="center"></td><td align="center">limit</td><td align="center">Integer</td><td align="center">조회 최대 건수 (기본:100, 최대:1000)</td></tr><tr><td align="center"></td><td align="center">offset</td><td align="center">Integer</td><td align="center">시작 offset 번호 (기본:0)</td></tr><tr><td align="center"></td><td align="center">total</td><td align="center">Integer</td><td align="center">총 개수</td></tr></tbody></table>

