# 토큰 생성 API

### 인증 토큰 생성

* API 사용을 위한 인증 토큰을 생성합니다.
* 발급받은 인증 토큰(accessToken)을 HTTP 헤더 영역(`Authorization: Bearer {accessToken}`)에 추가해야 API 사용이 가능합니다.
* **POST** /rcsapi/v1/token
* Content-Type: application/json; charset=utf-8

**Request**

<table data-header-hidden><thead><tr><th width="177" align="center"></th><th width="150" align="center"></th><th width="150" align="center"></th><th width="242" align="center"></th></tr></thead><tbody><tr><td align="center"><strong>키</strong></td><td align="center"><strong>타입</strong></td><td align="center"><strong>필수</strong></td><td align="center"><strong>설명</strong></td></tr><tr><td align="center">bizId</td><td align="center">String</td><td align="center">O</td><td align="center">BIZPPURIO ID</td></tr><tr><td align="center">apiKey</td><td align="center">String</td><td align="center">O</td><td align="center">API 발급 키</td></tr></tbody></table>

**Response**

<table data-header-hidden><thead><tr><th width="150" align="center"></th><th width="150" align="center"></th><th width="150" align="center"></th><th width="208" align="center"></th></tr></thead><tbody><tr><td align="center"><strong>키</strong></td><td align="center"></td><td align="center"><strong>타입</strong></td><td align="center"><strong>설명</strong></td></tr><tr><td align="center">code</td><td align="center"></td><td align="center">String</td><td align="center">결과 코드</td></tr><tr><td align="center">message</td><td align="center"></td><td align="center">String</td><td align="center">총 개수</td></tr><tr><td align="center">totalCount</td><td align="center"></td><td align="center">Integer</td><td align="center">총 페이지 수</td></tr><tr><td align="center">currentPage</td><td align="center"></td><td align="center">Integer</td><td align="center">현재 페이지</td></tr><tr><td align="center">data</td><td align="center"></td><td align="center">Array</td><td align="center">성공 시 템플릿 목록</td></tr><tr><td align="center"></td><td align="center">accessToken</td><td align="center">String</td><td align="center">인증 토큰</td></tr><tr><td align="center"></td><td align="center">expiresIn</td><td align="center">String</td><td align="center">만료 시간</td></tr><tr><td align="center"></td><td align="center">refreshToken</td><td align="center">String</td><td align="center">리프레시 토큰 </td></tr></tbody></table>



**ex)**

**Request**

인증 토큰 생성 : [https://rapi.bizppurio.com/rcsapi/v1/token](https://rapi.bizppurio.com/rcsapi/v1/token)

```json5
{
  "bizId": "[비즈뿌리오 사용자 ID]",
  "apiKey": "[발급 받은 API Key]"
}
```

**Response**

인증 토큰 정보

```json5
{
  "code": 200,
  "data": {
  "accessToken": "[인증 토큰]", 
  "expiresIn": [만료시간 ex:1568694883], 
  "refreshToken": "[리프레시 토큰]"
  }
}
```

### 인증 토큰 재 생성

* API 사용을 위한 인증 토큰을 재 생성합니다.
* **POST** /rcsapi/v1/refresh\_token
* Content-Type: application/json; charset=utf-8\


**Request**

<table data-header-hidden><thead><tr><th width="177" align="center"></th><th width="150" align="center"></th><th width="150" align="center"></th><th width="405" align="center"></th></tr></thead><tbody><tr><td align="center"><strong>키</strong></td><td align="center"><strong>타입</strong></td><td align="center"><strong>필수</strong></td><td align="center"><strong>설명</strong></td></tr><tr><td align="center">brandId</td><td align="center">String</td><td align="center">O</td><td align="center">BizCenter에서 생성한 브랜드 ID</td></tr><tr><td align="center">brandKey</td><td align="center">String</td><td align="center">O</td><td align="center">BizCenter 에서 기업 관리자가 발급하여 대행사에 전달한 브랜드 Key</td></tr></tbody></table>

**Response**

<table data-header-hidden><thead><tr><th align="center">Text</th><th width="167.33333333333331" align="center"></th><th align="center"></th></tr></thead><tbody><tr><td align="center"><strong>키</strong></td><td align="center"><strong>타입</strong></td><td align="center"><strong>설명</strong></td></tr><tr><td align="center">code</td><td align="center">String</td><td align="center">결과 코드</td></tr><tr><td align="center">message</td><td align="center">String</td><td align="center">실패 시 결과 메시지</td></tr><tr><td align="center">data</td><td align="center"></td><td align="center">브랜드 상세 조회<br>(브랜드 연동 상세조회 반환 값 참조)</td></tr><tr><td align="center">pagination</td><td align="center"></td><td align="center">페이지 상세 조회<br>(브랜드 연동 상세조회 반환 값 참조)</td></tr></tbody></table>

