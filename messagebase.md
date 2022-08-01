# 메세지베이스 관리

### 메시지베이스 등록

* 브랜드 내에서 사용할 메시지베이스를 등록합니다.\
  등록된 메시지 베이스는 브랜드 포털 관리자의 승인 후 사용 가능하며, 템플릿 등록시 사용되는**messagebaseformId** 의 **formattedString** 을 이용하여 등록해야 합니다.
* **POST** /rcsapi/v1/brand/msgbase/create
* Content-Type: application/json; charset=utf-8

**Request**

|       **키**       | **타입** | **필수** |                          **설명**                         |
| :---------------: | :----: | :----: | :-----------------------------------------------------: |
|      brandId      | String |    O   |                 BizCenter 에서 생성한 브랜드 ID                 |
|    custTmpltId    | String |    O   | <p>사용자 지정 템플릿 ID</p><p>(정규식패턴: ^[0-9A-Za-z]{1,25}$)</p> |
| messagebaseformId | String |    O   |  <p>메시지베이스 폼 ID</p><p>(정규식패턴: ^[0-9A-Za-z]{1,10}$)</p>  |
|  formattedString  | Object |    O   |                        메시지베이스 포맷                        |
|     tmpltName     | String |    O   |                         메시지베이스 명                        |

****

**Response**

|    **키**   |     **-**     |  **타입** |                         **설명**                        |
| :--------: | :-----------: | :-----: | :---------------------------------------------------: |
|    code    |               |  String |                         결과 코드                         |
|   message  |               |  String |                      실패 시 결과 메시지                      |
|    data    |               |         |                        성공 시 데이터                       |
|            | messagebaseId |  String |                       메시지베이스 ID                       |
| pagination |               |         |                                                       |
|            |     limit     | Integer | <p>조회 최대 건수<br><strong></strong>(기본:100, 최대:1000)</p> |
|            |     offset    | Integer |                  시작 offset 번호 (기본:0)                  |
|            |     total     | Integer |                          총 개수                         |

****

### 메시지베이스 수정

* 브랜드 내에서 사용할 메시지베이스를 수정합니다.\
  메시지베이스 수정은 승인상태에 따라 처리 여부가 결정됩니다. 템플릿 수정 시에는 기존에 사용된 messagebaseformId 를 동일한 cardType(cell, description)에 한하여 변경할 수 있습니다. (상태: 저장, 반려)
* POST /rcsapi/v1/brand/msgbase/update
* Content-Type: application/json; charset=utf-8

**Request**

|       **키**       | **타입** | **필수** |                          **설명**                         |
| :---------------: | :----: | :----: | :-----------------------------------------------------: |
|      brandId      | String |    O   |                 BizCenter 에서 생성한 브랜드 ID                 |
|    custTmpltId    | String |    O   | <p>사용자 지정 템플릿 ID</p><p>(정규식패턴: ^[0-9A-Za-z]{1,25}$)</p> |
|   messagebaseId   | String |    O   |                        메시지베이스 ID                        |
| messagebaseformId | String |    O   |  <p>메시지베이스 폼 ID</p><p>(정규식패턴: ^[0-9A-Za-z]{1,10}$)</p>  |
|  formattedString  | Object |    O   |                        메시지베이스 포맷                        |
|     tmpltName     | String |    O   |                         메시지베이스 명                        |

****

**Response**

|    **키**   |     **-**     |  **타입** |                         **설명**                        |
| :--------: | :-----------: | :-----: | :---------------------------------------------------: |
|    code    |               |  String |                         결과 코드                         |
|   message  |               |  String |                      실패 시 결과 메시지                      |
|    data    |               |         |                        성공 시 데이터                       |
|            | messagebaseId |  String |                       메시지베이스 ID                       |
| pagination |               |         |                                                       |
|            |     limit     | Integer | <p>조회 최대 건수<br><strong></strong>(기본:100, 최대:1000)</p> |
|            |     offset    | Integer |                  시작 offset 번호 (기본:0)                  |
|            |     total     | Integer |                          총 개수                         |

### 메시지베이스 삭제

* 브랜드 내에서 지정된 메시지베이스를 삭제합니다.\
  메시지베이스 삭제는 승인상태에 따라 처리 여부가 결정됩니다. 한번 삭제된 메시지베이스는 복원이 불가능하며 동일한 ID로 생성할 수 없습니다.
* **POST** /rcsapi/v1/brand/msgbase/remove
* Content-Type: application/json; charset=utf-8

**Request**

|     **키**     | **타입** | **필수** |          **설명**         |
| :-----------: | :----: | :----: | :---------------------: |
|    brandId    | String |    O   | BizCenter 에서 생성한 브랜드 ID |
| messagebaseId | String |    O   |        메시지베이스 ID        |

**Response**

|    **키**   |     **-**     |  **타입** |                         **설명**                        |
| :--------: | :-----------: | :-----: | :---------------------------------------------------: |
|    code    |               |  String |                         결과 코드                         |
|   message  |               |  String |                      실패 시 결과 메시지                      |
|    data    |               |         |                        성공 시 데이터                       |
|            | messagebaseId |  String |                       메시지베이스 ID                       |
| pagination |               |         |                                                       |
|            |     limit     | Integer | <p>조회 최대 건수<br><strong></strong>(기본:100, 최대:1000)</p> |
|            |     offset    | Integer |                  시작 offset 번호 (기본:0)                  |
|            |     total     | Integer |                          총 개수                         |

### 메시지베이스 목록 조회

* 브랜드에 등록된 메시지베이스 목록을 조회합니다.
* **GET** /rcsapi/v1/brand/msgbase/list
* Content-Type: application/json; charset=utf-8

**Request**

|  **키**  |  **타입** | **필수** |                  **설명**                  |
| :-----: | :-----: | :----: | :--------------------------------------: |
| brandId |  String |    O   |          BizCenter 에서 생성한 브랜드 ID         |
|  limit  | Integer |    X   | <p>조회 최대 건수<br>(기본 : 100, 최대 : 1000)</p> |
|  offset | Integer |    X   |            시작 offset 번호 (기본:0)           |

****

**Response**

|    **키**   |       **-**       |  **타입** |                         **설명**                        |
| :--------: | :---------------: | :-----: | :---------------------------------------------------: |
|    code    |                   |  String |                         결과 코드                         |
|   message  |                   |  String |                      실패 시 결과 메시지                      |
|    data    |                   |         |                        성공 시 데이터                       |
|            |    approvalDate   |  String |                      메시지베이스 승인 일시                     |
|            |   approvalReason  |  String |                         승인 사유                         |
|            |   approvalResult  |  String |                         승인 상태                         |
|            |      brandId      |  String |                         브랜드 ID                        |
|            |      groupId      |  String |                         그룹 ID                         |
|            |   messagebaseId   |  String |                       메시지베이스 ID                       |
|            | messagebaseformId |  String |                      메시지베이스 폼 ID                      |
|            |    registerDate   |  String |                      메시지베이스 등록 일시                     |
|            |     registerId    |  String |                    메시지베이스 등록 계정 ID                    |
|            |       status      |  String |                       메시지베이스 상태                       |
|            |     tmpltName     |  String |                        메시지베이스 명                       |
|            |     updateDate    |  String |                      메시지베이스 수정 일시                     |
|            |      updateId     |  String |                    메시지베이스 수정 계정 ID                    |
| pagination |                   |         |                                                       |
|            |       limit       | Integer | <p>조회 최대 건수<br><strong></strong>(기본:100, 최대:1000)</p> |
|            |       offset      | Integer |                  시작 offset 번호 (기본:0)                  |
|            |       total       | Integer |                          총 개수                         |

### 메시지베이스 상세 조회

* 브랜드에 등록된 지정 메시지베이스의 상세 내역을 조회합니다.
* **GET** /rcsapi/v1/brand/msgbase/info
* Content-Type: application/json; charset=utf-8



**Request**

|     **키**     | **타입** | **필수** |          **설명**         |
| :-----------: | :----: | :----: | :---------------------: |
|    brandId    | String |    O   | BizCenter 에서 생성한 브랜드 ID |
| messagebaseId | String |    O   |        메시지베이스 ID        |

**Response**

|    **키**   |       **-**       |  **타입** |                         **설명**                        |
| :--------: | :---------------: | :-----: | :---------------------------------------------------: |
|    code    |                   |  String |                         결과 코드                         |
|   message  |                   |  String |                      실패 시 결과 메시지                      |
|    data    |                   |         |                        성공 시 데이터                       |
|            |      agecyId      |  String |                                                       |
|            |    approvalDate   |  String |                      메시지베이스 승인 일시                     |
|            |   approvalReason  |  String |                         승인 사유                         |
|            |   approvalResult  |  String |                         승인 상태                         |
|            |     attribute     |  Array  |                                                       |
|            |      brandId      |  String |                         브랜드 ID                        |
|            |      cardType     |  String |            카드 종류 (Cell, Description, Free)            |
|            |  formattedString  |  Object |                       메시지베이스 포맷                       |
|            |      groupId      |  String |                         그룹 ID                         |
|            |     guideInfo     |  Object |                                                       |
|            |     inputText     |  String |                                                       |
|            |   messagebaseId   |  String |                       메시지베이스 ID                       |
|            | messagebaseformId |  String |                      메시지베이스 폼 ID                      |
|            |       params      |  Array  |                                                       |
|            |     policyInfo    |  Object |                                                       |
|            |    registerDate   |  String |                      메시지베이스 등록 일시                     |
|            |     registerId    |  String |                    메시지베이스 등록 계정 ID                    |
|            |        spec       |  String |                                                       |
|            |       status      |  String |                       메시지베이스 상태                       |
|            |     tmpltName     |  String |                        메시지베이스 명                       |
|            |     updateDate    |  String |                      메시지베이스 수정 일시                     |
|            |      updateId     |  String |                    메시지베이스 수정 계정 ID                    |
| pagination |                   |         |                                                       |
|            |       limit       | Integer | <p>조회 최대 건수<br><strong></strong>(기본:100, 최대:1000)</p> |
|            |       offset      | Integer |                  시작 offset 번호 (기본:0)                  |
|            |       total       | Integer |                          총 개수                         |



### 메시지베이스 양식 목록 조회

* 오픈리치카드 템플릿 작성이 필요한 경우 조회된 템플릿 양식 ID를 이용하여 **messagebaseform** 세부정보를 조회합니다.
* **GET** /rcsapi/v1/msgbaseform/list
* Content-Type: application/json; charset=utf-8

**Request**

|     **키**    |  **타입** | **필수** |                           **설명**                          |
| :----------: | :-----: | :----: | :-------------------------------------------------------: |
|  bizCategory |  String |    X   | <p>유형 그룹<br>(Description, Cell 에서만 사용 / 일반, 금용, 교통 등)</p> |
| bizCondition |  String |    X   |                      대상 업태 (기본: all)                      |
|  bizService  |  String |    X   |                     유형 (승인, 입금, 출금 등)                     |
|   cardType   |  String |    X   |         <p>카드 종류<br>(Cell, Description, Free)</p>         |
|     limit    | Integer |    X   |          <p>조회 최대 건수<br>(기본 : 100, 최대 : 1000)</p>         |
|    offset    | Integer |    X   |                    시작 offset 번호 (기본:0)                    |

**Response**

|    **키**   |       **-**       |  **타입** |                           **설명**                          |
| :--------: | :---------------: | :-----: | :-------------------------------------------------------: |
|    code    |                   |  String |                           결과 코드                           |
|   message  |                   |  String |                        실패 시 결과 메시지                        |
|    data    |                   |         |                          성공 시 데이터                         |
|            |    bizCategory    |  String | <p>유형 그룹<br>(Description, Cell 에서만 사용 / 일반, 금용, 교통 등)</p> |
|            |    bizCondition   |  Array  |                      대상 업태 (기본: all)                      |
|            |     bizService    |  String |                     유형 (승인, 입금, 출금 등)                     |
|            |      cardType     |  String |              카드 종류 (Cell, Description, Free)              |
|            |      formName     |  String |                            폼 명                            |
|            | messagebaseformId |  String |                        메시지베이스 폼 ID                        |
|            |    registerDate   |  String |                           등록 일자                           |
|            |     updateDate    |  String |                           수정 일자                           |
| pagination |                   |         |                                                           |
|            |       limit       | Integer |   <p>조회 최대 건수<br><strong></strong>(기본:100, 최대:1000)</p>   |
|            |       offset      | Integer |                    시작 offset 번호 (기본:0)                    |
|            |       total       | Integer |                            총 개수                           |

### 메시지베이스 유형 상세 조회

* 메시지베이스 유형의 상세 내용을 조회합니다.\
  **formattedString** 을 이용하여 원하는 브랜드용 메시지베이스를 작성할 수 있습니다.
* **GET** /rcsapi/v1/msgbaseform/info
* Content-Type: application/json; charset=utf-8

**Request**

|       **키**       | **타입** | **필수** |   **설명**  |
| :---------------: | :----: | :----: | :-------: |
| messagebaseformId | String |    O   | 메시지베이스 ID |

**Response**

|    **키**   |       **-**       |  **타입** |                           **설명**                          |
| :--------: | :---------------: | :-----: | :-------------------------------------------------------: |
|    code    |                   |  String |                           결과 코드                           |
|   message  |                   |  String |                        실패 시 결과 메시지                        |
|    data    |                   |         |                          성공 시 데이터                         |
|            |    bizCategory    |  String | <p>유형 그룹<br>(Description, Cell 에서만 사용 / 일반, 금용, 교통 등)</p> |
|            |    bizCondition   |  Array  |                      대상 업태 (기본: all)                      |
|            |     bizService    |  String |                     유형 (승인, 입금, 출금 등)                     |
|            |      cardType     |  String |              카드 종류 (Cell, Description, Free)              |
|            |      formName     |  String |                            폼 명                            |
|            |  formattedString  |  Object |                         메시지베이스 포맷                         |
|            |     guideInfo     |  Object |                                                           |
|            |      mediaUrl     |  Array  |                                                           |
|            | messagebaseformId |  String |                        메시지베이스 폼 ID                        |
|            |       params      |  Array  |                                                           |
|            |     policyInfo    |  Object |                                                           |
|            |    productCode    |  String |                                                           |
|            |        spec       |  String |                                                           |
|            |    registerDate   |  String |                           등록 일자                           |
|            |     updateDate    |  String |                           수정 일자                           |
| pagination |                   |         |                                                           |
|            |       limit       | Integer |   <p>조회 최대 건수<br><strong></strong>(기본:100, 최대:1000)</p>   |
|            |       offset      | Integer |                    시작 offset 번호 (기본:0)                    |
|            |       total       | Integer |                            총 개수                           |

### 메시지베이스 조회 (이통사 기본 제공)

* 리치카드 규격의 SMS, LMS, MMS 용 메시지베이스를 조회합니다. (현재 리치카드는 비즈니스 유형 별로 제공되는 항목은 없습니다.)
* **GET** /rcsapi/v1/msgbase/common/list
* Content-Type: application/json; charset=utf-8



**Request**

|    **키**    |  **타입** | **필수** |                                                    **설명**                                                   |
| :---------: | :-----: | :----: | :---------------------------------------------------------------------------------------------------------: |
|   cardType  |  String |    X   | <p>카드 종류 <br>(standalone, standalone media top, standalone horizontal, carousel medium, carousel small)</p> |
| productCode |  String |    X   |                                            상품 코드 (sms, lms, mms)                                            |
|    limit    | Integer |    X   |                                   <p>조회 최대 건수<br>(기본 : 100, 최대 : 1000)</p>                                  |
|    offset   | Integer |    X   |                                             시작 offset 번호 (기본:0)                                             |

**Response**

|    **키**   |       **-**       |  **타입** |                         **설명**                        |
| :--------: | :---------------: | :-----: | :---------------------------------------------------: |
|    code    |                   |  String |                         결과 코드                         |
|   message  |                   |  String |                      실패 시 결과 메시지                      |
|    data    |                   |         |                        성공 시 데이터                       |
|            |    approvalDate   |  String |                      메시지베이스 승인 일시                     |
|            |   approvalReason  |  String |                         승인 사유                         |
|            |   approvalResult  |  String |                         승인 상태                         |
|            |      brandId      |  String |                         브랜드 ID                        |
|            |      groupId      |  String |                         그룹 ID                         |
|            |   messagebaseId   |  String |                       메시지베이스 ID                       |
|            | messagebaseformId |  String |                      메시지베이스 폼 ID                      |
|            |    registerDate   |  String |                      메시지베이스 등록 일시                     |
|            |     registerId    |  String |                    메시지베이스 등록 계정 ID                    |
|            |       status      |  String |                       메시지베이스 상태                       |
|            |     tmpltName     |  String |                        메시지베이스 명                       |
|            |     updateDate    |  String |                      메시지베이스 수정 일시                     |
|            |      updateId     |  String |                    메시지베이스 수정 계정 ID                    |
| pagination |                   |         |                                                       |
|            |       limit       | Integer | <p>조회 최대 건수<br><strong></strong>(기본:100, 최대:1000)</p> |
|            |       offset      | Integer |                  시작 offset 번호 (기본:0)                  |
|            |       total       | Integer |                          총 개수                         |

### 메시지베이스 상세 조회 (이통사 기본 제공)

* 이통사가 기본 제공하는 메시지베이스의 상세 내용을 조회합니다.\
  리치카드 규격의 SMS, LMS, MMS 용 메시지베이스를 조회합니다. 비즈니스 유형에 따라 조회할 수 있습니다.
* GET /rcsapi/v1/msgbse/common/info
* Content-Type: application/json; charset=utf-8



**Request**

|     **키**     | **타입** | **필수** |   **설명**  |
| :-----------: | :----: | :----: | :-------: |
| messagebaseId | String |    O   | 메시지베이스 ID |

**Response**

|    **키**   |       **-**       |  **타입** |                         **설명**                        |
| :--------: | :---------------: | :-----: | :---------------------------------------------------: |
|    code    |                   |  String |                         결과 코드                         |
|   message  |                   |  String |                      실패 시 결과 메시지                      |
|    data    |                   |         |                        성공 시 데이터                       |
|            |      agecyId      |  String |                                                       |
|            |    approvalDate   |  String |                      메시지베이스 승인 일시                     |
|            |   approvalReason  |  String |                         승인 사유                         |
|            |   approvalResult  |  String |                         승인 상태                         |
|            |     attribute     |  Array  |                                                       |
|            |      brandId      |  String |                         브랜드 ID                        |
|            |      cardType     |  String |            카드 종류 (Cell, Description, Free)            |
|            |  formattedString  |  Object |                       메시지베이스 포맷                       |
|            |      groupId      |  String |                         그룹 ID                         |
|            |     guideInfo     |  Object |                                                       |
|            |     inputText     |  String |                                                       |
|            |   messagebaseId   |  String |                       메시지베이스 ID                       |
|            | messagebaseformId |  String |                      메시지베이스 폼 ID                      |
|            |       params      |  Array  |                                                       |
|            |     policyInfo    |  Object |                                                       |
|            |    registerDate   |  String |                      메시지베이스 등록 일시                     |
|            |     registerId    |  String |                    메시지베이스 등록 계정 ID                    |
|            |        spec       |  String |                                                       |
|            |       status      |  String |                       메시지베이스 상태                       |
|            |     tmpltName     |  String |                        메시지베이스 명                       |
|            |     updateDate    |  String |                      메시지베이스 수정 일시                     |
|            |      updateId     |  String |                    메시지베이스 수정 계정 ID                    |
| pagination |                   |         |                                                       |
|            |       limit       | Integer | <p>조회 최대 건수<br><strong></strong>(기본:100, 최대:1000)</p> |
|            |       offset      | Integer |                  시작 offset 번호 (기본:0)                  |
|            |       total       | Integer |                          총 개수                         |
