# 비즈뿌리오 RCS API 소개

### 개요

* 본 문서는 Url 호출 방식으로 RCS 메시지 발송을 위해 필요한 브랜드, 챗봇, 파일, 메세지베이스의 정보를 조회 및 업데이트를 할 수 있도록 연동 규격을 정의한 API 문서입니다.
* 본 문서는 Https 프로토콜을 통해 데이터를 Json 형식으로 가공하고 POST,GET method 를 사용하여 전송합니다.
* Json 형식의 결과 데이터를 Parsing 하여 처리할 수 있음을 전제로 작성되었습니다.



### 용어 정의

* 브랜드(Brand) : 메시지 발송 서비스 이용 고객이 등록한 기업 정보
* 챗봇(Chatbot) : 브랜드의 발송 프로필
* 메시지베이스(Messagebase) : 브랜드가 발송할 수 있는 메시지의 형태 및 규격
* 메시지베이스폼(MessagebaseForm) : 메시지베이스의 기본 틀이 되는 발송 메시지 포맷



### 선결 조건&#x20;

1. RCS API 를 사용하기 위해서는 아래의 조건이 선결되어야 합니다.

* &#x20;사용자는 등록한 비즈뿌리오 계정 정보로 메세지 송에 필요한 **bizId, apiKey** 를 요청하고, 이 키를 메세지 전송 시스템에 적용해야 합니다.
* 브랜드를 등록하는 것은 BizCenter 에서만 가능합니다.
* BizCenter URL : [https://www.rcsbizcenter.com/](https://www.rcsbizcenter.com/)
* 인증은 HTTP Authorization 헤더와 Bearer 인증 스킴을 사용하며, 인증 토큰(accessToken)은 API 를 통해 발행합니다. (예: `Authorization: Bearer {accessToken}`)
