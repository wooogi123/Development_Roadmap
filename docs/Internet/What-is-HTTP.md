## HTTP는 무엇일까요?

**Summary (요약)**
- **HTTP (HyperText Transfer Protocol)** 은 웹상에서 HTML 문서와 같은 정보를 주고받을 수 있는 프로토콜입니다.
- 클라이언트와 서버 사이에서 이루어지는 요청/응답 (Request/Response) 프로토콜입니다.
- 1990년대 초에 설계된 HTTP는 거듭하여 발전해온 확장 가능한 프로토콜입니다.
- **HTTP**는 애플리케이션 계층의 프로토콜로, 신뢰 가능한 전송 프로토콜이라면 이론상 무엇이든 사용할 수 있으나 주로 TCP 또는 암호화된 TCP인 TLS를 통해 전송합니다.
- **HTTP**의 확장성 덕분에 HTML 문서 뿐만 아니라 이미지, 비디오, HTML Form 결과와 같은 내용을 서버로 POST 하기 위해서도 사용할 수 있습니다.

**HTTP 기반 시스템의 구성요소**
- **HTTP**는 클라이언트-서버 프로토콜입니다.
- 요청은 하나의 개체인 User-Agent (또는 프록시)에 의해 전송됩니다.
- User-Agent는 대부분의 경우 브라우저이지만, 크롤링 봇과 같이 무엇이던지 될 수 있습니다.
- 각각의 요청들은 서버로 보내지며, 서버는 요청을 처리하고 **Response**라고 불리는 응답을 제공합니다.
- 이 요청과 응답 사이에는 여러 개체들이 있는데, 예를 들어 다양한 작업을 수행하고 게이트웨이 또는 캐시 역할을 하는 **프록시** 등이 있습니다.
  ![What-is-HTTP-1](https://github.com/wooogi123/Development_Roadmap/blob/master/docs/Internet/images/What-is-HTTP-1.png)
- 실제로는 브라우저와 요청을 처리하는 서버 사이에 많은 컴퓨터들이 존재합니다 - 라우터, 모뎀 등이 있습니다.
- 웹의 계층적 설계 덕분에 이 컴퓨터들은 네트워크와 전송 계층 안으로 숨겨집니다.
- **HTTP**는 애플리케이션 계층의 최상위에 있습니다.


### Reference
  [What is HTTP?](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview)
