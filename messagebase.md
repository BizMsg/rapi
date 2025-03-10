# 메세지베이스 관리

### 메시지베이스 등록

* 브랜드 내에서 사용할 메시지베이스를 등록합니다.\
  등록된 메시지 베이스는 브랜드 포털 관리자의 승인 후 사용 가능하며, 템플릿 등록시 사용되는**messagebaseformId** 의 **formattedString** 을 이용하여 등록해야 합니다.
* **POST** /rcsapi/v1/brand/msgbase/create
* Content-Type: application/json; charset=utf-8

**Request**

<table data-header-hidden><thead><tr><th width="220" align="center"></th><th width="150" align="center"></th><th width="150" align="center"></th><th width="293" align="center"></th></tr></thead><tbody><tr><td align="center"><strong>키</strong></td><td align="center"><strong>타입</strong></td><td align="center"><strong>필수</strong></td><td align="center"><strong>설명</strong></td></tr><tr><td align="center">brandId</td><td align="center">String</td><td align="center">O</td><td align="center">BizCenter 에서 생성한 브랜드 ID</td></tr><tr><td align="center">custTmpltId</td><td align="center">String</td><td align="center">O</td><td align="center"><p>사용자 지정 템플릿 ID</p><p>(정규식패턴: ^[0-9A-Za-z]{1,25}$)</p></td></tr><tr><td align="center">messagebaseformId</td><td align="center">String</td><td align="center">O</td><td align="center"><p>메시지베이스 폼 ID</p><p>(정규식패턴: ^[0-9A-Za-z]{1,10}$)</p></td></tr><tr><td align="center">formattedString</td><td align="center">Object</td><td align="center">O</td><td align="center">메시지베이스 포맷</td></tr><tr><td align="center">tmpltName</td><td align="center">String</td><td align="center">O</td><td align="center">메시지베이스 명</td></tr></tbody></table>

**Response**

<table data-header-hidden><thead><tr><th width="150" align="center"></th><th width="153" align="center"></th><th width="150" align="center"></th><th width="276" align="center"></th></tr></thead><tbody><tr><td align="center"><strong>키</strong></td><td align="center"><strong>-</strong></td><td align="center"><strong>타입</strong></td><td align="center"><strong>설명</strong></td></tr><tr><td align="center">code</td><td align="center"></td><td align="center">String</td><td align="center">결과 코드</td></tr><tr><td align="center">message</td><td align="center"></td><td align="center">String</td><td align="center">실패 시 결과 메시지</td></tr><tr><td align="center">data</td><td align="center"></td><td align="center"></td><td align="center">성공 시 데이터</td></tr><tr><td align="center"></td><td align="center">messagebaseId</td><td align="center">String</td><td align="center">메시지베이스 ID</td></tr><tr><td align="center">pagination</td><td align="center"></td><td align="center"></td><td align="center"></td></tr><tr><td align="center"></td><td align="center">limit</td><td align="center">Integer</td><td align="center">조회 최대 건수<br>(기본:100, 최대:1000)</td></tr><tr><td align="center"></td><td align="center">offset</td><td align="center">Integer</td><td align="center">시작 offset 번호 (기본:0)</td></tr><tr><td align="center"></td><td align="center">total</td><td align="center">Integer</td><td align="center">총 개수</td></tr></tbody></table>

###

### 메시지베이스 수정

* 브랜드 내에서 사용할 메시지베이스를 수정합니다.\
  메시지베이스 수정은 승인상태에 따라 처리 여부가 결정됩니다. 템플릿 수정 시에는 기존에 사용된 messagebaseformId 를 동일한 cardType(cell, description)에 한하여 변경할 수 있습니다. \
  (상태: 저장, 반려)
* POST /rcsapi/v1/brand/msgbase/update
* Content-Type: application/json; charset=utf-8

**Request**

<table data-header-hidden><thead><tr><th width="220" align="center"></th><th width="150" align="center"></th><th width="150" align="center"></th><th width="293" align="center"></th></tr></thead><tbody><tr><td align="center"><strong>키</strong></td><td align="center"><strong>타입</strong></td><td align="center"><strong>필수</strong></td><td align="center"><strong>설명</strong></td></tr><tr><td align="center">brandId</td><td align="center">String</td><td align="center">O</td><td align="center">BizCenter 에서 생성한 브랜드 ID</td></tr><tr><td align="center">custTmpltId</td><td align="center">String</td><td align="center">O</td><td align="center"><p>사용자 지정 템플릿 ID</p><p>(정규식패턴: ^[0-9A-Za-z]{1,25}$)</p></td></tr><tr><td align="center">messagebaseId</td><td align="center">String</td><td align="center">O</td><td align="center">메시지베이스 ID</td></tr><tr><td align="center">messagebaseformId</td><td align="center">String</td><td align="center">O</td><td align="center"><p>메시지베이스 폼 ID</p><p>(정규식패턴: ^[0-9A-Za-z]{1,10}$)</p></td></tr><tr><td align="center">formattedString</td><td align="center">Object</td><td align="center">O</td><td align="center">메시지베이스 포맷</td></tr><tr><td align="center">tmpltName</td><td align="center">String</td><td align="center">O</td><td align="center">메시지베이스 명</td></tr></tbody></table>

**Response**

<table data-header-hidden><thead><tr><th width="150" align="center"></th><th width="158.98765432098767" align="center"></th><th width="150" align="center"></th><th width="276" align="center"></th></tr></thead><tbody><tr><td align="center"><strong>키</strong></td><td align="center"><strong>-</strong></td><td align="center"><strong>타입</strong></td><td align="center"><strong>설명</strong></td></tr><tr><td align="center">code</td><td align="center"></td><td align="center">String</td><td align="center">결과 코드</td></tr><tr><td align="center">message</td><td align="center"></td><td align="center">String</td><td align="center">실패 시 결과 메시지</td></tr><tr><td align="center">data</td><td align="center"></td><td align="center"></td><td align="center">성공 시 데이터</td></tr><tr><td align="center"></td><td align="center">messagebaseId</td><td align="center">String</td><td align="center">메시지베이스 ID</td></tr><tr><td align="center">pagination</td><td align="center"></td><td align="center"></td><td align="center"></td></tr><tr><td align="center"></td><td align="center">limit</td><td align="center">Integer</td><td align="center">조회 최대 건수<br>(기본:100, 최대:1000)</td></tr><tr><td align="center"></td><td align="center">offset</td><td align="center">Integer</td><td align="center">시작 offset 번호 (기본:0)</td></tr><tr><td align="center"></td><td align="center">total</td><td align="center">Integer</td><td align="center">총 개수</td></tr></tbody></table>

###

### 메시지베이스 등록 v2

* 브랜드 내에서 사용할 메시지베이스을 등록합니다.\
  모든 메시지베이스 등록이 가능합니다.                                                                                                               템플릿 등록 시 사용되는 messagebaseformId의 params의 각 항목 중 메시지베이스에 표시될 내용을 입력하여 원하는 메시지베이스을 등록할 수 있습니다.                                                                                    등록된 메시지베이스은 RCS Biz Center 운영자의 승인이 필요합니다.
* **POST** /rcsapi/v1/brand/msgbase/v2/create
* Content-Type: application/json; charset=utf-8

**Request**

<table data-header-hidden><thead><tr><th width="220" align="center"></th><th width="150" align="center"></th><th width="150" align="center"></th><th width="293" align="center"></th></tr></thead><tbody><tr><td align="center"><strong>키</strong></td><td align="center"><strong>타입</strong></td><td align="center"><strong>필수</strong></td><td align="center"><strong>설명</strong></td></tr><tr><td align="center">brandId</td><td align="center">String</td><td align="center">O</td><td align="center">BizCenter 에서 생성한 브랜드 ID</td></tr><tr><td align="center">messagebaseformId</td><td align="center">String</td><td align="center">O</td><td align="center"><p>메시지베이스 폼 ID</p><p>(정규식패턴: ^[0-9A-Za-z]{1,10}$)</p><p></p></td></tr><tr><td align="center">custTmpltId</td><td align="center">String</td><td align="center">O</td><td align="center"><p>사용자 지정 템플릿 ID</p><p>(정규식패턴: ^[0-9A-Za-z]{1,25}$)</p></td></tr><tr><td align="center">tmpltName</td><td align="center">String</td><td align="center">O</td><td align="center">메시지베이스 명</td></tr><tr><td align="center">body</td><td align="center">Array</td><td align="center">O</td><td align="center">*<strong>BODY</strong> 참조</td></tr><tr><td align="center">buttons</td><td align="center">Array</td><td align="center">X</td><td align="center"><p>메시지베이스에 삽입할 버튼정보</p><p>* <strong>BUTTONS</strong> 참조</p></td></tr></tbody></table>

**Response**

<table data-header-hidden><thead><tr><th width="150" align="center"></th><th width="153" align="center"></th><th width="150" align="center"></th><th width="276" align="center"></th></tr></thead><tbody><tr><td align="center"><strong>키</strong></td><td align="center"><strong>-</strong></td><td align="center"><strong>타입</strong></td><td align="center"><strong>설명</strong></td></tr><tr><td align="center">code</td><td align="center"></td><td align="center">String</td><td align="center">결과 코드</td></tr><tr><td align="center">message</td><td align="center"></td><td align="center">String</td><td align="center">실패 시 결과 메시지</td></tr><tr><td align="center">data</td><td align="center"></td><td align="center"></td><td align="center">성공 시 데이터</td></tr><tr><td align="center"></td><td align="center">messagebaseId</td><td align="center">String</td><td align="center">메시지베이스 ID</td></tr></tbody></table>

###

### 메시지베이스 수정 v2

* 이미 등록된 템플릿의 내용을 수정합니다.\
  messagebase의 ID를 유지하면서 내용을 변경하고자 하는 경우 사용이 가능합니다.                               수정 등록된 템플릿은 RCS Biz Center 운영자의 승인이 필요합니다.
* **POST** /rcsapi/v1/brand/msgbase/v2/update
* Content-Type: application/json; charset=utf-8

**Request**

<table data-header-hidden><thead><tr><th width="220" align="center"></th><th width="150" align="center"></th><th width="150" align="center"></th><th width="293" align="center"></th></tr></thead><tbody><tr><td align="center"><strong>키</strong></td><td align="center"><strong>타입</strong></td><td align="center"><strong>필수</strong></td><td align="center"><strong>설명</strong></td></tr><tr><td align="center">brandId</td><td align="center">String</td><td align="center">O</td><td align="center">BizCenter 에서 생성한 브랜드 ID</td></tr><tr><td align="center">messagebaseId</td><td align="center">String</td><td align="center">O</td><td align="center">메시지베이스 ID</td></tr><tr><td align="center">messagebaseformId</td><td align="center">String</td><td align="center">O</td><td align="center"><p>메시지베이스 폼 ID</p><p>(정규식패턴: ^[0-9A-Za-z]{1,10}$)</p></td></tr><tr><td align="center">tmpltName</td><td align="center">String</td><td align="center">O</td><td align="center">메시지베이스 명</td></tr><tr><td align="center">body</td><td align="center">Array</td><td align="center">O</td><td align="center">*<strong>BODY</strong> 참조</td></tr><tr><td align="center">buttons</td><td align="center">Array</td><td align="center">X</td><td align="center"><p>메시지에 삽입할 버튼정보</p><p>* <strong>BUTTONS</strong> 참조</p></td></tr></tbody></table>

**Response**

<table data-header-hidden><thead><tr><th width="150" align="center"></th><th width="158.98765432098767" align="center"></th><th width="150" align="center"></th><th width="276" align="center"></th></tr></thead><tbody><tr><td align="center"><strong>키</strong></td><td align="center"><strong>-</strong></td><td align="center"><strong>타입</strong></td><td align="center"><strong>설명</strong></td></tr><tr><td align="center">code</td><td align="center"></td><td align="center">String</td><td align="center">결과 코드</td></tr><tr><td align="center">message</td><td align="center"></td><td align="center">String</td><td align="center">실패 시 결과 메시지</td></tr><tr><td align="center">data</td><td align="center"></td><td align="center"></td><td align="center">성공 시 데이터</td></tr><tr><td align="center"></td><td align="center">messagebaseId</td><td align="center">String</td><td align="center">메시지베이스 ID</td></tr></tbody></table>

## **BODY**

* messagebaseform JSON의 ROOT.params\[n-1] object의 type 이 file, string 인 경우,                              각 속성에 맞는 데이터 Object를 사용하여 템플릿을 구성합니다.&#x20;
* messageabseform JSON의 ROOT.params\[n-1].isMandatory 가 true 이면 템플릿 등록을 위해 필수로 등록해야 하는 요소이므로 반드시 데이터를 설정해야 템플릿 등록이 가능합니다.&#x20;
* 변수 mTitleMedia, itemMedia 에 사용할 이미지는 브랜드 로고(logo) 등록 후 발급된 fileId를 지정해야 합니다.

<table data-header-hidden><thead><tr><th width="220" align="center"></th><th width="150" align="center"></th><th width="150" align="center"></th><th width="293" align="center"></th></tr></thead><tbody><tr><td align="center"><strong>키</strong></td><td align="center"><strong>타입</strong></td><td align="center"><strong>필수</strong></td><td align="center"><strong>설명</strong></td></tr><tr><td align="center">param</td><td align="center">String</td><td align="center">O</td><td align="center"><p></p><ol><li>ROOT.params[n-1].type == string messagebaseform JSON의 ROOT.params[n-1].param 과 동일한 값으로 템플릿 구성 Text의 표시 위치에 해당합니다.<br> ex) "description"</li><li>ROOT.params[n-1].type == file messagebaseform JSON의 ROOT.params[n-1].param 과 동일한 값으로 템플릿 구성 File(이미지)의 표시 위치에 해당합니다.</li></ol></td></tr><tr><td align="center">value</td><td align="center">String</td><td align="center">O</td><td align="center"><p></p><ol><li>ROOT.params[n-1].type == string 영역에 지정할 Text 형식에 맞게 입력해야 합니다.</li></ol><ul><li>messagebaseform의 ROOT.params[n-1].contentType이 title, description, cell 인 경우: 고정부와 변수부로 이루어진 문장</li><li>messagebaseform의 ROOT.params[n-1].contentType이 url인 경우: http(s)://로 시작하는 URL 입력</li></ul><ol start="2"><li>ROOT.params[n-1].type == file 템플릿에 지정할 File(이미지) - maapfile://{fileId} 형식으로 입력합니다.</li></ol></td></tr><tr><td align="center">decoration</td><td align="center">Object</td><td align="center">X</td><td align="center">StringObject에서 사용되는 text서식  *<strong>DECORATION</strong> 참조</td></tr><tr><td align="center">lineIndex</td><td align="center">Integer</td><td align="center">X</td><td align="center"><p>템플릿에 Line을 행별로 표시합니다. 현재는 스타일(Cell) 템플릿에서 Text 행 아래 삽입되며 총 9개까지 지원합니다. <br>lineIndex 값은 템플릿 내의 지정 위치 값을 의미 합니다. </p><p>예를 들어 lineIndex 2는 두번째 Text 행 아래 입니다. ex) 2</p></td></tr></tbody></table>

**DECORATION**\



<table data-header-hidden><thead><tr><th width="220" align="center"></th><th width="150" align="center"></th><th width="150" align="center"></th><th width="293" align="center"></th></tr></thead><tbody><tr><td align="center"><strong>키</strong></td><td align="center"><strong>타입</strong></td><td align="center"><strong>필수</strong></td><td align="center"><strong>설명</strong></td></tr><tr><td align="center">textSize</td><td align="center">String</td><td align="center">X</td><td align="center">글자 크기 지정시 사용합니다. 숫자 뒤에 단위 dp를 반드시 붙여서 입력하여야 합니다. ex) 16dp</td></tr><tr><td align="center">textAlignment</td><td align="center">String</td><td align="center">X</td><td align="center"><p></p><p>문장 정렬 지정시 사용합니다.<br>지원하는 정렬의 종류는 다음과 같습니다.</p><ul><li>textStart: 왼쪽 정렬</li><li>center: 중앙 정렬</li><li>textEnd: 오른쪽 정렬</li></ul></td></tr><tr><td align="center">textStyle</td><td align="center">String</td><td align="center">X</td><td align="center">문장의 글자를 굵게 표현할 때 사용합니다. ex) "bold"</td></tr><tr><td align="center">textColor</td><td align="center">String</td><td align="center">X</td><td align="center">문장의 글자 색상을 지정한 색상 값으로 설정합니다. - 색상코드 Hex 표현식 ex) "#232323"</td></tr><tr><td align="center">height</td><td align="center">String</td><td align="center">X</td><td align="center">Line의 굵기 지정시 사용합니다. 숫자 뒤에 단위 dp를 반드시 붙여서 입력하여야 합니다. ex) "0.3dp"</td></tr><tr><td align="center">background</td><td align="center">String</td><td align="center">X</td><td align="center"><p>Line 색상을 지정한 색상 값으로 설정합니다. - 색상코드 Hex 표현식 </p><p>ex) "#232323"</p></td></tr></tbody></table>

## BUTTONS

* 템플릿에 버튼을 설정하는 경우 지정합니다.                                                                                                         이통사 발송규격에서 제공되는 buttons와 동일한 사용 방식으로 템플릿에 표시되는 버튼을 지정할수 있습니다.&#x20;
* 이미지 템플릿 슬라이드형의 경우 buttons 배열 내 object가 각 카드에 해당하며, object 하위 suggestions 배열 내에 messagebaseform의 policyInfo.maxButtonCount 지정 숫자만큼 버튼을 등록할 수 있습니다.&#x20;

<table data-header-hidden><thead><tr><th width="149" align="center"></th><th width="234" align="center"></th><th width="293" align="center"></th></tr></thead><tbody><tr><td align="center"><strong>키</strong></td><td align="center"><strong>타입</strong></td><td align="center"><strong>설명</strong></td></tr><tr><td align="center">suggestions</td><td align="center">array of 'suggestions'</td><td align="center">*<strong>SUGGESTIONS</strong> 참조</td></tr></tbody></table>

## **SUGGESTIONS**

<table data-header-hidden><thead><tr><th width="149" align="center"></th><th width="234" align="center"></th><th width="293" align="center"></th></tr></thead><tbody><tr><td align="center"><strong>키</strong></td><td align="center"><strong>타입</strong></td><td align="center"><strong>설명</strong></td></tr><tr><td align="center">action</td><td align="center">json</td><td align="center">*<strong>ACTION</strong> 참조</td></tr></tbody></table>

## **ACTION**

* action의 displayText, postback을 제외한 action 하위 항목에 다음과 같이 변수부를 지정할 수 있습니다.&#x20;

<figure><img src=".gitbook/assets/rcs_action.png" alt=""><figcaption></figcaption></figure>

※ API 등록 시 각 Action 구분 별 <mark style="color:red;">**postback.data**</mark>를 반드시 삽입해서 등록해야 합니다.

ACTION 규격 Examples

<figure><img src=".gitbook/assets/ACTION예시.png" alt=""><figcaption></figcaption></figure>

### 메시지베이스 삭제

* 브랜드 내에서 지정된 메시지베이스를 삭제합니다.\
  메시지베이스 삭제는 승인상태에 따라 처리 여부가 결정됩니다. 한번 삭제된 메시지베이스는 복원이 불가능하며 동일한 ID로 생성할 수 없습니다.
* **POST** /rcsapi/v1/brand/msgbase/remove
* Content-Type: application/json; charset=utf-8

**Request**

<table data-header-hidden><thead><tr><th width="181" align="center"></th><th width="150" align="center"></th><th width="150" align="center"></th><th width="261" align="center"></th></tr></thead><tbody><tr><td align="center"><strong>키</strong></td><td align="center"><strong>타입</strong></td><td align="center"><strong>필수</strong></td><td align="center"><strong>설명</strong></td></tr><tr><td align="center">brandId</td><td align="center">String</td><td align="center">O</td><td align="center">BizCenter 에서 생성한 브랜드 ID</td></tr><tr><td align="center">messagebaseId</td><td align="center">String</td><td align="center">O</td><td align="center">메시지베이스 ID</td></tr></tbody></table>

**Response**

<table data-header-hidden><thead><tr><th width="150" align="center"></th><th width="153" align="center"></th><th width="150" align="center"></th><th width="276" align="center"></th></tr></thead><tbody><tr><td align="center"><strong>키</strong></td><td align="center"><strong>-</strong></td><td align="center"><strong>타입</strong></td><td align="center"><strong>설명</strong></td></tr><tr><td align="center">code</td><td align="center"></td><td align="center">String</td><td align="center">결과 코드</td></tr><tr><td align="center">message</td><td align="center"></td><td align="center">String</td><td align="center">실패 시 결과 메시지</td></tr><tr><td align="center">data</td><td align="center"></td><td align="center"></td><td align="center">성공 시 데이터</td></tr><tr><td align="center"></td><td align="center">messagebaseId</td><td align="center">String</td><td align="center">메시지베이스 ID</td></tr><tr><td align="center">pagination</td><td align="center"></td><td align="center"></td><td align="center"></td></tr><tr><td align="center"></td><td align="center">limit</td><td align="center">Integer</td><td align="center">조회 최대 건수<br>(기본:100, 최대:1000)</td></tr><tr><td align="center"></td><td align="center">offset</td><td align="center">Integer</td><td align="center">시작 offset 번호 (기본:0)</td></tr><tr><td align="center"></td><td align="center">total</td><td align="center">Integer</td><td align="center">총 개수</td></tr></tbody></table>

###

### 메시지베이스 목록 조회

* 브랜드에 등록된 메시지베이스 목록을 조회합니다.
* **GET** /rcsapi/v1/brand/msgbase/list
* Query Parameter

**Request**

<table data-header-hidden><thead><tr><th width="181" align="center"></th><th width="150" align="center"></th><th width="150" align="center"></th><th width="261" align="center"></th></tr></thead><tbody><tr><td align="center"><strong>키</strong></td><td align="center"><strong>타입</strong></td><td align="center"><strong>필수</strong></td><td align="center"><strong>설명</strong></td></tr><tr><td align="center">brandId</td><td align="center">String</td><td align="center">O</td><td align="center">BizCenter 에서 생성한 브랜드 ID</td></tr><tr><td align="center">limit</td><td align="center">Integer</td><td align="center">X</td><td align="center">조회 최대 건수<br>(기본 : 100, 최대 : 1000)</td></tr><tr><td align="center">offset</td><td align="center">Integer</td><td align="center">X</td><td align="center">시작 offset 번호 (기본:0)</td></tr></tbody></table>



**Response**

<table data-header-hidden><thead><tr><th width="150" align="center"></th><th width="195.98765432098767" align="center"></th><th width="150" align="center"></th><th width="276" align="center"></th></tr></thead><tbody><tr><td align="center"><strong>키</strong></td><td align="center"><strong>-</strong></td><td align="center"><strong>타입</strong></td><td align="center"><strong>설명</strong></td></tr><tr><td align="center">code</td><td align="center"></td><td align="center">String</td><td align="center">결과 코드</td></tr><tr><td align="center">message</td><td align="center"></td><td align="center">String</td><td align="center">실패 시 결과 메시지</td></tr><tr><td align="center">data</td><td align="center"></td><td align="center"></td><td align="center">성공 시 데이터</td></tr><tr><td align="center"></td><td align="center">approvalDate</td><td align="center">String</td><td align="center">메시지베이스 승인 일시</td></tr><tr><td align="center"></td><td align="center">approvalReason</td><td align="center">String</td><td align="center">승인 사유</td></tr><tr><td align="center"></td><td align="center">approvalResult</td><td align="center">String</td><td align="center">승인 상태</td></tr><tr><td align="center"></td><td align="center">brandId</td><td align="center">String</td><td align="center">브랜드 ID</td></tr><tr><td align="center"></td><td align="center">groupId</td><td align="center">String</td><td align="center">그룹 ID</td></tr><tr><td align="center"></td><td align="center">messagebaseId</td><td align="center">String</td><td align="center">메시지베이스 ID</td></tr><tr><td align="center"></td><td align="center">messagebaseformId</td><td align="center">String</td><td align="center">메시지베이스 폼 ID</td></tr><tr><td align="center"></td><td align="center">registerDate</td><td align="center">String</td><td align="center">메시지베이스 등록 일시</td></tr><tr><td align="center"></td><td align="center">registerId</td><td align="center">String</td><td align="center">메시지베이스 등록 계정 ID</td></tr><tr><td align="center"></td><td align="center">status</td><td align="center">String</td><td align="center">메시지베이스 상태</td></tr><tr><td align="center"></td><td align="center">tmpltName</td><td align="center">String</td><td align="center">메시지베이스 명</td></tr><tr><td align="center"></td><td align="center">updateDate</td><td align="center">String</td><td align="center">메시지베이스 수정 일시</td></tr><tr><td align="center"></td><td align="center">updateId</td><td align="center">String</td><td align="center">메시지베이스 수정 계정 ID</td></tr><tr><td align="center">pagination</td><td align="center"></td><td align="center"></td><td align="center"></td></tr><tr><td align="center"></td><td align="center">limit</td><td align="center">Integer</td><td align="center">조회 최대 건수<br>(기본:100, 최대:1000)</td></tr><tr><td align="center"></td><td align="center">offset</td><td align="center">Integer</td><td align="center">시작 offset 번호 (기본:0)</td></tr><tr><td align="center"></td><td align="center">total</td><td align="center">Integer</td><td align="center">총 개수</td></tr></tbody></table>

###

### 메시지베이스 상세 조회

* 브랜드에 등록된 지정 메시지베이스의 상세 내역을 조회합니다.
* **GET** /rcsapi/v1/brand/msgbase/info
* Query Parameter



**Request**

<table data-header-hidden><thead><tr><th width="181" align="center"></th><th width="150" align="center"></th><th width="150" align="center"></th><th width="261" align="center"></th></tr></thead><tbody><tr><td align="center"><strong>키</strong></td><td align="center"><strong>타입</strong></td><td align="center"><strong>필수</strong></td><td align="center"><strong>설명</strong></td></tr><tr><td align="center">brandId</td><td align="center">String</td><td align="center">O</td><td align="center">BizCenter 에서 생성한 브랜드 ID</td></tr><tr><td align="center">messagebaseId</td><td align="center">String</td><td align="center">O</td><td align="center">메시지베이스 ID</td></tr></tbody></table>

**Response**

<table data-header-hidden><thead><tr><th width="150" align="center"></th><th width="195.98765432098767" align="center"></th><th width="150" align="center"></th><th width="276" align="center"></th></tr></thead><tbody><tr><td align="center"><strong>키</strong></td><td align="center"><strong>-</strong></td><td align="center"><strong>타입</strong></td><td align="center"><strong>설명</strong></td></tr><tr><td align="center">code</td><td align="center"></td><td align="center">String</td><td align="center">결과 코드</td></tr><tr><td align="center">message</td><td align="center"></td><td align="center">String</td><td align="center">실패 시 결과 메시지</td></tr><tr><td align="center">data</td><td align="center"></td><td align="center"></td><td align="center">성공 시 데이터</td></tr><tr><td align="center"></td><td align="center">agecyId</td><td align="center">String</td><td align="center"></td></tr><tr><td align="center"></td><td align="center">approvalDate</td><td align="center">String</td><td align="center">메시지베이스 승인 일시</td></tr><tr><td align="center"></td><td align="center">approvalReason</td><td align="center">String</td><td align="center">승인 사유</td></tr><tr><td align="center"></td><td align="center">approvalResult</td><td align="center">String</td><td align="center"><p>승인 상태<br>(ACT : 저장, RDY : 승인대기, </p><p>STT : 검수시작, REJ : 반려, </p><p>COM : 검수완료, APR : 승인완료,</p><p>RDM : 승인대기(수정),</p><p> STM : 검수시작(수정), </p><p>RJM : 반려(수정), </p><p>ISM : 검수완료(수정))</p></td></tr><tr><td align="center"></td><td align="center">attribute</td><td align="center">Array</td><td align="center"></td></tr><tr><td align="center"></td><td align="center">brandId</td><td align="center">String</td><td align="center">브랜드 ID</td></tr><tr><td align="center"></td><td align="center">cardType</td><td align="center">String</td><td align="center">카드 종류 (Cell, Description, Free)</td></tr><tr><td align="center"></td><td align="center">formattedString</td><td align="center">Object</td><td align="center">메시지베이스 포맷 </td></tr><tr><td align="center"></td><td align="center">groupId</td><td align="center">String</td><td align="center">그룹 ID</td></tr><tr><td align="center"></td><td align="center">guideInfo</td><td align="center">Object</td><td align="center"></td></tr><tr><td align="center"></td><td align="center">inputText</td><td align="center">String</td><td align="center"></td></tr><tr><td align="center"></td><td align="center">messagebaseId</td><td align="center">String</td><td align="center">메시지베이스 ID</td></tr><tr><td align="center"></td><td align="center">messagebaseformId</td><td align="center">String</td><td align="center">메시지베이스 폼 ID</td></tr><tr><td align="center"></td><td align="center">params</td><td align="center">Array</td><td align="center"></td></tr><tr><td align="center"></td><td align="center">policyInfo</td><td align="center">Object</td><td align="center"></td></tr><tr><td align="center"></td><td align="center">registerDate</td><td align="center">String</td><td align="center">메시지베이스 등록 일시</td></tr><tr><td align="center"></td><td align="center">registerId</td><td align="center">String</td><td align="center">메시지베이스 등록 계정 ID</td></tr><tr><td align="center"></td><td align="center">spec</td><td align="center">String</td><td align="center"></td></tr><tr><td align="center"></td><td align="center">status</td><td align="center">String</td><td align="center">메시지베이스 상태</td></tr><tr><td align="center"></td><td align="center">tmpltName</td><td align="center">String</td><td align="center">메시지베이스 명</td></tr><tr><td align="center"></td><td align="center">updateDate</td><td align="center">String</td><td align="center">메시지베이스 수정 일시</td></tr><tr><td align="center"></td><td align="center">updateId</td><td align="center">String</td><td align="center">메시지베이스 수정 계정 ID</td></tr><tr><td align="center">pagination</td><td align="center"></td><td align="center"></td><td align="center"></td></tr><tr><td align="center"></td><td align="center">limit</td><td align="center">Integer</td><td align="center">조회 최대 건수<br>(기본:100, 최대:1000)</td></tr><tr><td align="center"></td><td align="center">offset</td><td align="center">Integer</td><td align="center">시작 offset 번호 (기본:0)</td></tr><tr><td align="center"></td><td align="center">total</td><td align="center">Integer</td><td align="center">총 개수</td></tr></tbody></table>



### 메시지베이스 양식 목록 조회

* 오픈리치카드 템플릿 작성이 필요한 경우 조회된 템플릿 양식 ID를 이용하여 **messagebaseform** 세부정보를 조회합니다.
* **GET** /rcsapi/v1/msgbaseform/list
* Query Parameter

**Request**

<table data-header-hidden><thead><tr><th width="181" align="center"></th><th width="150" align="center"></th><th width="150" align="center"></th><th width="261" align="center"></th></tr></thead><tbody><tr><td align="center"><strong>키</strong></td><td align="center"><strong>타입</strong></td><td align="center"><strong>필수</strong></td><td align="center"><strong>설명</strong></td></tr><tr><td align="center">bizCategory</td><td align="center">String</td><td align="center">X</td><td align="center">유형 그룹<br>(Description, Cell 에서만 사용 / 일반, 금용, 교통 등)</td></tr><tr><td align="center">bizCondition</td><td align="center">String</td><td align="center">X</td><td align="center">대상 업태 (기본: all)</td></tr><tr><td align="center">bizService</td><td align="center">String</td><td align="center">X</td><td align="center">유형 (승인, 입금, 출금 등)</td></tr><tr><td align="center">cardType</td><td align="center">String</td><td align="center">X</td><td align="center">카드 종류<br>(Cell, Description, Free)</td></tr><tr><td align="center">limit</td><td align="center">Integer</td><td align="center">X</td><td align="center">조회 최대 건수<br>(기본 : 100, 최대 : 1000)</td></tr><tr><td align="center">offset</td><td align="center">Integer</td><td align="center">X</td><td align="center">시작 offset 번호 (기본:0)</td></tr></tbody></table>

**Response**

<table data-header-hidden><thead><tr><th width="150" align="center"></th><th width="190.98765432098767" align="center"></th><th width="150" align="center"></th><th width="276" align="center"></th></tr></thead><tbody><tr><td align="center"><strong>키</strong></td><td align="center"><strong>-</strong></td><td align="center"><strong>타입</strong></td><td align="center"><strong>설명</strong></td></tr><tr><td align="center">code</td><td align="center"></td><td align="center">String</td><td align="center">결과 코드</td></tr><tr><td align="center">message</td><td align="center"></td><td align="center">String</td><td align="center">실패 시 결과 메시지</td></tr><tr><td align="center">data</td><td align="center"></td><td align="center"></td><td align="center">성공 시 데이터</td></tr><tr><td align="center"></td><td align="center">bizCategory</td><td align="center">String</td><td align="center">유형 그룹<br>(Description, Cell 에서만 사용 / 일반, 금용, 교통 등)</td></tr><tr><td align="center"></td><td align="center">bizCondition</td><td align="center">Array</td><td align="center">대상 업태 (기본: all)</td></tr><tr><td align="center"></td><td align="center">bizService</td><td align="center">String</td><td align="center">유형 (승인, 입금, 출금 등)</td></tr><tr><td align="center"></td><td align="center">cardType</td><td align="center">String</td><td align="center">카드 종류 (Cell, Description, Free)</td></tr><tr><td align="center"></td><td align="center">formName</td><td align="center">String</td><td align="center">폼 명</td></tr><tr><td align="center"></td><td align="center">messagebaseformId</td><td align="center">String</td><td align="center">메시지베이스 폼 ID</td></tr><tr><td align="center"></td><td align="center">registerDate</td><td align="center">String</td><td align="center">등록 일자</td></tr><tr><td align="center"></td><td align="center">updateDate</td><td align="center">String</td><td align="center">수정 일자</td></tr><tr><td align="center">pagination</td><td align="center"></td><td align="center"></td><td align="center"></td></tr><tr><td align="center"></td><td align="center">limit</td><td align="center">Integer</td><td align="center">조회 최대 건수<br>(기본:100, 최대:1000)</td></tr><tr><td align="center"></td><td align="center">offset</td><td align="center">Integer</td><td align="center">시작 offset 번호 (기본:0)</td></tr><tr><td align="center"></td><td align="center">total</td><td align="center">Integer</td><td align="center">총 개수</td></tr></tbody></table>

###

### 메시지베이스 유형 상세 조회

* 메시지베이스 유형의 상세 내용을 조회합니다.\
  **formattedString** 을 이용하여 원하는 브랜드용 메시지베이스를 작성할 수 있습니다.
* **GET** /rcsapi/v1/msgbaseform/info
* Query Parameter

**Request**

<table data-header-hidden><thead><tr><th width="221.46361185983827" align="center"></th><th width="150" align="center"></th><th width="150" align="center"></th><th width="193" align="center"></th></tr></thead><tbody><tr><td align="center"><strong>키</strong></td><td align="center"><strong>타입</strong></td><td align="center"><strong>필수</strong></td><td align="center"><strong>설명</strong></td></tr><tr><td align="center">messagebaseformId</td><td align="center">String</td><td align="center">O</td><td align="center">메시지베이스 ID</td></tr></tbody></table>

**Response**

<table data-header-hidden><thead><tr><th width="150" align="center"></th><th width="190.98765432098767" align="center"></th><th width="150" align="center"></th><th width="276" align="center"></th></tr></thead><tbody><tr><td align="center"><strong>키</strong></td><td align="center"><strong>-</strong></td><td align="center"><strong>타입</strong></td><td align="center"><strong>설명</strong></td></tr><tr><td align="center">code</td><td align="center"></td><td align="center">String</td><td align="center">결과 코드</td></tr><tr><td align="center">message</td><td align="center"></td><td align="center">String</td><td align="center">실패 시 결과 메시지</td></tr><tr><td align="center">data</td><td align="center"></td><td align="center"></td><td align="center">성공 시 데이터</td></tr><tr><td align="center"></td><td align="center">bizCategory</td><td align="center">String</td><td align="center">유형 그룹<br>(Description, Cell 에서만 사용 / 일반, 금용, 교통 등)</td></tr><tr><td align="center"></td><td align="center">bizCondition</td><td align="center">Array</td><td align="center">대상 업태 (기본: all)</td></tr><tr><td align="center"></td><td align="center">bizService</td><td align="center">String</td><td align="center">유형 (승인, 입금, 출금 등)</td></tr><tr><td align="center"></td><td align="center">cardType</td><td align="center">String</td><td align="center">카드 종류 (Cell, Description, Free)</td></tr><tr><td align="center"></td><td align="center">formName</td><td align="center">String</td><td align="center">폼 명</td></tr><tr><td align="center"></td><td align="center">formattedString</td><td align="center">Object</td><td align="center">메시지베이스 포맷</td></tr><tr><td align="center"></td><td align="center">guideInfo</td><td align="center">Object</td><td align="center"></td></tr><tr><td align="center"></td><td align="center">mediaUrl</td><td align="center">Array</td><td align="center"></td></tr><tr><td align="center"></td><td align="center">messagebaseformId</td><td align="center">String</td><td align="center">메시지베이스 폼 ID</td></tr><tr><td align="center"></td><td align="center">params</td><td align="center">Array</td><td align="center"></td></tr><tr><td align="center"></td><td align="center">policyInfo</td><td align="center">Object</td><td align="center"></td></tr><tr><td align="center"></td><td align="center">productCode</td><td align="center">String</td><td align="center"></td></tr><tr><td align="center"></td><td align="center">spec</td><td align="center">String</td><td align="center"></td></tr><tr><td align="center"></td><td align="center">registerDate</td><td align="center">String</td><td align="center">등록 일자</td></tr><tr><td align="center"></td><td align="center">updateDate</td><td align="center">String</td><td align="center">수정 일자</td></tr><tr><td align="center">pagination</td><td align="center"></td><td align="center"></td><td align="center"></td></tr><tr><td align="center"></td><td align="center">limit</td><td align="center">Integer</td><td align="center">조회 최대 건수<br>(기본:100, 최대:1000)</td></tr><tr><td align="center"></td><td align="center">offset</td><td align="center">Integer</td><td align="center">시작 offset 번호 (기본:0)</td></tr><tr><td align="center"></td><td align="center">total</td><td align="center">Integer</td><td align="center">총 개수</td></tr></tbody></table>

###

### 이통사 제공 메시지베이스 목록 조회

* 리치카드 규격의 SMS, LMS, MMS 용 메시지베이스를 조회합니다. (현재 리치카드는 비즈니스 유형 별로 제공되는 항목은 없습니다.)
* **GET** /rcsapi/v1/msgbase/common/list
* Query Parameter



**Request**

<table data-header-hidden><thead><tr><th width="181" align="center"></th><th width="150" align="center"></th><th width="150" align="center"></th><th width="261" align="center"></th></tr></thead><tbody><tr><td align="center"><strong>키</strong></td><td align="center"><strong>타입</strong></td><td align="center"><strong>필수</strong></td><td align="center"><strong>설명</strong></td></tr><tr><td align="center">cardType</td><td align="center">String</td><td align="center">X</td><td align="center">카드 종류 <br>(standalone, standalone media top, standalone horizontal, carousel medium, carousel small)</td></tr><tr><td align="center">productCode</td><td align="center">String</td><td align="center">X</td><td align="center">상품 코드 (sms, lms, mms)</td></tr><tr><td align="center">limit</td><td align="center">Integer</td><td align="center">X</td><td align="center">조회 최대 건수<br>(기본 : 100, 최대 : 1000)</td></tr><tr><td align="center">offset</td><td align="center">Integer</td><td align="center">X</td><td align="center">시작 offset 번호 (기본:0)</td></tr></tbody></table>

**Response**

<table data-header-hidden><thead><tr><th width="150" align="center"></th><th width="195.98765432098767" align="center"></th><th width="150" align="center"></th><th width="276" align="center"></th></tr></thead><tbody><tr><td align="center"><strong>키</strong></td><td align="center"><strong>-</strong></td><td align="center"><strong>타입</strong></td><td align="center"><strong>설명</strong></td></tr><tr><td align="center">code</td><td align="center"></td><td align="center">String</td><td align="center">결과 코드</td></tr><tr><td align="center">message</td><td align="center"></td><td align="center">String</td><td align="center">실패 시 결과 메시지</td></tr><tr><td align="center">data</td><td align="center"></td><td align="center"></td><td align="center">성공 시 데이터</td></tr><tr><td align="center"></td><td align="center">approvalDate</td><td align="center">String</td><td align="center">메시지베이스 승인 일시</td></tr><tr><td align="center"></td><td align="center">approvalReason</td><td align="center">String</td><td align="center">승인 사유</td></tr><tr><td align="center"></td><td align="center">approvalResult</td><td align="center">String</td><td align="center">승인 상태</td></tr><tr><td align="center"></td><td align="center">brandId</td><td align="center">String</td><td align="center">브랜드 ID</td></tr><tr><td align="center"></td><td align="center">groupId</td><td align="center">String</td><td align="center">그룹 ID</td></tr><tr><td align="center"></td><td align="center">messagebaseId</td><td align="center">String</td><td align="center">메시지베이스 ID</td></tr><tr><td align="center"></td><td align="center">messagebaseformId</td><td align="center">String</td><td align="center">메시지베이스 폼 ID</td></tr><tr><td align="center"></td><td align="center">registerDate</td><td align="center">String</td><td align="center">메시지베이스 등록 일시</td></tr><tr><td align="center"></td><td align="center">registerId</td><td align="center">String</td><td align="center">메시지베이스 등록 계정 ID</td></tr><tr><td align="center"></td><td align="center">status</td><td align="center">String</td><td align="center">메시지베이스 상태</td></tr><tr><td align="center"></td><td align="center">tmpltName</td><td align="center">String</td><td align="center">메시지베이스 명</td></tr><tr><td align="center"></td><td align="center">updateDate</td><td align="center">String</td><td align="center">메시지베이스 수정 일시</td></tr><tr><td align="center"></td><td align="center">updateId</td><td align="center">String</td><td align="center">메시지베이스 수정 계정 ID</td></tr><tr><td align="center">pagination</td><td align="center"></td><td align="center"></td><td align="center"></td></tr><tr><td align="center"></td><td align="center">limit</td><td align="center">Integer</td><td align="center">조회 최대 건수<br>(기본:100, 최대:1000)</td></tr><tr><td align="center"></td><td align="center">offset</td><td align="center">Integer</td><td align="center">시작 offset 번호 (기본:0)</td></tr><tr><td align="center"></td><td align="center">total</td><td align="center">Integer</td><td align="center">총 개수</td></tr></tbody></table>

###

### 이통사 제공 메시지베이스 상세 조회

* 이통사가 기본 제공하는 메시지베이스의 상세 내용을 조회합니다.\
  리치카드 규격의 SMS, LMS, MMS 용 메시지베이스를 조회합니다. 비즈니스 유형에 따라 조회할 수 있습니다.
* GET /rcsapi/v1/msgbse/common/info
* Query Parameter



**Request**

<table data-header-hidden><thead><tr><th width="181" align="center"></th><th width="150" align="center"></th><th width="150" align="center"></th><th width="261" align="center"></th></tr></thead><tbody><tr><td align="center"><strong>키</strong></td><td align="center"><strong>타입</strong></td><td align="center"><strong>필수</strong></td><td align="center"><strong>설명</strong></td></tr><tr><td align="center">messagebaseId</td><td align="center">String</td><td align="center">O</td><td align="center">메시지베이스 ID</td></tr></tbody></table>

**Response**

<table data-header-hidden><thead><tr><th width="150" align="center"></th><th width="195.98765432098767" align="center"></th><th width="150" align="center"></th><th width="276" align="center"></th></tr></thead><tbody><tr><td align="center"><strong>키</strong></td><td align="center"><strong>-</strong></td><td align="center"><strong>타입</strong></td><td align="center"><strong>설명</strong></td></tr><tr><td align="center">code</td><td align="center"></td><td align="center">String</td><td align="center">결과 코드</td></tr><tr><td align="center">message</td><td align="center"></td><td align="center">String</td><td align="center">실패 시 결과 메시지</td></tr><tr><td align="center">data</td><td align="center"></td><td align="center"></td><td align="center">성공 시 데이터</td></tr><tr><td align="center"></td><td align="center">agecyId</td><td align="center">String</td><td align="center"></td></tr><tr><td align="center"></td><td align="center">approvalDate</td><td align="center">String</td><td align="center">메시지베이스 승인 일시</td></tr><tr><td align="center"></td><td align="center">approvalReason</td><td align="center">String</td><td align="center">승인 사유</td></tr><tr><td align="center"></td><td align="center">approvalResult</td><td align="center">String</td><td align="center">승인 상태</td></tr><tr><td align="center"></td><td align="center">attribute</td><td align="center">Array</td><td align="center"></td></tr><tr><td align="center"></td><td align="center">brandId</td><td align="center">String</td><td align="center">브랜드 ID</td></tr><tr><td align="center"></td><td align="center">cardType</td><td align="center">String</td><td align="center">카드 종류 (Cell, Description, Free)</td></tr><tr><td align="center"></td><td align="center">formattedString</td><td align="center">Object</td><td align="center">메시지베이스 포맷</td></tr><tr><td align="center"></td><td align="center">groupId</td><td align="center">String</td><td align="center">그룹 ID</td></tr><tr><td align="center"></td><td align="center">guideInfo</td><td align="center">Object</td><td align="center"></td></tr><tr><td align="center"></td><td align="center">inputText</td><td align="center">String</td><td align="center"></td></tr><tr><td align="center"></td><td align="center">messagebaseId</td><td align="center">String</td><td align="center">메시지베이스 ID</td></tr><tr><td align="center"></td><td align="center">messagebaseformId</td><td align="center">String</td><td align="center">메시지베이스 폼 ID</td></tr><tr><td align="center"></td><td align="center">params</td><td align="center">Array</td><td align="center"></td></tr><tr><td align="center"></td><td align="center">policyInfo</td><td align="center">Object</td><td align="center"></td></tr><tr><td align="center"></td><td align="center">registerDate</td><td align="center">String</td><td align="center">메시지베이스 등록 일시</td></tr><tr><td align="center"></td><td align="center">registerId</td><td align="center">String</td><td align="center">메시지베이스 등록 계정 ID</td></tr><tr><td align="center"></td><td align="center">spec</td><td align="center">String</td><td align="center"></td></tr><tr><td align="center"></td><td align="center">status</td><td align="center">String</td><td align="center">메시지베이스 상태</td></tr><tr><td align="center"></td><td align="center">tmpltName</td><td align="center">String</td><td align="center">메시지베이스 명</td></tr><tr><td align="center"></td><td align="center">updateDate</td><td align="center">String</td><td align="center">메시지베이스 수정 일시</td></tr><tr><td align="center"></td><td align="center">updateId</td><td align="center">String</td><td align="center">메시지베이스 수정 계정 ID</td></tr><tr><td align="center">pagination</td><td align="center"></td><td align="center"></td><td align="center"></td></tr><tr><td align="center"></td><td align="center">limit</td><td align="center">Integer</td><td align="center">조회 최대 건수<br>(기본:100, 최대:1000)</td></tr><tr><td align="center"></td><td align="center">offset</td><td align="center">Integer</td><td align="center">시작 offset 번호 (기본:0)</td></tr><tr><td align="center"></td><td align="center">total</td><td align="center">Integer</td><td align="center">총 개수</td></tr></tbody></table>
