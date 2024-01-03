# 대행사 전용

### 파일 등록

* RCS 포토 발송에 사용할 미디어 파일을 등록합니다.
* &#x20;**POST** /rcsapi/v1/agency/file
* **Content-Type :** multipart/form-data

**Request**

<table><thead><tr><th width="160">키</th><th width="108">타입</th><th width="72">필수</th><th>설명</th></tr></thead><tbody><tr><td>file</td><td>File</td><td>O</td><td>업로드 파일</td></tr><tr><td>field</td><td>String</td><td>O</td><td>파일 ID (64byte)</td></tr><tr><td>mimeType</td><td>String</td><td>O</td><td><p>Mime type</p><p>(image/jpeg, image/png, image/gif, image/bmp)</p></td></tr><tr><td>usageType</td><td>String</td><td>O</td><td>사용 타입 (send)</td></tr></tbody></table>

**Response**

<table><thead><tr><th width="160">키</th><th width="108">타입</th><th>설명</th></tr></thead><tbody><tr><td>code</td><td>String</td><td>결과 코드</td></tr><tr><td>message</td><td>String</td><td>실패 시 결과 메시지</td></tr><tr><td>data</td><td></td><td>파일 상세 조회 (<a href="file.md#undefined-1">파일 상세조회 반환 값</a> 참조)</td></tr><tr><td>pagination</td><td></td><td>페이지 상세 조회 (<a href="file.md#undefined-1">파일 상세조회 반환 값</a> 참조)</td></tr></tbody></table>
