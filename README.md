## 알고리즘 , 자료구조

1. DFS와 BFS에 대해 설명해주세요.

- DFS와 BFS는 그래프의 모든 정점을 탐색하는 알고리즘입니다.
- DFS는 특정 분기를 끝까지 타고 들어가고, 이후 다른 분기를 이어서 타고 들어가는 특징을 갖고 있으며, 재귀(재귀도 어짜피 스택메모리의 스택구조를 활용)나 스택자료구조를 이용하여 구현합니다.
- DFS는 특히 모든 조합에서 특정 조건을 만족하는 경우의 수를 구하는 백트래킹 기법이 필요한 문제에 사용됩니다.
- BFS는 특정 정점에서 가까운 레벨에 있는 노드들을 우선적으로 탐색하는 알고리즘입니다. 
- 큐를 사용하여 구현하며, 최초로 나온 해가 최적해임을 보장하는 특징을 갖고 있어, 최단거리를 구하는 문제에서 많이 사용됩니다.
- 메모리 사용측면에서는 DFS가 BFS보다 유리합니다.

2. UNION FIND에 대해 설명해주세요.

- UNION FIND 알고리즘은 서로소 집합을 만들기 위해 사용되는 알고리즘입니다.
- FIND 연산은 특정 원소가 소속된 집합이 어디인지 알려주는 연산이며, UNION 연산은 두개의 원소가 각각 소속된 집합을 합치는 연산입니다.
- FIND 연산은 내부적으로 parent배열을 참조하여, 재귀적으로 부모를 탐색해 자신이 속한 집합의 대표를 리턴합니다. 
- 최적화를 위해 FIND 연산에서 경로압축을 적용할 수 있으며, UNION 연산에서 트리깊이가 낮은쪽이 높은쪽에 추가되는 형태로 최적화를 진행할 수 있습니다.

![image](https://user-images.githubusercontent.com/49670068/120060325-1a10d100-c092-11eb-904b-4027b6d67c8d.png)

3. 퀵정렬에 대해 설명해보세요.

- 퀵정렬은 분할 정복 알고리즘 중 하나 입니다. 
- 배열의 가장 왼쪽값을 피벗으로 삼고, 피벗을 기준으로 왼쪽에서는 피벗보다 작은 값을 오른쪽에는 피벗보다 큰값을 N번의 비교연산을 통해 위치시킵니다. 
- 그리고 피벗을 기준으로 왼쪽과 오른쪽의 배열값들을 재귀적으로 분할,비교해나가는 과정을 배열의 크기가 1 또는 0 될때까지 반복합니다.
- 퀵정렬은 카운팅 정렬을 제외하면, 평균시간복잡도가 NlogN으로 가장 빠른 정렬 알고리즘으로 알려져 있습니다. 허나 최악의 경우에는 N^2입니다.
- NlogN인 이유는 반반씩 분할해 나간다면 분할횟수는 logN번 그리고 각 횟수에서 N번의 비교연산이 발생하므로 N*logN입니다.
- 합병정렬은 추가적인 배열공간을 생성하는 오버헤드가 발생해서 평균적인 경우 퀵정렬보다는 느립니다.

4. 합병정렬에 대해 설명해보세요.

- 합병정렬은 분할 정복 알고리즘 중 하나입니다.
- 재귀를 통해 배열의 크기가 1 또는 0이 될때까지 나눕니다. 그리고 나눈 배열들을 임시배열에 다시 병합해 나가는 과정을 진행합니다.
- 최종적으로 임시배열에 있는 값들을 원본배열에 복사하여 정렬된 배열을 얻습니다.
- 반반씩 나누는 분할의 횟수는 logN번 수행되며, 병합과정에서 쪼개진 두배열의 값을 비교해가며 임시배열에 넣는 과정에서 N번의 연산이 발생합니다.
- 그리고 병합과정도 logN번 발생하는데, 시간복잡도에서는 계수를 제외하므로 NlogN의 시간복잡도가 발생합니다.

5. 힙정렬에 대해 설명해보세요.

- 힙정렬은 힙 자료구조를 이용하여 정렬하는 알고리즘입니다.
- 힙은 부모노드 값이 자식노드 값보다 작은 최소힙과 반대인 최대힙이 존재하며,
- 오름차순 정렬을 하고자하는 경우에는 배열의 모든 값을 최소힙에 넣어 루트노드부터 하나씩 빼 배열을 만들면 됩니다.
- 힙은 자료구조에 데이터를 넣는 과정에서 heapify라는 재조정작업으로 인해 logN번의 연산이 발생하며, N개의 데이터를 넣고 빼는 과정을 포함하면, 결과적으로 NlogN의 시간복잡도가 발생합니다.

6. 카운팅정렬에 대해 설명해보세요.

- 카운팅정렬은 시간복잡도가 N에 해당하는 가장 빠른 정렬알고리즘입니다.
- 구현시 배열의 값들의 개수를 저장하는 카운팅 배열을 추가적으로 생성해야합니다.
- 카운팅 배열을 통해 개수가 1이상인 요소에 대해 맨 앞에서부터 채워나가면 정렬된 배열을 완성할 수 있습니다.
- 배열 요소들의 분포가 넓을 경우 카운팅 배열을 만드는 과정에서 공간복잡도에 대한 비용이 크게 증가할 수 있습니다.
- 그래서 배열 요소들의 분포가 좁을 경우 사용하기 적합한 정렬 알고리즘입니다.

7. 맵과 셋에 대해 설명해보세요.

- 맵은 유일한 key를 기반으로 값을 저장하는 자료구조입니다.
- key를 기반으로 값을 얻어오고 저장하는 것이가능하며, 중복된 키가 저장될 수 없습니다.
- 셋은 값만을 가지고 있는 자료구조입니다. 값은 유일해야하며, 중복될수 없습니다.(자바스크립트 문서에는 셋은 값만을 갖는 자료구조라고 설명되어있음)

8. 해시테이블에 대해 설명해보세요.

- 해시테이블은 key,value 자료구조로 해시함수와 배열을 내부적으로 사용합니다.
- 해시함수는 모듈러 연산을 활용해 key를 배열의 인덱스로 변환하는 함수입니다.
- 키가 다르더라도 해시함수가 동일한 인덱스를 리턴하는 경우를 해시충돌이라하며, 개방주소법과, 분리연결법을 통해 해시충돌문제를 해결할 수 있습니다.
- 해시테이블은 삽입,삭제,접근 모두 시간복잡도가 상수입니다.

9. 우선순위큐에 대해 설명해보세요.

- 우선순위큐는 힙을 기반으로 하는 자료구조입니다.
- 일반 큐와 달리 우선순위가 높은 요소가 먼저 꺼내지는 큐입니다.
- 자바스크립트에서는 배열에 값이 추가될때마다 sort 함수를 통해 우선순위에 따른 정렬을 수행하여, 우선순위큐를 구현할 수 있습니다.

10. MST에 대해 설명해보세요.

- 최소 스패닝 트리는 그래프의 모든 정점을 연결하는 데 최소 간선으로 이루어진 부분 그래프입니다.
- 특성상 싸이클이 존재하지 않지 않기때문에 트리로 분류됩니다.
- 크루스칼 알고리즘과 프림 알고리즘을 활용하여 MST를 구성하는데 최소 비용을 구할 수 있습니다.

> 크루스칼 알고리즘은 간선리스트를 가중치를 기준으로 정렬한뒤 최소 간선부터 mst에 포함시켜나가는데 사이클이 발생하면, 해당 간선을 포함시키지 않습니다.
이런식으로 정점-1개의 간선의 비용을 모두 더하면 MST를 구성하는 최소비용을 구할 수 있습니다.

> 프림 알고리즘은 그래프의 특정정점부터 시작한다.
> 인접한 정점과 간선들을 우선순위큐에 추가하고, 우선순위큐에서 작은 가중치 간선부터 하나씩 꺼내 합하고 정점을 방문처리하며, 
> 모든 정점을 방문하면 MST를 구성하는 최소비용을 구할 수 있다. 

11. 이진힙 자료구조에 대해 설명해보세요.

- 힙은 노드의 값에 따라 부모노드와 자식노드가 결정되는 완전이진트리이다. 완전이진트리는 마지막 레벨을 제외한 모든 노드가 채워져 있으며, 마지막 레벨은 왼쪽부터 자식노드가 채워져 있는 트리
- 이진 힙은 자식노드가 2개 이하인 힙이다.

12. 다익스트라 알고리즘에 대해 설명해보세요.

- 다익스트라는 특정 정점으로부터 각 정점까지 도달하는 최소 비용을 구하는 알고리즘이다.
- 양의 간선으로 이루어져있어야 사용 가능하다.
- 각 정점까지 최소 비용을 저장하는 DISTANCE배열을 모두 무한대 값으로 초기화하고,
- 시작정점부터 시작하여 인접한 정점들에 해당하는 DISTANCE 배열의 값을 갱신해나갑니다.(최소비용 갱신 방법 : (출발 정점의 DISTANCE 배열 값 + 도착 정점까지의 거리)가 도착정점의 DISTANCE배열값보다 작다면 갱신)
- 모든 정점을 방문하면 DISTANCE배열에는 각 정점까지의 최소비용이 저장됩니다.

## 웹

1. 브라우저에서 www.daum.net을 입력하면 어떤 일이 일어나나요.

- 브라우저는 URL을 파싱하여, 프로토콜과 URL, 포트를 분석합니다. 
- URL에 해당하는 IP주소를 찾기위해 DNS캐시,HOST파일,DNS서버 순으로 검색을 하며, IP주소를 알아내면 해당 IP주소에 해당하는 서버와 3WAY HAND SHAKE 과정을 통해 TCP 소켓 연결을 진행합니다.
- 소켓 연결이 되면, HTTP 요청을 보내고, 응답을 받습니다. 
- 응답을 통해 HTML문서를 받은 브라우저는 HTML,CSS 파싱과정을 거쳐 DOM TREE와 CSSOM 트리를 완성합니다.
- 두 트리를 기반으로 RENDER TREE를 만들며, RENDER TREE를 기반으로 리플로우라고도 불리는 레이아웃 연산과정(각요소들이 실제 브라우저 화면에 보여질 크기, 위치와 같은 값을 계산하는 과정)을 거칩니다.
- 레이아웃 연산과정이 완료되면, 페인트 과정을 거쳐 화면에 보이게 됩니다.

2. DOM이란 ?

- DOM이란 웹페이지에 대한 프로그래밍 인터페이스입니다. 
- 웹문서를 구조화된 노드를 통해 객체형태로 표현하며, 이러한 요소들을 자바스크립트에서 접근할 수 있도록 API를 제공합니다.

3. CORS란 ?

- CORS란 서버에서 허용하는 경우 다른 출처의 서버로 요청과 응답이 가능한 브라우저 상의 정책입니다.
- Preflight request라고 하는 사전 요청을 통해 허용 출처들을 질의하고, Access-Control-Allow-Origin이라는 헤더를 통해 허용하는 출처들을 리턴받습니다.
- 브라우저는 요청한 출처가 허용 출처에 포함된다면 실제 요청과 응답을 진행합니다.

4. 크로스브라우징이란 무엇이고 전략에 대해 말해보세요.

- 크로스 브라우징이란 어떠한 환경에서도 이상없이 동작시키도록 하는 방법이다. 
- 웹페이지 제작시 사용자가 사용하는 다양한 브라우저 환경에서 정상동작하도록 개발해야한다.
- 자바스크립트의 경우 라이브러리를 사용하거나, 직접 폴리필(해당 환경에서 메서드 또는 함수가 존재하지 않는 경우 런타임에 환경에 맞게 주입하는 기술)을 구현한다.
- css의 경우 브라우저마다 기본 스타일이 다르기때문에 아얘 초기화하는 reset.css나 기본스타일을 통일하는 nomalize.css를 사용하면 된다.

5. SSR과 CSR에 대해 말해보세요.

- SSR은 서버측에서 DATA가 결합된 HTML을 만들어서 클라이언트로 전달하는 방식이고, CSR은 DATA가 결합되지 않은 HTML파일을 받은 후 클라이언트에서 비동기적으로 DATA를 받아와 렌더링하는 방식이다.
- SPA는 최초에 한번 페이지를 로딩한후 즉, HTML 파일을 한번만 받은 뒤 클라이언트단에서 데이터만 변경해 사용하는 어플리케이션이다.

6. GET과 POST의 차이점에 대해 말해보세요.

- GET 방식은 보통 서버에 데이터 요청시 사용하는 HTTP METHOD 중 하나입니다.
- GET 방식은 브라우저에 캐싱되며, URL을 통해 쿼리문자열이 전달되므로 쿼리문자열 길이의 제한이 있습니다.
- POST 방식은 보통 서버에 데이터 입력시 사용하는 HTTP METHOD 중 하나입니다.
- POST 방식은 브라우저에 캐싱되지 않으며, HTTP 본문을 통해 데이터가 전달되므로, 데이터 길이의 제한이 없습니다.

7. 브라우저 저장소에 대해 설명해보세요.

- 브라우저 저장소에는 쿠키와 웹스토리지 라는 것이 있습니다.
- 쿠키는 보통 서버에서 클라이언트를 식별하기위해 전달하는 값으로 사용됩니다.
- 쿠키는 길이의 제한이 있으며, SetCookie라는 서버의 응답헤더를 통해 설정될수도 있습니다.
- 쿠키는 유효기간이 존재하며, 도메인별로 저장됩니다. 그리고 http 요청시마다 첨부되어 전송됩니다.
- 웹스토리지는 key/value 기반의 세션스토리지와 로컬스토리지 두가지가 있습니다.
- 로컬 스토리지는 영구적으로 저장할수 있으며, 도메인별로 생성됩니다. 그리고 브라우저를 종료해도 데이터가 남아있습니다.
- 세션 스토리지는 브라우저 탭마다 존재하며, 탭을 종료하면 소멸됩니다.

8. HTML 렌더링 중 자바스크립트 코드가 실행되면 멈추는 이유가 뭔가요 ??

- HTML 파싱과정에서 CSS파일 또는 자바스크립트 코드는 블로킹 요소입니다.
- 즉, 파싱과정중 자바스크립트 코드를 만나게되면, 파싱과정을 중지하고 자바스크립트 코드를 수행합니다.
- 실행이 완료되면, HTML 파싱과정을 다시 진행하기때문에 렌더링이 잠시 멈추게 됩니다.

9. HTTP 버전별 특징에 대해 말해보세요.

- 0.9버전은 가장 초기버전으로 GET통신만 가능하며, HTTP헤더가 존재하지않아, 오류발생시 HTML문서안에 포함되었습니다.
- 1.0에서 HTTP 헤더가 등장했고, POST방식이 추가되었습니다.
- 1.1은 현재 가장 표준적인 버전이며, 지금 일반적으로 사용하는 HTTP METHOD가 모두 등장했습니다.
- 또한 Keep alive라는 기능이 추가되어 소켓 커넥션을 맺은뒤 일정 시간동안은 유지되도록 성능이 개선되었습니다. 
- 2.0은 가장 최신 버전이며, 이진 프로토콜이라고만 알고있습니다. 또한 하나의 http 요청을 통해 여러개 자원을가져올 수 있는것으로 알고있습니다.
 
10. HTML5에 대해 말해보세요.

- 과거에는 동영상 음악감상,은행업무등과 같은 인터넷 서비스를 플러그인 설치를 통해 제공하였는데, 이러한 기능들이 브라우저 자체에서 제공할 수 있도록 고안하여 등장한것이 HTML5입니다.
- 지금 많이 사용하는 웹소켓 , 웹스토리지, 카메라,마이크 액세스,CSS3같은 기술들이 HTML5 스펙에 포함되어있습니다.

11. REST API란 ?

- HTTP 프로토콜 본연의 특징을 최대한 활용하여 API를 설계하는 방법론입니다.
- HTTP METHOD로 CRUD를 표현하고 URL을 통해 자원을 명시함으로써 자원에 대한 CRUD 오퍼레이션을 정의할 수 있습니다.
- API가 이해하기 쉽고, 설계하기 단순하여 많이 사용됩니다.

12. 시멘틱 태그란 ?

- SEO 최적화를 위해 봇에서 크롤링시 HTML의 각 태그들이 어떠한 역할을 하는지 의미적으로 부여한 태그들입니다.
- header,section,aside,footer와 같은 태그들이 시멘틱 태그들입니다.

## 자바스크립트

1. 호이스팅에 대해 설명해보세요.

- 호이스팅이란 변수,함수의 선언부가 최상위로 끌어올려지는 것을 말합니다. 
- 자바스크립트 엔진은 선언문을 구문분석과정에서 해석하고, 할당문은 런타임과정에서 실행되기에 선언부가 최상위로 끌어올려집니다. 
- var 변수와 함수 선언문의 경우 선언부가 함수 스코프의 최상위로 끌어올려지며, 함수선언문은 구현부까지 같이 끌어 올려집니다. 
- let const는 보통 호이스팅되지 않는다고 알고있으나 실제로는 블록 스코프의 최상위로 끌어올려집니다. 
- 스코프 시작지점과 초기화지점 사이를 temparal dead zone이라고 하는 데, 이 영역에서 let const를 참조하면 아직 초기화되지 않았다는 에러가 뜹니다.

2. 클로저에 대해 설명해보세요. 클로저를 언제 사용하나요.

- 클로저는 고차함수 안에서 리턴되는 함수안에서 외부함수의 변수를 참조하는 경우 고차 함수의 호출이 종료되어도, 리턴된 함수에서 상위 스코프의 변수를 지속적으로 참조가능한 메커니즘을 말합니다.
- 클로저는 보통 고차함수에서 동적인 함수를 리턴할때 많이 사용이됩니다. 예를 들어 고차함수 매개변수로 3을 입력받고 리턴되는 함수에서 3을 참조하여 3의 배수를 리턴하는 함수를 생성할 수 있습니다.

3. 스코프체인에 대해 설명해보세요.

- 스코프체인은 자바스크립트에서 변수를 찾는 메커니즘입니다. 실행중인 렉시컬 환경에 변수정보가 없다면 상위스코프를 따라 올라가며 찾는 방식이며, window 객체까지 도달하여 변수 정보가 없다면, undefined라는 에러를 출력합니다.

4. this란 무엇인가요 ?

- this는 window객체로 초기화가 됩니다. 하지만 함수 호출패턴에 따라 그 의미와 값을 달리할 수 있습니다. 

5. 함수 호출 패턴에서 따른 this 값에 대해 설명해보세요.

- 일반적인 함수호출의 경우 window 객체이며, 메서드 호출의 경우 메서드를 호출한 객체가 this가 됩니다.
- 생성자함수의 경우 생성되는 객체가 this가 됩니다.
- 또한 this는 call,apply,bind와 같은 this 바인딩 메서드을 통해서도 값을 달리할 수 있습니다.
- call의 경우 함수 호출시 사용하며, 인자전달시 쉼표로 구분하여 전달합니다. 또한 apply경우도 함수호출시 사용하며, 인자 전달시 배열의 형태로 전달합니다.
- bind는 함수 선언시 사용하며 선언문 뒤에 붙입니다.

6. 자바스크립트 언어의 특징에 대해 말해보세요.

- 자바스크립트는 싱글스레드 언어이며, 한줄씩 분석해가며 실행하는 인터프리터 언어입니다.
- 또한 함수를 일급객체(변수에 할당,인자전달,함수에서 리턴이 가능) 취급하기 떄문에 함수형 프로그래밍이 가능합니다.
- 그리고 최근 자바스크립트 엔진은 JIT 컴파일러가 내장되어 있어 자주 반복되는 바이트 코드를 기계어로 컴파일하여 실행속도를 최적화합니다.

7. 자바스크립트는 싱글스레드인데 어떻게 비동기를 지원하나요 ?

- 자바스크립트는 싱글스레드로 동작하지만, 자바스크립트 일부 기능들은 Web api를 사용합니다. 
- Web api는 자바스크립트 엔진이 아닌 독립적인 영역에서 실행되며, 전달된 콜백함수는 web api가 종료되면 이벤트큐로 전달되고 자바스크립트 코드가 모두 실행되면 이벤트 루프에 의해 큐에 꺼내지어 호출스택에 올라갑니다.
- 이러한 흐름이 비동기적 실행을 가능하게 만듭니다.

9. 이벤트 루프란 무엇인가요 ?

- 이벤트 루프는 호출스택이 비게 되면 이벤트 큐에 저장된 함수들을 호출스택에 올려 실행하는 스케쥴러입니다. 

10. setTimeout 을 0초로 설정한 콜백함수와 Promise resolve의 콜백함수중 뭐가 먼저 실행되나요 ?

- setTimeout의 경우 콜백함수가 테스크 큐에 저장되고, Promise resolve 콜백함수의 경우, 마이크로 테스크 큐에 저장됩니다.
- 브라우저마다 각 큐의 우선순위는 다를수 있으나, 크롬의 경우 마이크로 테스크 큐가 우선순위가 높기때문에 Promise resolve의 콜백함수가 먼저실행됩니다.

11. 자바스크립트를 멀티쓰레드로 실행하는 방법에 대해 말해보세요.

- 자바스크립트는 싱글스레드로 동작하기떄문에 연산량이 많은 작업을 할 경우, 웹워커를 생성하여, 멀티쓰레드로 실행 시킬 수 있습니다.
- 워커는 dom에 접근할수 없으므로, 메인쓰레드와의 통신을 통해 연산의 결과를 전달 받을 수 있습니다.

12. 렉시컬 스코프란 무엇이고, 이와 반대되는 개념은 무엇인가요 ?

- 프로그래밍 언어에서 함수의 선언 위치에 따라 상위스코프가 결정되는 것을 렉시컬 스코프라고합니다.
- 렉시컬 스코프는 렉싱타임에 즉, 구문분석 과정에서 상위스코프가 결정되므로 렉시컬 스코프라 부릅니다.
- 반대되는 개념은 동적 스코프이며, 동적스코프는 함수 호출 위치에 따라 상위스코프가 결정됩니다.
- 동적스코프는 런타임에 상위스코프가 결정됩니다.

13. 비동기적으로 실행되는 것을 동기적으로 코딩하는 방법에 대해 말해보세요.

- 우선 비동기 함수들은 콜백 중첩을 통해 동기적으로 실행시킬수 있습니다.
- 콜백 중첩은 가독성을 떨어뜨리기 때문에 Promise객체를 사용하여 가독성을 올릴수 있습니다.
- Promise 객체생성 즉시 Promise 객체는 pending(약속을 수행중인) 상태가 되며, resolve 호출시 fulfilled,reject호출시 rejected 상태가 되어, 해당 상태에 따른 콜백함수가 호출되도록 설계되어 있습니다.
- then 체이닝과 Promise 객체생성을 통해 콜백 중첩보다는 가독성 좋은 코드 작성이 가능합니다.
- async await은 비동기 함수를 처리하는 가장 최신 문법입니다.
- await은 어짜피 Promise 객체를 대상으로 블록하기때문에 Promise가 같이 사용된다고 할 수 있습니다.
- async키워드로 선언된 함수에서만 await 문법 사용이 가능합니다.

14. DOM 이벤트란 무엇이고, 이벤트의 흐름은 어떻게 되는지 말씀해보세요.

- DOM 이벤트는 브라우저 이벤트 인터페이스에 맞춰 구현된 객체입니다.
- 해당 객체는 사용자 인터렉션 또는 DOM 변화,브라우저로 부터 생성 및 전파됩니다.
- 이벤트의 흐름은 부모 엘리먼트에 의존합니다. window 객체부터 이벤트가 발생한 엘리먼트까지 이벤트가 전파되며, 이과정을 캡처링 이라고 합니다. 캡처링 단계이후, 다시 부모엘리먼트를 따라 window 객체까지 타고 올라가는 버블링 단계가 있습니다.
- 이벤트 흐름을 중단하기 위한 메서드로는 stopPropagation(다음 엘리먼트로의 전파 중단),stopImmediatePropagation(이벤트가 발생한 엘리먼트 내에서 전파 중단)이 있습니다.

15. 실행컨텍스트란 무엇인가요 ?

- 실행컨텍스트는 자바스크립트 실행시 함수가 호출될때마다 호출스택에 생성되는 물리적 객체입니다.
- 코드가 실행되면 최초로 전역 실행 컨텍스트가 생성되며, 함수 호출마다 함수 실행 컨텍스트가 생성됩니다.
- 실행컨텍스트는 ES6가 나온 뒤로 렉시컬 환경과 변수 환경이라는 두개의 컴포넌트를 갖고 있는데, 렉시컬 환경은 let,const,함수에 대한 정보와 상위 스코프에 대한 참조, 함수 환경은 var에 대한 정보를 갖고 있습니다.

16. require와 import의 차이점에 대해 말씀해보세요.

- require는 Commonjs 모듈화 방식이며, import는 ES6에서 등장한 ESM 방식입니다.
- 과거 브라우저는 ESM방식을 지원하지 않았기떄문에 ESM은 바벨과 함께 사용하는 경우가 보통입니다.
- require와 달리 import는 필요한 객체 또는 함수만 로드하여 메모리 절약이 가능합니다.

17. ES6의 화살표 함수는 언제 사용하고, 왜쓰나요 ?

- 화살표 함수는 함수 표현식을 간결하게 할 수 있고, this값을 가지고 있지 않습니다.
- 즉, this를 참조하는 경우 상위스코프의 this를 참조하게 됩니다.
- this는 메서드가 아닌 일반함수에서 상위스코프의 this를 참조해야할 떄 사용됩니다. 
- 예를들면 메서드 내부에 setTimeout이 사용되는 경우 콜백함수를 arrow function으로 선언하면 this가 메서드 객체를 가르키게 할 수 있습니다.

18. var let const 의 차이점에 대해 말씀해보세요 !

- var는 함수 스코프를 따르며, let const는 블록 스코프를 따릅니다.
- 함수 스코프란 함수단위로 스코프가 정해지는 것을 말합니다.
- 블록 스코프란 블록단위로 스코프가 정해지는 것을 말합니다.

19. 이터러블 객체란 무엇이며, 이터레이터객체란 무엇인가요 ?

- 이터러블 객체란, for of와 같은 문법을 통해 반복 가능한 객체로 이터레이터 객체를 반환하는 Symbol.iterator(심볼이란 es6에서 등장한 타입으로 충돌이 없는 키로써 활용됩니다)라고 하는 특수 내장 심볼 프로퍼티를 가진 객체입니다.
- 이터레이터 객체란, next메서드를 통해 반복에 사용될 값을 만들어내는 객체입니다.
- next 메서드는 반복의 상태를 객체형태로 반환하는데 done 프로퍼티가 true일 경우 반복이 끝나고, done 프로퍼티가 false일 경우 반복이 가능한 상태로 값을 리턴합니다.

20. 제너레이터란 무엇이며, 제너레이터 함수란 무엇인가요 ?

- 제너레이터 객체는 여러개의 값을 필요에 따라 하나씩 반환하는 객체입니다. 이터러블 객체라고 보면되는데, 제너레이터 함수를 이용해 쉽게 생성할 수 있습니다.
- 제너레이터 함수는 제너레이터 객체를 생성하는 함수입니다. 제너레이터가 반환할 로직을 함수에서 yield 키워드를 통해 정의합니다.

21. 쓰로틀과 디바운스의 차이점에 대해 말해보세요.

- 쓰로틀은 특정 시간간격안에 많은 이벤트가 발생할때, 한번만 함수호출이 되게하는 기술입니다. 
- 디바운스는 이벤트가 발생하고 특정 시간간격안에 이벤트가 연속적으로 발생하면 함수호출을 지연시키는 기술입니다.
- 쓰로틀은 특정 시간간격마다 함수호출을 보장하지만, 디바운스는 이벤트가 계속 연속적으로 발생한다면 무한정 지연될수 있습니다.

22. 프로토타입이란 뭔가요 ? 구조에 대해 설명해보세요.

- 생성자 함수 또는 class를 기반으로 생성된 객체의 원형이 되는 객체가 프로토타입 객체입니다. 함수 및 class 선언시 생성됩니다.
- 함수의 prototype프로퍼티를 통해 프로토타입객체에 대한 참조가 가능하며, 생성된 객체는 `__proto__`라는 키워드를 통해 프로토타입 객체에 대한 참조가 가능합니다.
- 또한 프로토타입객체의 생성자는 자신을 생성한 객체를 가르킵니다.
- 프로토타입 객체에 변수 또는 메서드를 할당하면 생성된 객체에서 마치 자신의 메서드인 것처럼 사용이 가능합니다.

23. 프로토타입 체인이란 뭔가요 ?

- 프로토타입 체인이란 프로퍼티를 검색하는 메커니즘입니다.
- 객체에 프로퍼티가 존재하지 않으면 proto 프로퍼티를 통해 프로토타입 객체에 해당 프로퍼티가 존재하는지 확인하고 있다면 마치 자신의 것처럼 사용가능합니다.
- 또 프로토타입 객체에도 없다면 해당 프로토타입 객체의 `__proto__` 프로퍼티가 가르키는 객체에서 찾습니다. 이런식으로 계속 따라 올라가는데 Object 프로토타입 객체를 거쳐 null 나올때까지 찾아들어갑니다.
- 프로토타입 메커니즘을 활용해 상속이라고 하는 개념을 사용할 수 있습니다.

24. 이벤트 위임기법이란 뭔가요 ? 장점은 무엇인가요 ?

- 이벤트 위임기법이란 버블링이라고하는 이벤트 흐름을 이용하여 상위엘리멘트 이벤트 리스너를 통해 하위 엘리먼트에서 발생한 이벤트를 다루는 기술입니다.
- 리스너를 하나만 만들기때문에 메모리 효율성 측면에서 좋습니다.
- 여러 엘리먼트에서 발생하는 이벤트를 하나의 리스너에서 관리하기 때문에 이벤트 관리에 좋습니다.

25. 무한스크롤 구현방법에 대해 말씀해보세요.

- 무한 스크롤의 경우 저는 IntersectionObserver라는 객체를 사용하여 구현합니다.
- 옵저버 객체를 생성후 옵저버객체가 관찰할 대상 엘리먼트를 등록할 수 있습니다.
- 관찰 대상 엘리먼트가 교차영역에 들어오면 콜백함수가 호출되며, 교차영역에 들어온 엘리먼트의 목록을 콜백함수의 인자로 전달받습니다.
- 무한 스크롤 구현시 가장 밑바닥에 엘리먼트를 하나두고 해당 엘리먼트가 교차영역에 들어오면 추가적인 데이터를 요청하는 방식으로 구현합니다.

26. 이미지 레이지 로딩이란 무엇이며, 구현하는 방법을 말씀해보세요.

- 이미지 레이지 로딩도 IntersectionObserver라는 객체를 사용하여 구현합니다.
- 모든 이미지 태그는 src 속성을 비워두고 dataset 속성에 이미지 url을 설정해놓습니다.
- 그리고 교차영역에 들어오는 순간 dataset 속성의 이미지 url을 src 속성에 설정합니다.

27. defer과 async의 차이점에 대해 말해보세요.

- 브라우저는 defer속성이 박힌 스크립트를 백그라운드에서 다운로드합니다. 즉, html 파싱과정과 독립적으로 로드합니다.
- 하지만 defer는 dom이 준비된 이후 실행됩니다. 또 DOMContentLoaded가 발생하기 전에 실행됩니다.
- 그리고 defer속성이 박힌 스크립트는 태그된 순서에 따라 순차적으로 실행됩니다.
- async는 페이지와 완전히 독립적으로 동작합니다.
- 실행시 dom을 기다리지도 않으며, 태그된 순서와 관계없이 모든 async 태그는 비동기적으로 실행됩니다.

## 프레임워크

1. 리액트에서 setState는 왜쓰나요 ?

- 리액트에서는 상태변화에 따른 뷰의 변화를 추구합니다.
- 허나 리액트에서는 기존 state를 직접 변경한다고 리렌더링 되지 않습니다.
- 그러므로 setState를 사용해야합니다.

2. 리액트에서 state가 불변해야하는 이유는 뭔가요 ?

- 리액트는 setState 메서드를 통해 전달된 객체와 기존 state 객체 주소비교를 통해 다름을 감지하고 다를시에 리렌더링을 수행하므로 새로운 객체를 setState의 인자로 전달해야합니다.
- 즉, 리액트가 상태변화를 감지하려면 불변성을 유지해야합니다.
- shouldComponentUpdate은 리렌더링 여부를 결정하는 메서드인데 인자로 변경될 state객체를 받습니다. 이때 불변성을 유지해야만, 이전 객체와 변경될 객체의 비교가 수월하기 때문에 불변성을 유지해야합니다.
- 리덕스에서도 reducer를 순수함수(입력데이터를 변경하지 않고 동일한 입력데이터에 대해 동일한 출력값을 일관되게 리턴하는 함수)로 사용하기 위해 인자로 전달된 state의 불변함을 유지한다. redux자체가 내부적으로 주소비교를 통해 변경을 감지하므로 state를 불변하게 유지해야한다.

3. 리액트에서 key는 왜쓰나요 ??

- 배열을 기반으로map함수를 사용해 엘리먼트 리스트를 생성하는 경우, 이전 엘리먼트와 생성될 엘리먼트의 key값을 기반으로 변경을 감지하여 리렌더링여부를 결정합니다. 이때, 엘리먼트 식별 및 리렌더링의 효율성을 위해 key를 사용합니다. 
- 또한 key로 인덱스를 사용하면 안됩니다. 배열의 순서가 이전과 동일하다는 것이 보장되지 않기때문에 이전에 사용되었던 배열의 요소라도 인덱스변화로 인해 다른 요소로 식별되어 리렌더링되는 이슈를 발생시킬수 있기때문입니다.

4. useEffect란 무엇인가요 ?

- useEffect는 함수형 컴포넌트에서 사용하는 훅 종류중 하나입니다.
- 렌더링이 완료되어 dom이 준비되면 비동기적으로 호출되는 부수효과함수입니다.
- 의존성 배열에 상태를 추가하여 상태 변화에 따라 매번 호출되게 할 수도있으며,
- 빈배열로 선언시 컴포넌트 생성시 한번만 호출됩니다.
- 또한 함수를 리턴할수도 있는데 리턴하는 함수는 useEffect함수가 호출되기 직전과 컴포넌트가 소멸될때 호출됩니다.

5. 함수형 컴포넌트와 클래스형 컴포넌트의 차이점에 대해 말씀해보세요.

- 함수형 컴포넌트는 함수로 작성 컴포넌트이고, 클래스형 컴포넌트는 클래스로 작성된 컴포넌트입니다.
- 과거 함수형 컴포넌트는 상태가 존재하지 않는 정적 컴포넌트였으나, 훅의 등장으로 state를 사용할수 있게되었습니다.
- 또한 함수형 컴포넌트에서는 생명주기를 훅을 통해 관리하지만 클래스형 컴포넌트에서는 생명주기 메서드들을 활용해 관리합니다.

6. 함수형 컴포넌트에서 상태관리 방법이 뭔가요 ?

- 함수형 컴포넌트에서는 useState를 사용해 상태값과 상태값을 갱신하는 함수를 생성하여 관리할 수 있습니다.

7. useEffect는 클래스형 컴포넌트의 어떤 생명주기 함수를 대체할 수 있나요 ?

- 클래스형 컴포넌트 생명주기 메서드들 중 componentDidUpdate와 componentDidMount, componentWillUnmount를 대체할 수 있습니다. componentWillUnmount의 경우 리턴되는 함수를 통해 대체가능합니다.

8. HOC란 무엇인가요 ?

- 고차 컴포넌트함수로써 컴포넌트를 인자로 받아 인자로 받은 컴포넌트를 렌더링하는 새로운 컴포넌트를 리턴합니다.
- 인자로 받은 컴포넌트를 새로운 컴포넌트로 감싸 컴포넌트를 데코레이팅 하는데 사용할 수 있습니다. 
- 예를들어 여러 컴포넌트가 공통적으로 수행해야하는 로직 수행후 props로 전달되야 할때, HOC로 해당 기능들을 데코레이팅 할 수있습니다. 로직 재사용성 측면에서 매우 유용합니다.

9. Redux-saga란 무엇이며, saga의 동작원리를 제네레이터함수와 연관지어 말씀해보세요.

- redux를 사용시 특정 action을 후킹하여 비동기 요청시 redux saga를 사용할 수 있습니다.
- 비동기요청결과는 리듀서함수의 페이로드로 전달됩니다.
- saga를 미들웨어로 등록하여 특정액션을 캐치하도록 할 수 있습니다.
- saga 작성시 제너레이터 함수를 사용하는데, yield 키워드를 사용해 액션을 기다리는 take 함수 실행을 반복시키기 위함입니다.

10. Virtual Dom이란 무엇인가요 ?

- Virtual dom이란 실제돔을 추상화한 객체입니다. 
- DOM API를 사용해 DOM을 수정하는 경우 리플로우가 발생하는데, API를 사용할떄마다 발생하여, 연산비용이 증가할 수 있습니다.
- 하지만 Virtual dom에 변경된 내역을 모으고 한번에 실제돔에 적용한다면 리플로우 과정을 한번만 수행하면 되기때문에 효율적입니다.

11. shouldComponentUpdate 메서드에 대해 설명해주세요.

- 리렌더링이 발생하기 직전 호출되는 메서드로 변경된 상태값과 Props를 전달받습니다.
- true를 리턴하면 리렌더링을 수행하고 false를 리턴하면 리렌더링을 수행하지 않습니다.
- 상태값 비교를 통해 리렌더링을 효율적으로 수행시키위해 사용합니다.

12. shouldComponentUpdate 메서드에서 false를 리턴하면, 자식컴포넌트는 리렌더링이 될까요 ?

- 아니요.

13. shouldComponentUpdate 메서드에서 false를 리턴하면, 자식컴포넌트는 리렌더링이 되지 않는데, 리렌더링 시키는 방법은 뭘까요 ?

- forceUpdate라고 하는 메서드를 사용하면 되는 것으로 알고 있습니다.

14. Nextjs란 무엇인가요 ?

- 서버사이드 렌더링을 위한 프레임 워크입니다.

15. getInitialProps 메서드에 대해 설명해보세요.

- 해당 메서드는 페이지 렌더링 전에 사전 수행할 로직들을 위해 사용합니다.
- 서버 또는 클라이언트에서 실행될 수 있습니다.
- URL 입력 또는 새로고침시 서버에서 실행되며, Link컴포넌트를 통해 페이지를 이동하는 경우 클라이언트에서 실행됩니다.
- 페이지로 전달할 props를 리턴할 수 있으며, 서버에서 실행시 메서드 실행후 완성된 html을 보내줍니다.

16. Nextjs 구조에 대해 말씀해보세요.

- `_document.js`는 index.html파일을 구조를 정의합니다.
- `_app.js`는 모든 페이지 컴포넌트의 공통 레이아웃을 만들때 사용하는 파일입니다.
- pages 폴더에 페이지를 생성할 수 있으며, 기본적으로 페이지 url은 파일이름과 동일합니다.
- 웹팩 플러그인 적용시 next.config.js에 설정하면 됩니다.

## 운영체제

1. OS 역할과 응용프로그램과 관계지어 필요한 이유를 설명해보세요.

- os는 시스템 관리자이자, 사용자에게 os 기능을 사용할수 있는 인터페이스를 제공합니다.
- os는 응용프로그램을 관리합니다.(메모리에 적재하거나, cpu에 할당한다,권한관리,다중사용자 시스템제공)
- 시스템 리소스를 효율적으로 배분하고 지원합니다.(프로세스가 효율적으로 동작하도록 지원)

2. SEHLL이란 ?

- CLI,GUI와 같이 OS기능을 사용할 수 있도록 인터페이스를 제공하는 프로그램이다.

3. API란 ?

- API는 응용프로그램에서 OS 기능을 사용할 수 있도록 라이브러리를 통해 제공하는 프로그래밍 인터페이스이다.

4. 시스템 콜이란 ?

- API는 내부적으로 시스템콜을 사용합니다.
- 시스템 콜은 OS에서 제공하는 함수인데, 호출시 커널모드로 실행됩니다.

5. 사용자모드와 커널모드의 차이점

- 커널모드는 특권명령 또는 OS기능 사용시 필요한 모드입니다.
- 사용자 모드는 응용프로그램에서 실행되는 일반적인 명령 수행시 사용되는 모드입니다.
- 응용프로그램에서 시스템콜 호출시 커널모드로 전환후 실행하고 실행이 끝나면 다시 사용자 모드로 전환됩니다.

6. 배치처리시스템,시분할시스템,멀티 태스킹,멀티프로그래밍 시스템에 대해 설명해보세요.

- 배치 처리시스템 : 요청한 작업을 요청 순서대로 처리하는 시스템입니다.
- 시분할 시스템 : 다중사용자 지원을 위해 응답시간을 최소화하여 인터렉션에 빠르게 반응하는 시스템입니다.(컨텍스트 스위칭이 빈번하게 일어납니다)
- 멀티 태스킹 시스템 : 단일 CPU에서 마치 동시에 여러 프로그램이 실행되는 것처럼 보이게하기 위해 매우 빈번하게 컨텍스트스위칭이 일어납니다.
- 멀티 프로그래밍 시스템 : CPU의 활용도를 높히는시스템입니다. 프로세스가 CPU는 사용하지 않을때, 다른 프로세스를 CPU에 할당하여 CPU 노는시간을 최소화합니다.

7. 프로세스란 ?

- 프로세스는 프로그램이 메모리에 적재되어 운영체제의 제어를 받는 상태를 의미합니다.

8. FIFO 스케쥴러, SJF 스케쥴러,우선순위 기반 스케쥴러에 대해 설명해주세요.

- FIFO 스케쥴러 : FCFS(First Come First Served) 스케쥴러라고도 부릅니다., 프로세스를 요청 순서대로 프로세서에 할당합니다.(배치 처리시스템과 동일)
- SJF 스케쥴러 : 실행시간이 가장 짧은 프로세스를 우선적으로 CPU에 할당하는 스케쥴러입니다.
- 우선순위 스케쥴러 : 우선순위가 높은 프로세스를 우선적으로 CPU에 할당합니다.
- 3가지 스케쥴러 모두 비선점 스케쥴러(스케쥴러가 프로세스를 선점할 수 없음)입니다.

9. 라운트로빈 스케쥴러에 대한 설명

- 시분할 시스템의 기반이 되는 스케쥴러입니다.
- 프로세스가 한번에 사용할 수 있는 시간을 지정하여, 사용시간이 끝나면 실행중인 프로세스를 선점하여 중지시키고 다른 프로세스를 CPU에 할당하는 스케쥴러입니다.
- 선점 스케쥴러입니다.

10. 프로세스 상태에 대해 설명해보세요.

- 준비상태 : 스케쥴러가 언제든지 CPU에 할당할 수 있는 상태입니다. (시분할 시스템에 의해 실행상태에서 준비상태로 전환될수있습니다.)
- 실행상태 : 스케쥴러가 준비상태에 있는 프로세스를 CPU에 할당하면 실행상태로 전환됩니다.
- 대기상태 : 인터럽트를 기다리는 상태(저장매체에서 파일읽기가 끝나면 인터럽트를 발생시키는데, 해당 인터럽트를 CPU가 받게되면 프로세스를 대기상태에서 준비상태로 바꿉니다.) 

11. 선점형 스케쥴러와 비선점 스케쥴러의 차이

- 선점형 스케쥴러 : 스케쥴러가 실행중인 프로세스를 선점하여 중지시키고 다른 프로세스를 실행시킬수 있다
- 비선점 스케쥴러 : 스케쥴러가 실행중인 프로세스를 선점할 수 없다.

12. 인터럽트란 무엇이고 왜 필요한가요 ?

- 인터럽트란 하드웨어 또는 소프트웨어에서 이벤트 또는 예외가 발생했을때, CPU에 알려 이를 처리하는 기술입니다.
- 시스템 콜도 소프트웨어 인터럽트에 해당됩니다.
- 타이머 칩에서 특정시간마다 하드웨어 인터럽트를 발생시킵니다.(시분할 시스템에서도 타이머 인터럽트를 통해 프로세스가 교체되야할 시점을 계산합니다)
- 저장매체에서도 파일읽기가 끝나면 특정 명령을 수행하도록 인터럽트를 발생시킵니다.

13. 인터럽트 종류에는 무엇이 있나요 ?

- 하드웨어 인터럽트 : 하드웨어에서 발생시키는 인터럽트
- 소프트웨어 인터럽트 : 소프트웨어에서 발생시키는 인터럽트

14. 프로세스 구조에 대해 말해보세요.

- 프로세스 메모리 구조는 커널영역과 사용자 영역으로 나뉩니다.
- 사용자 영역에는 프로그램 실행 바이너리에 해당되는 CODE(TEXT) 영역과
- 런타임에 동적으로 할당가능한 힙 영역(예를 들면 malloc or new)이 있고,
- 초기화 되지않은 전역변수,STATIC 변수가 저장되는 BSS영역,
- 초기화된 전역변수,STATIC 변수가 저장되는 DATA영역,
- 함수안에서 사용되는 지역변수 매개변수가 저장되는 STACK영역이있으며, 함수가 호출될때마다 STACK에 스택프레임이 생성됩니다.
- PCB, IPC 데이터는 커널영역에 생성됩니다.

15. PCB란 ?

- 프로세스 제어 블록이라고 부릅니다.
- 프로세스 ID,현재 상태와 같은 정보를 저장하며,
- 프로세스가 컨텍스트 스위칭에 의해 준비상태로 변할때,
- 변하는 시점의 레지스터 상태를 저장합니다.

16. 컨텍스트 스위칭이란 ?

- 컨텍스트 스위칭은 CPU에 실행할 프로세스를 교체하는 기술입니다.
-  중지할 프로세스의 레지스터의 상태를 PCB에 저장하며, 실행시킬 프로세스의 PCB를 통해 중단된 시점의 레지스터 상태를 복원합니다.

17. IPC란 무엇이고 왜 필요한가요

- OS 보안상 프로세스 간에는 서로 직접 메모리에 접근할 수 없습니다.
- 프로세스간 데이터를 공유해야하는 경우 IPC라고 하는 설비를 사용하여 데이터를 주고 받을 수 있습니다.
- IPC에서 데이터 교환을 위해 사용되는 메모리 공간은 커널 영역에 생성됩니다.

18. IPC 종류에 대해 말해보세요.

- 파이프 : 부모프로세스와 자식프로세스간 단방향 데이터 전달이 가능한 기법 입니다.
- 메시지큐 : KEY를 기반으로하는 큐를 생성하여, 프로세스간 양방향 데이터 전달이 가능합니다.
- 공유메모리 : KEY를 기반으로 프로세스가 접근가능한 공유메모리 영역을 생성하여, 데이터를 읽고 덮어쓸수 있습니다.
- 시그널 : 커널 또는 프로세스에서 다른 프로세스로 어떤 이벤트가 발생했는지 알리는 기법입니다.(KILL 명령을 통해서도 시그널을 사용할 수 있습니다. kill -9 프로세스번호는 프로세스 종료하라는 이벤트를 날리는 것)
- 소켓 : 네트워크 통신을 위한 기술입니다. 서버 클라이언트간 통신을 위한 기술이며, 같은 컴퓨터의 프로세스간에도 소켓을 통한 네트워크 통신이 가능합니다.

19. 프로세스와 스레드의 차이점

- 프로세스는 프로그램이 메모리에 적재되어 운영체제의 제어를 받는 상태를 말하는데,
- 스레드는 프로세스 안에서의 실행 흐름 단위를 얘기합니다.
- 스레드는 프로세스와 달리 생성시마다 스택을 제외한 프로세스의 영역을 공유하여 사용하기때문에, 스택 메모리만 생성하면 됩니다.
- 스레드간 통신 역시 메모리 영역을 공유하기때문에 간편합니다.
- 멀티스레드라함은 프로세스 안에서 실행흐름이 여러개인 것을 의미합니다.

20. 스레드 동기화 이슈란 ?

- 스레드가 동일한 자원에 접근할때, 컨텍스트 스위칭으로 인해 비정상적으로 실행되는 이슈를 발생킬수 있습니다.
- 예를 들어 여러 스레드가 자원에 1씩 값을 더하는 프로그램을 실행했다고 해봅시다.
- 하나의 스레드가 자원의 데이터를 레지스터로 가져온 직후 다른스레드로 교환되고, 해당 스레드도 레지스터로 데이터를 가져온다면,
- 둘다 2의 값을 쓰므로 두개의 쓰레드가 한번씩 총 두번 실행했음에도 1만 증가하는 비정상실행이 일어날수 있습니다.

21. 동기화 이슈 해결방법은 ?

- 한 스레드가 접근중일때, 다른 스레드가 접근하지 못하도록 막아야합니다.
- 스레드 접근 개수를 제어하는 코드 영역을 임계 영역이라합니다.
- 임계 영역에 대한 접근을 막기위한 락킹 메커니즘으로는 뮤텍스와 세마포어,모니터가 존재합니다.

22. 뮤텍스와 세마포어의 차이점

- 뮤텍스,모니터 : 하나의 스레드만 접근가능한 방식입니다. 허나 뮤텍스는 프로세스간 동기화에 사용하고, 모니터는 한 프로세스안에서 스레드간 동기화에 사용합니다. 또한 뮤텍스가 OS 커널에 의해 제공되고, 뮤텍스는 라이브러리 자체에서 제공하기때문에, 뮤텍스가 오버헤드가 큽니다.
- 세마포어 : 여러 스레드가 접근 가능한 방식입니다. 카운터를 통해 스레드 접근 개수를 제한합니다.

23. 세마포어는 어떻게 구현하나요 ?

- 임계 영역에 진입할때 카운터가 0이면 무한대기하고 1이상이면 카운터를 감소시키는 검사함수와,
- 임계영역에서 나올때 카운터 개수를 증가시키는 증가함수를 구현합니다.

24. 교착상태란 ? 해결방법도 말해보세요.

- 두개이상의 스레드가 서로 점유한 자원을 요청할때, 서로 상대방이 끝나기만을 무한정 기다리는 상태입니다.
- 교착상태 발생조건으로는 상호배제(점유한 자원을 접근못하도록하는 특징),점유대기(점유한 상태에서 기다리는 상태),비선점(자원을 선점할수 없음),순환대기(점유한 상태에서 추가적으로 다른 자원을 요청하는 상태)가 있으며, 해결방법으로는 위 조건중 하나를 제거하거나, 하나의 프로세스를 선점하여 중지시키거나 하는 방법들이 있습니다.

25. 기아상태란 ? 해결방법도 말해보세요.

- 특정 프로세스 또는 스레드 우선순위가 낮아 원하는 자원을 계속 할당받지 못하는 상태
- 오래 기다린 프로세스의 우선순위를 높혀 주는 방법으로 해결이 가능합니다.

26. 가상메모리란 무엇인가요 ?

- 메모리가 실제 메모리보다 많아 보이게 하는 기술입니다.
- 프로세스가 실제 사용하는 메모리영역이 작다는 점에서 착안한 기술입니다.
- 프로세스는 가상주소를 참조하고 실제 CPU 명령 실행시 MMU를 통해 물리메모리를 참조하도록합니다.

27. 페이징 시스템에 대해 설명해보세요.

- 페이징 시스템은 4GB에 해당하는 가상메모리 영역을 4KB의 페이지 단위로 나누어 관리하는 기법입니다.
- 가상 주소는 페이지 번호와 변위값으로 이루어져 있는데,
- 페이지 테이블을 통해 해당 페이지가 위치한 메모리의 베이스 주소를 얻어오고 여기에 변위값을 더해 실제 메모리 주소를 얻습니다.

28. 다중 단계 페이징 시스템이란 무엇인가요 ? 

- 페이지 단위로 가상메모리 공간을 나눈다면 만들어야할 주소공간이 너무 많기때문에,
- 페이지를 디렉토리라고 하는 단위로 한번더 나누어 초기에 만들어야할 주소공간을 최소화하는 시스템입니다.

29. 요구페이징이란 ?

- 프로세스는 모든 데이터를 메모리에 적재하지 않습니다. 필요한 시점에 필요한 영역만 물리메모리에 적재하는데,
- 이를 요구 페이징이라합니다.

30. 페이지 폴트란 무엇인가요 ?

- 요청한 페이지가 실제 물리메모리에 없을때, 일어나는 인터럽트입니다.
- 인터럽트 발생시 해당되는 페이지를 물리메모리에 적재합니다.

31. 페이지 교체 알고리즘 중 FIFO 알고리즘에 대해 말씀해보세요.

- 가장 먼저 들어온 페이지를 내리는 알고리즘입니다.

32. 페이지 교체 알고리즘 중 OPT 알고리즘에 대해 말씀해보세요.

- 앞으로 오랫동안 사용하지 않을 페이지를 내리는 알고리즘입니다.(현실적으로 불가능)

33. 페이지 교체 알고리즘 중 LRU 알고리즘에 대해 말씀해보세요. 

- 사용한지 가장 오래된 페이지를 내리는 알고리즘입니다. 마지막 사용시간을 기반으로 합니다.

34. 페이지 교체 알고리즘 중 LFU 알고리즘에 대해 말씀해보세요.

- 가장 적게 사용된 페이지를 내리는 알고리즘입니다.

35. 페이지 교체 알고리즘 중 NRU 알고리즘에 대해 말씀해보세요.

- 최근에 미사용된 페이지를 내리는 알고리즘입니다. 읽기,쓰기비트를 기반합니다.

36. 세그멘테이션 기법에 대해 말씀해보세요.

- 페이지 시스템과 달리 크기가 서로다른 세그먼트 단위로 쪼개어 관리하는 기법입니다.
- 세그먼트라함은 CODE,DATA,STACK,HEAP 영역단위로 쪼개집니다.
- 외부단편화가 발생합니다.(세그먼트단위의 동적인 크기로 메모리가 실제 물리메모리에 적재되면, 다른 크기의 세그먼트가 실제메모리에 적재될때, 필요한 공간이 확보되지 않을수있음)

37. 파일시스템이란 무엇인가요 ?

- 파일을 저장매체에 효율적으로 저장하기위한 자료구조 또는 알고리즘이다.
- 리눅스는 ext2,3,4파일시스템을 사용하고, 윈도우에서는 FAT이나 NTFS 파일시스템을 이용한다.
- ext는 인덱스 블록기법을 기반으로 한다.

38. 저장매체에 파일을 저장하는 방법 중 블록체인방식과 인덱스 블록 기법에 대해 말해보세요.

- 블록체인 방식은 파일을 블록단위로 쪼개어 저장매체에 저장하고, 각 블록이 다음 블록의 주소를 기억하도록 하는 형태로 관리(첫 블록 주소만 알면 파일데이터를 모두 확인할 수 있다.)
- 인덱스 블록 기법은 파일을 블록단위로 쪼개 저장하고, 각 블록의 위치를 파일 메타정보에 저장하는 기법이다.

39. INODE 방식의 파일시스템에 대해 설명해주세요.

- 인덱스 블록 기법을 기반으로 하고 있으며, 파일시스템 정보를 저장하는 수퍼블록, 파일 상세정보를 저장하는 아이노드블록, 실제데이터를 저장하는 데이터블록으로 구성된다.
- 각 파일을 inode 고유값을 가지며, inode 번호를 통해 아이노드 블록을 참조한다.
- 아이노드 블록에는 파일 권한,소유자정보,파일사이즈,각 블록의 위치를 저장하고 있다.

40. 디렉토리 엔트리란 ?

- 디렉토리마다 가지고 있는 파일/디렉토리에 대한 정보이다.

41. 컴퓨터 부팅과정을 ROM,메모리,저장매체와 연관지어 말씀해주세요.

- 컴퓨터를 켜면 ROM에 저장된 BIOS 코드가 실행된다.
- BIOS 코드에 의해 저장매체 MBR 영역에 있는 부트로더가 메모리에 적재 실행되며,
- 부트로더에 의해 저장매체 부트섹터에 있는 부트코드가 메모리에 적재 실행된다.
- 부트 코드에 의해 저장매체에 저장된 OS 이미지가 메모리에 로드되고 결과적으로 SHELL 프로그램이 실행되어 화면에 보이게 된다.
