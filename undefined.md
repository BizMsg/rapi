# 브랜드 관리

### 브랜드 연동

* 해당 파트너에 브랜드를 연동합니다.
* **POST** /rcsapi/v1/brand/link
* Content-Type: application/json; charset=utf-8



**Request**

|   **키**  | **타입** | **필수** |                        **설명**                       |
| :------: | :----: | :----: | :-------------------------------------------------: |
|  brandId | String |    O   |                BizCenter에서 생성한 브랜드 ID               |
| brandKey | String |    O   | <p>BizCenter에서 기업 관리자가 발급하여 대행사에 전달한<br>브랜드 Key</p> |

**Response**

|    **키**   | **타입** |                   **설명**                  |
| :--------: | :----: | :---------------------------------------: |
|    code    | String |                   결과 코드                   |
|   message  | String |                실패 시 결과 메시지                |
|    data    |        | <p>브랜드 상세 조회<br>(브랜드 연동 상세조회 반환 값 참조)</p> |
| pagination |        | <p>페이지 상세 조회<br>(브랜드 연동 상세조회 반환 값 참조)</p> |

### 브랜드 연동 상세 조회

* 해당 파트너와 연동된 브랜드를 조회합니다.
* **GET** /rcsapi/v1/brand
* Content-Type: application/json; charset=utf-8



**Request**

|   **키**  | **타입** | **필수** |                        **설명**                       |
| :------: | :----: | :----: | :-------------------------------------------------: |
|  brandId | String |    O   |                BizCenter에서 생성한 브랜드 ID               |
| brandKey | String |    O   | <p>BizCenter에서 기업 관리자가 발급하여 대행사에 전달한<br>브랜드 Key</p> |

****

**Response**

|    **키**   |                 |  **타입** |                   **설명**                  |
| :--------: | :-------------: | :-----: | :---------------------------------------: |
|    code    |                 |  String |                   결과 코드                   |
|   message  |                 |  String |                실패 시 결과 메시지                |
|    data    |                 |  Array  |                  성공 시 데이터                 |
|            |     brandId     |  String |           BizCenter에서 생성한 브랜드 ID          |
|            |     brandKey    |  String | BizCenter에서 기업 관리자가 발급하여 대행사에 전달한 브랜드 Key |
|            |   chatbotDate   |  String |                 챗봇 최종 수정일시                |
|            |     linkDate    |  String |                  파트너 연동일시                 |
|            | messagebaseDate |  String |                템플릿 최종 수정일시                |
|            |       name      |  String |                   브랜드 명                   |
|            |    partnerId    |  String |                  파트너 아이디                  |
|            |   registerDate  |  String |                  브랜드 등록일시                 |
|            |      status     |  String |                   브랜드 상태                  |
|            |    updateDate   |  String |                브랜드 최종 수정일시                |
| pagination |                 |         |                                           |
|            |      limit      | Integer |         조회 최대 건수 (기본:100, 최대:1000)        |
|            |      offset     | Integer |            시작 offset 번호 (기본:0)            |
|            |      total      | Integer |                    총 개수                   |

