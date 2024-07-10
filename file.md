# 파일 관리

### 파일 등록&#x20;

* Maap 미디어 파일을 등록합니다.
* **POST** /rcsapi/v1/file/send
* Content-Type: multipart/form-data

**Request**

<table data-header-hidden><thead><tr><th width="150" align="center"></th><th width="150" align="center"></th><th width="150" align="center"></th><th width="284" align="center"></th></tr></thead><tbody><tr><td align="center"><strong>키</strong></td><td align="center"><strong>타입</strong></td><td align="center"><strong>필수</strong></td><td align="center"><strong>설명</strong></td></tr><tr><td align="center">file</td><td align="center">File</td><td align="center">O</td><td align="center">업로드 파일</td></tr><tr><td align="center">fileId</td><td align="center">String</td><td align="center">O</td><td align="center">파일 ID</td></tr><tr><td align="center">mimeType</td><td align="center">String</td><td align="center">O</td><td align="center">Mime type<br>(image/jpeg, image/png…)</td></tr><tr><td align="center">usageType</td><td align="center">String</td><td align="center">O</td><td align="center"><p>사용 타입</p><p>(chatbot, messagebase, send)</p></td></tr></tbody></table>

**Response**

<table data-header-hidden><thead><tr><th align="center"></th><th width="150" align="center"></th><th width="358" align="center"></th></tr></thead><tbody><tr><td align="center">Code</td><td align="center">String</td><td align="center">결과 코드</td></tr><tr><td align="center">Message</td><td align="center">String</td><td align="center">실패 시 결과 메시지</td></tr><tr><td align="center">data</td><td align="center"></td><td align="center">파일 상세 조회<br>(파일 상세조회 반환 값 참조)</td></tr><tr><td align="center">pagination</td><td align="center"></td><td align="center">페이지 상세 조회<br>(파일 상세조회 반환 값 참조)</td></tr></tbody></table>

### 파일 상세 조회

* Maap 미디어 파일을 조회합니다.
* **GET** /rcsapi/v1/file/info
* Query Parameter

**Request**



<table data-header-hidden><thead><tr><th width="150" align="center"></th><th width="150" align="center"></th><th width="150" align="center"></th><th width="273" align="center"></th></tr></thead><tbody><tr><td align="center"><strong>키</strong></td><td align="center"><strong>타입</strong></td><td align="center"><strong>필수</strong></td><td align="center"><strong>설명</strong></td></tr><tr><td align="center">comCode</td><td align="center">String</td><td align="center">O</td><td align="center">통신사 코드 (SKT, KT, LGU)</td></tr><tr><td align="center">fileId</td><td align="center">String</td><td align="center">O</td><td align="center">파일 ID</td></tr></tbody></table>

**Response**

<table data-header-hidden><thead><tr><th width="150" align="center"></th><th width="150" align="center"></th><th width="150" align="center"></th><th width="279" align="center"></th></tr></thead><tbody><tr><td align="center"><strong>키</strong></td><td align="center"><strong>-</strong></td><td align="center"><strong>타입</strong></td><td align="center"><strong>설명</strong></td></tr><tr><td align="center">code</td><td align="center"></td><td align="center">String</td><td align="center">결과 코드</td></tr><tr><td align="center">message</td><td align="center"></td><td align="center">String</td><td align="center">실패 시 결과 메시지</td></tr><tr><td align="center">data</td><td align="center"></td><td align="center">Array</td><td align="center">성공 시 데이터</td></tr><tr><td align="center"></td><td align="center">expiryDate</td><td align="center">String</td><td align="center">유효 기간</td></tr><tr><td align="center"></td><td align="center">fileId</td><td align="center">String</td><td align="center">파일 ID</td></tr><tr><td align="center"></td><td align="center">mimeType</td><td align="center">String</td><td align="center">Mime type<br>(image/jpeg, image/png)</td></tr><tr><td align="center"></td><td align="center">Status</td><td align="center">String</td><td align="center">파일 상태<br>(ready, expired)</td></tr><tr><td align="center"></td><td align="center">usageType</td><td align="center">String</td><td align="center">사용 타입<br>(chatbot, messagebase, send)</td></tr><tr><td align="center">pagination</td><td align="center"></td><td align="center"></td><td align="center"></td></tr><tr><td align="center"></td><td align="center">limit</td><td align="center">Integer</td><td align="center">조회 최대 건수<br>(기본:100, 최대:1000)</td></tr><tr><td align="center"></td><td align="center">offset</td><td align="center">Integer</td><td align="center">시작 offset 번호<br>(기본:0)</td></tr><tr><td align="center"></td><td align="center">total</td><td align="center">Integer</td><td align="center">총 개수</td></tr></tbody></table>



### RCS MMS 이미지 규격&#x20;

![](<.gitbook/assets/image (5).png>)
