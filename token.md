# 토큰 생성 API

### 인증 토큰 생성

* API 사용을 위한 인증 토큰을 생성합니다.
* 발급받은 인증 토큰(accessToken)을 HTTP 헤더 영역(`Authorization: Bearer {accessToken}`)에 추가해야 API 사용이 가능합니다.
* **POST** /rcsapi/v1/token
* Content-Type: application/json; charset=utf-8

**Request**

|  **키** | **타입** | **필수** |    **설명**    |
| :----: | :----: | :----: | :----------: |
|  bizId | String |    O   | BIZPPURIO ID |
| apiKey | String |    O   |   API 발급 키   |

**Response**

|    **키**    |              |  **타입** |    **설명**   |
| :---------: | :----------: | :-----: | :---------: |
|     code    |              |  String |    결과 코드    |
|   message   |              |  String |     총 개수    |
|  totalCount |              | Integer |   총 페이지 수   |
| currentPage |              | Integer |    현재 페이지   |
|     data    |              |  Array  | 성공 시 템플릿 목록 |
|             |  accessToken |  String |    인증 토큰    |
|             |   expiresIn  |  String |    만료 시간    |
|             | refreshToken |  String |   리프레시 토큰   |



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

|   **키**  | **타입** | **필수** |                   **설명**                   |
| :------: | :----: | :----: | :----------------------------------------: |
|  brandId | String |    O   |           BizCenter에서 생성한 브랜드 ID           |
| brandKey | String |    O   | BizCenter 에서 기업 관리자가 발급하여 대행사에 전달한 브랜드 Key |

**Response**

|    **키**   | **타입** |                   **설명**                  |
| :--------: | :----: | :---------------------------------------: |
|    code    | String |                   결과 코드                   |
|   message  | String |                실패 시 결과 메시지                |
|    data    |        | <p>브랜드 상세 조회<br>(브랜드 연동 상세조회 반환 값 참조)</p> |
| pagination |        | <p>페이지 상세 조회<br>(브랜드 연동 상세조회 반환 값 참조)</p> |

