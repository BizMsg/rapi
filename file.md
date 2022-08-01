# 파일 관리

### 파일 등록&#x20;

* Maap 미디어 파일을 등록합니다.
* **POST** /rcsapi/v1/file/send
* Content-Type: multipart/form-data

**Request**

|   **키**   | **타입** | **필수** |                      **설명**                     |
| :-------: | :----: | :----: | :---------------------------------------------: |
|    file   |  File  |    O   |                      업로드 파일                     |
|   fileId  | String |    O   |                      파일 ID                      |
|  mimeType | String |    O   |   <p>Mime type<br>(image/jpeg, image/png…)</p>  |
| usageType | String |    O   | <p>사용 타입</p><p>(chatbot, messagebase, send)</p> |

**Response**

|    Code    | String |                 결과 코드                 |
| :--------: | :----: | :-----------------------------------: |
|   Message  | String |              실패 시 결과 메시지              |
|    data    |        |  <p>파일 상세 조회<br>(파일 상세조회 반환 값 참조)</p> |
| pagination |        | <p>페이지 상세 조회<br>(파일 상세조회 반환 값 참조)</p> |

### 파일 상세 조회

* Maap 미디어 파일을 조회합니다.
* **GET** /rcsapi/v1/file/info
* Content-Type: application/json; charset=utf-8

**Request**

****

|  **키**  | **타입** | **필수** |        **설명**        |
| :-----: | :----: | :----: | :------------------: |
| comCode | String |    O   | 통신사 코드 (SKT, KT, U+) |
|  fileId | String |    O   |         파일 ID        |

**Response**

|    **키**   |    **-**   |  **타입** |                         **설명**                        |
| :--------: | :--------: | :-----: | :---------------------------------------------------: |
|    code    |            |  String |                         결과 코드                         |
|   message  |            |  String |                      실패 시 결과 메시지                      |
|    data    |            |  Array  |                        성공 시 데이터                       |
|            | expiryDate |  String |                         유효 기간                         |
|            |   fileId   |  String |                         파일 ID                         |
|            |  mimeType  |  String |      <p>Mime type<br>(image/jpeg, image/png)</p>      |
|            |   Status   |  String |            <p>파일 상태<br>(ready, expired)</p>           |
|            |  usageType |  String |      <p>사용 타입<br>(chatbot, messagebase, send)</p>     |
| pagination |            |         |                                                       |
|            |    limit   | Integer | <p>조회 최대 건수<br><strong></strong>(기본:100, 최대:1000)</p> |
|            |   offset   | Integer |             <p>시작 offset 번호<br>(기본:0)</p>             |
|            |    total   | Integer |                          총 개수                         |



### RCS MMS 이미지 규격&#x20;

![](<.gitbook/assets/image (5).png>)
