네트워크 통신의 종류
소켓방식의 연결성 통신 : TCP/UDP
프로토콜을 이용한 비연결성 통신 : HTTP, HTTPS, SMTP
 

소켓 방식의 연결 지향 통신
소켓을 이용한 네트워크 통신은 보통 저수준(Low-level) 통신을 통하여 구현된다. 소켓은 전구가 결합하는 개념을 따온것이다. 앱과 서버가 연결되면 한쪽에서 연결을 끊기 전까지는 계속 연결이 유지되기 때문에 연결 지향 통신이라고 한다.

따라서 연결을 계속 유지하기 위해서 네트워크 대역도 많이 소모되고, 서버 부하도 크기 때문에 모바일 서비스에서는 메신저, 화상통화, RPG 게임 등에서 주로 사용된다.

TCP는 속도는 느리지만, 데이터 유실을 방지하고 완전한 전송을 보장한다.

UDP는 속도는 빠르지만, 데이터의 완전한 전송을 보장하지 않는다.

 

 

비연결 지향 통신
비연결성 통신은 프로토콜을 사용하여 메시지를 주고받는 방식을 말한다. 대표적으로 HTTP/HTTPS 프로토콜이 있으며, 웹 서비스에 주로 사용된다. 소켓 통신과는 달리 요청이 들어오면 응답을 보낸후 바로 연결을 끊는다. 따라서 비연결성 이라고 해서 연결이 아예 없는게 아니라, 요청과 응답을 완료한 후에 연결을 유지하지 않을 뿐이다.

연결을 유지하지 않기 때문에 소켓 방싱게 비해 상대적으로 속도가 느리지만, 네트워크 대역 소모를 많이 감소시킬 수 있고, 서버 부하도 낮출 수 있다.

 

 

웹 서비스 (Web service)
일반적으로 HTML을 이용하는 웹 페이지도 HTTP/HTTPS 프로토콜을 사용한다. 하지만 데이터만 주고 받을 수 있도록 설계된 모듈을 말한다. 웹 서비스에는 SOAP 방식과 Restful방식이 있다.

 

 

SOAP (Simple Object Access Protocol)
XML 형태의 메시지를 주고받도록 구현된 프로토콜을 말한다.
SOAP 메시지의 구조는 Envelop / Header / Body 세가지로 구성된다.
SOAP의 표준 프로토콜은 HTTP이지만, 다른 프로토콜도 다양하게 사용 가능하다.
매우 간단하고 확장이 용이하다.
플랫폼 독립적인 통신이기 때문에 서로 다른 플랫폼 간에도 데이터 통신이 편리하다.
프로그래밍 언어에 제약을 받지 않는다.
 

XML (Extensible Markup Language)
SOAP에도 , RESTful API에도 모두 사용될 수 있다. XML은 다목적 마크업 언어이며, HTML의 한계를 극복하기 위한 목적으로 만들어졌다. 그래서 HTML처럼 태그(Tag)형태의 마크업 구조를 가진다. 태그는 데이터들의 계층구조를 나타낸다.

iOS에서는 XML을 파싱하기 위해 XMLParser라는 파서 모듈을 제공하고있다.



 

RESTful(Representational State Transfer)
REST는 실질적인 네트워크 프로토콜을 말한다기 보다는, 네트워크 자원을 정의하고 자원에 대한 주소 관리방법을 의미한다.
SOAP와는 다르게 Envelope/Header/Body와 같이 별도의 규약 없이 주고받으면 된다.
URI 는 정보의 분류체계만 포함되어야 하며, 동작에 대한 명세는 포함하지 않는것이 좋다.

RESTful API에서의 HTTP Method

URI에 동작에 관한 명세를 하지 않기 때문에 헤더부분에 HTTP Method를 사용하여 동작을 정의하게 된다.

 

JSON (JavaScript Object Notation)
XML은 태그와 계층구조를 가져야하기 때문에 텍스트의 양도 많아지게 되고 지켜야할 규약들도 있다. 이러한 단점을 극복하기 위해 JSON이라는 경량 데이터 교환 형식이 만들어졌다. 원래는 자바스크립트의 객체 속성을 표현하기 위해 사용되었지만, 대부분의 언어에서 JSON포맷을 지원하게 되었고, 대표적인 텍스트 기반 데이터 구조로 자리잡게되었다.

JSON객체는 key와 Value가 한쌍이 되는 구조를 가지는 딕셔너리형태이다.
문자열인 경우 쿼우팅(Quoting)이 필요하다. (따옴표로 감싸주기) , 정수나 실수, bool 타입은 필요 없음
대괄호 [ ]를 사용하여 array를 사용할 수 있다.
JSON object 내부에 또다른 object를 넣을 수도있다. { }
 


{
    "version": "https://jsonfeed.org/version/1",
    "title": "My Example Feed",
    "home_page_url": "https://example.org/",
    "feed_url": "https://example.org/feed.json",
    "items": [
        {
            "id": "2",
            "content_text": "This is a second item.",
            "url": "https://example.org/second-item"
        },
        {
            "id": "1",
            "content_html": "<p>Hello, world!</p>",
            "url": "https://example.org/initial-post"
        }
    ]
}
 

 

NSDictionary / NSMutableDictionary
Swift에서는 하나의 딕셔너리안에 같은 타입들의 요소만 들어갈 수 있다. 따라서 Foundation 프레임워크에 정의되어있는 NSDictionary NSMutableDictionary 자료형을 사용하면 데이터 타입에 대한 손실없이 사용할 수 있다.

(Mutable이 붙은 타입은 수정이 가능하다는 뜻이다.)
