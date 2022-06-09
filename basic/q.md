### 브라우저의 렌더링 원리?

브라우저 종류에 따라 블링크,웹킷,게코같은 렌더링 엔진을 통해 <br />
html을 파싱후 dom트리를 구축합니다. <br />
두번째로 css를 파싱하여 cssom트리를 구축하고, <br />
js를 실행합니다. 그후 dom 과 cssom을 조합하여 렌더트리를 구축합니다. <br />
뷰포트기반으로 렌더트리의 각 노드가 가지는 위치와 크기를 계산하며 이것을 Layout이라고 부릅니다. <br />
계산된 위치/크기 기반으로 화면을 그리는 paint단계로 이루어지며 이러한 과정을 CRP라고 합니다. <br />
언급한 자원들을 픽셀로 변화하는 과정입니다. <br />

### 주소창에 구글을 입력하면 일어나는 일?

사용자가 브라우저를 통해 구글을 검색하면 url 주소 중 도메인 네임 부분을 Dns서버에서 검색합니다. <br />
dns서버에서 해당 도메인 네임에 해당하는 ip주소를 찾아 사용자가 입력한 url정보와 함께 브라우저에 전달합니다. <br />
브라우저는 http프로토콜을 사용해 요청 메시지를 생성하고 http 요청 메시지는 tcp/ip 프로토콜을 사용해 서버로 전송합니다. <br />
서버는 response 메시지를 생성해 다시 브라우저에 데이터를 전송합니다. <br />
브라우저는 응답을 받아 파싱해 화면에 렌더링 합니다. <br />

- dns: www.naver.com과 같은 사람이 읽을수 있는 도메인이름 <br />

- url: 통합 자원 지시자로서 인터넷의 리소스를 가리키는 표준 명칭 <br />

- http: tcp기반으로 클라이언트와 서버사이 이루어지는 요청/응답 프로토콜. 요청이 있으면 응답이 있어야한다. <br />

- 프로토콜: 서버와 클라언트 통신을 위한 약속을 정의해 둔것. <br />

- tcp: 두개의 호스트를 연결하고 데이터 스트림을 교환하게 해주는 네트워크 프로토콜. 데이터를 어떻게 보내고 제어할것인지 정의할것지를 정합니다. <br />

### 호이스팅

변수 및 함수 선언문이 스코프 내 최상단으로 끌어올려지는 현상을 말한다.<br />

- 인터프리팅: 컴파일과 다르게 소스코드를 한번에 읽어서 번역하지 않고, 런타임 상태에서 소스코드를 한줄한줄 번역하면서 프로그램을 구동하는 방식. 중간 코드로 번역되며 <br />
또 다시 다른 프로그램을 통해 기계어로 번역되어 실행된다.