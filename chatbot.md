# 챗봇 관리

### 챗봇 등록

* 브랜드 내에서 사용할 챗봇을 등록합니다.\
  등록된 챗봇은 브랜드 포털 관리자의 승인 후 사용 가능합니다.
* **POST** /rcsapi/v1/brand/chatbot/create&#x20;
* Content-Type: multipart/form-data

**Request**

|       **키**       | **타입** | **필수** |               **설명**               |
| :---------------: | :----: | :----: | :--------------------------------: |
|      brandId      | String |    O   |       BizCenter 에서 생성한 브랜드 ID      |
|      display      | String |    X   |                전시 여부               |
|        mdn        | String |    O   |         등록할 발신번호 (국가번호는 생략)        |
|      rcsReply     | String |    O   | 수신모드 설정 (SMS MO:0, RCS Postback:1) |
|      service      | String |    X   |           A2P/CHAT 서비스 유형          |
|       subNum      | String |    X   |      챗봇 ID (A2P의 경우 발신번호와 동일)      |
| subNumCertificate |  File  |    O   |          통신 서비스 이용 증명원 파일          |
|      subTitle     | String |    O   |                챗봇 명                |
|      webhook      | String |    X   |    service가 chat인 경우 사용(URL, 필수)   |

**Response**

|    **키**   |      **-**     |  **타입** |                         **설명**                        |
| :--------: | :------------: | :-----: | :---------------------------------------------------: |
|    code    |                |  String |                         결과 코드                         |
|   message  |                |  String |                      실패 시 결과 메시지                      |
|    data    |                |  Array  |                        성공 시 데이터                       |
|            |  approvalDate  |  String |                        챗봇 승인 일시                       |
|            | approvalResult |  String |                         승인 상태                         |
|            |     brandId    |  String |                         브랜드 ID                        |
|            |    chatbotId   |  String |                챗봇 ID (A2P의 경우 발신번호와 동일)               |
|            |     display    |  String |                         전시 상태                         |
|            |     groupId    |  String |                  챗봇이 대량 등록된 경우 그룹 ID                  |
|            |    isMainNum   | Boolean |                       대표번호 여부 표시                      |
|            |  registerDate  |  String |                        챗봇 등록 일시                       |
|            |     subNum     |  String |           회신번호 A2P의 경우 발신번호 (chatbotId와 동일)           |
|            |    subTitle    |  String |                          챗봇 명                         |
|            |   updateDate   |  String |                        챗봇 수정일시                        |
| pagination |                |         |                                                       |
|            |      limit     | Integer | <p>조회 최대 건수<br><strong></strong>(기본:100, 최대:1000)</p> |
|            |     offset     | Integer |             <p>시작 offset 번호<br>(기본:0)</p>             |
|            |      total     | Integer |                          총 개수                         |

### 챗봇 수정

**Request**

|       **키**       | **타입** | **필수** |                             **설명**                            |
| :---------------: | :----: | :----: | :-----------------------------------------------------------: |
|      brandId      | String |    O   |                    BizCenter 에서 생성한 브랜드 ID                    |
|     chatbotId     | String |    O   |                    챗봇 ID (A2P의 경우 발신번호와 동일)                   |
|      display      | String |    X   |                             전시 여부                             |
|        mdn        | String |    O   |                      등록할 발신번호 (국가번호는 생략)                      |
|      rcsReply     | String |    O   | <p>수신모드 설정<br><strong></strong>(SMS MO:0, RCS Postback:1)</p> |
|      service      | String |    X   |                        A2P/CHAT 서비스 유형                        |
|       subNum      | String |    X   |                    챗봇 ID (A2P의 경우 발신번호와 동일)                   |
| subNumCertificate |  File  |    O   |                        통신 서비스 이용 증명원 파일                       |
|      subTitle     | String |    O   |                              챗봇 명                             |
|      webhook      | String |    X   |            <p>servicer가 chat인 경우 사용<br>(URL 필요)</p>           |

**Response**

|    **키**   |      **-**     |  **타입** |                         **설명**                        |
| :--------: | :------------: | :-----: | :---------------------------------------------------: |
|    code    |                |  String |                         결과 코드                         |
|   message  |                |  String |                      실패 시 결과 메시지                      |
|    data    |                |  Array  |                        성공 시 데이터                       |
|            |  approvalDate  |  String |                        챗봇 승인 일시                       |
|            | approvalReason |  String |                         승인 사유                         |
|            | approvalResult |  String |                         승인 상태                         |
|            |    botTcPage   |  String |                 이용 약관 페이지 URL (수정 불가)                 |
|            |     brandId    |  String |                         브랜드 ID                        |
|            |    chatbotId   |  String |                챗봇 ID (A2P의 경우 발신번호와 동일)               |
|            |     display    |  String |                         전시 상태                         |
|            |     groupId    |  String |                  챗봇이 대량 등록된 경우 그룹 ID                  |
|            |    isMainNum   | Boolean |                       대표번호 여부 표시                      |
|            |    mediaUrl    |  Array  |              이미지 파일 ID와 URL 및 사용 유형 정보를 제             |
|            |  registerDate  |  String |                        챗봇 등록 일시                       |
|            |   registerId   |  String |                      챗봇 등록 계정 ID                      |
|            |  searchWeight  |  String |                    검색 우선 순위 (수정 불가)                   |
|            |     service    |  String |                    A2P/CHAT 서비스 유형                    |
|            |     subNum     |  String |      <p>회신번호 A2P의 경우 발신번호<br>(chatbotId와 동일)</p>      |
|            |    subTitle    |  String |                          챗봇 명                         |
|            |   updateDate   |  String |                        챗봇 수정일시                        |
|            |    updateId    |  String |                      챗봇 수정 계정 ID                      |
|            |     webhook    |  String |             service가 chat인 경우 사용 (URL 필수)             |
| pagination |                |         |                                                       |
|            |      limit     | Integer | <p>조회 최대 건수<br><strong></strong>(기본:100, 최대:1000)</p> |
|            |     offset     | Integer |             <p>시작 offset 번호<br>(기본:0)</p>             |
|            |      total     | Integer |                          총 개수                         |

### 챗봇 삭제

* 브랜드 내 지정된 챗봇을 삭제합니다.\
  챗봇의 삭제는 승인상태에 따라 처리 여부가 결정됩니다. 한번 삭제된 챗봇은 복원이 불가능 하며, 동일한 ID 로 생성할 수 없습니다. (상태: 저장, 반려, 승인)
* **POST** /rcsapi/v1/brand/chatbot/remove
* Content-Type: application/json; charset=utf-8

**Request**

|   **키**   | **타입** | **필수** |          **설명**         |
| :-------: | :----: | :----: | :---------------------: |
|  brandId  | String |    O   | BizCenter 에서 생성한 브랜드 ID |
| chatbotId | String |    O   |        삭제할 챗봇 ID        |

**Response**

****

|    **키**   |   **-**   |  **타입** |                         **설명**                        |
| :--------: | :-------: | :-----: | :---------------------------------------------------: |
|    code    |           |  String |                         결과 코드                         |
|   message  |           |  String |                      실패 시 결과 메시지                      |
|    data    |           |  Array  |                        성공 시 데이터                       |
|            | chatbotId |  String |         <p>챗봇 ID </p><p>(A2P 의 경우 발번호와 동일)</p>        |
| pagination |           |         |                                                       |
|            |   limit   | Integer | <p>조회 최대 건수<br><strong></strong>(기본:100, 최대:1000)</p> |
|            |   offset  | Integer |             <p>시작 offset 번호<br>(기본:0)</p>             |
|            |   total   | Integer |                          총 개수                         |



### 챗봇 목록 조회

* 브랜드 내에 등록된 챗봇 목록을 조회합니다.
* **GET** /rcsapi/v1/brand/chatbot/list
* Content-Type: application/json; charset=utf-8

**Request**

|  **키**  |  **타입** | **필수** |           **설명**           |
| :-----: | :-----: | :----: | :------------------------: |
| brandId |  String |    O   |   BizCenter 에서 생성한 브랜드 ID  |
|  limit  | Integer |    X   | 조회 최대 건수 (기본:100, 최대:1000) |
|  offset | Integer |    O   |     시작 offset 번호 (기본:0)    |

**Response**

|    **키**   |      **-**     |  **타입** |                         **설명**                        |
| :--------: | :------------: | :-----: | :---------------------------------------------------: |
|    code    |                |  String |                         결과 코드                         |
|   message  |                |  String |                      실패 시 결과 메시지                      |
|    data    |                |  Array  |                        성공 시 데이터                       |
|            |  approvalDate  |  String |                        챗봇 승인 일시                       |
|            | approvalResult |  String |                         승인 상태                         |
|            |     brandId    |  String |                         브랜드 ID                        |
|            |    chatbotId   |  String |                챗봇 ID (A2P의 경우 발신번호와 동일)               |
|            |     display    |  String |                         전시 상태                         |
|            |     groupId    |  String |                  챗봇이 대량 등록된 경우 그룹 ID                  |
|            |    isMainNum   | Boolean |                       대표번호 여부 표시                      |
|            |  registerDate  |  String |                        챗봇 등록 일시                       |
|            |     subNum     |  String |           회신번호 A2P의 경우 발신번호 (chatbotId와 동일)           |
|            |    subTitle    |  String |                          챗봇 명                         |
|            |   updateDate   |  String |                        챗봇 수정일시                        |
| pagination |                |         |                                                       |
|            |      limit     | Integer | <p>조회 최대 건수<br><strong></strong>(기본:100, 최대:1000)</p> |
|            |     offset     | Integer |             <p>시작 offset 번호<br>(기본:0)</p>             |
|            |      total     | Integer |                          총 개수                         |

### 챗봇 상세 조회

* 브랜드에 등록된 챗봇 상세 내역을 조회합니다.
* **GET** /rcsapi/v1/brand/chatbot/info
* Content-Type: application/json; charset=utf-8

**Request**

|   **키**   | **타입** | **필수** |          **설명**         |
| :-------: | :----: | :----: | :---------------------: |
|  brandId  | String |    O   | BizCenter 에서 생성한 브랜드 ID |
| chatbotId | String |    O   |       조회할 대상 챗봇 ID      |

**Response**

|    **키**   |      **-**     |  **타입** |                         **설명**                        |
| :--------: | :------------: | :-----: | :---------------------------------------------------: |
|    code    |                |  String |                         결과 코드                         |
|   message  |                |  String |                      실패 시 결과 메시지                      |
|    data    |                |  Array  |                        성공 시 데이터                       |
|            |  approvalDate  |  String |                        챗봇 승인 일시                       |
|            | approvalReason |  String |                         승인 사유                         |
|            | approvalResult |  String |                         승인 상태                         |
|            |    botTcPage   |  String |                 이용 약관 페이지 URL (수정 불가)                 |
|            |     brandId    |  String |                         브랜드 ID                        |
|            |    chatbotId   |  String |                챗봇 ID (A2P의 경우 발신번호와 동일)               |
|            |     display    |  String |                         전시 상태                         |
|            |     groupId    |  String |                  챗봇이 대량 등록된 경우 그룹 ID                  |
|            |    isMainNum   | Boolean |                       대표번호 여부 표시                      |
|            |    mediaUrl    |  Array  |              이미지 파일 ID와 URL 및 사용 유형 정보를 제             |
|            |  registerDate  |  String |                        챗봇 등록 일시                       |
|            |   registerId   |  String |                      챗봇 등록 계정 ID                      |
|            |  searchWeight  |  String |                    검색 우선 순위 (수정 불가)                   |
|            |     service    |  String |                    A2P/CHAT 서비스 유형                    |
|            |     subNum     |  String |      <p>회신번호 A2P의 경우 발신번호<br>(chatbotId와 동일)</p>      |
|            |    subTitle    |  String |                          챗봇 명                         |
|            |   updateDate   |  String |                        챗봇 수정일시                        |
|            |    updateId    |  String |                      챗봇 수정 계정 ID                      |
|            |     webhook    |  String |             service가 chat인 경우 사용 (URL 필수)             |
| pagination |                |         |                                                       |
|            |      limit     | Integer | <p>조회 최대 건수<br><strong></strong>(기본:100, 최대:1000)</p> |
|            |     offset     | Integer |             <p>시작 offset 번호<br>(기본:0)</p>             |
|            |      total     | Integer |                          총 개수                         |

