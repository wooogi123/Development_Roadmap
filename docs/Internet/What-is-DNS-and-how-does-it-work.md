## DNS와 동작 원리

**What is DNS? (DNS는 무엇인가요?)**
- **DNS(Domain Name System)**는 인터넷의 전화번호부 입니다.
- 사람들은 nytimes.com이나 espn.com과 같은 도메인 네임들을 통해 온라인으로 정보에 접근합니다.
- 웹 브라우저는 **IP(Internet Protocol)** 주소를 통해 상호작용합니다.
- DNS는 변환한다 도메인 네임을 IP 주소로 브라우저가 인터넷 자원을 불러올 수 있또록
- DNS는 브라우저가 인터넷 자원(Resource)을 불러올 수 있도록 도메인 네임을 IP 주소로 변환합니다.
- 인터넷에 연결된 각 기기는 다른 기계가 기기를 찾기 위해서 사용하는 고유 IP 주소를 가지고 있습니다.
- DNS 서버는 사람이 192.168.1.1 (IPv4), 또는 더 복잡한 2400:cb00:2048:1::c629:d7a2 (IPv6)와 같은 IP 주소를 기억할 필요가 없게 해줍니다.

**How does DNS work? (DNS는 어떻게 동작하나요?)**
- DNS의 확인 프로세스에는 호스트네임 (예: www.example.com)을 컴퓨터 친화적인 IP 주소(예: 192.168.1.1)로 변환하는 작업이 포함됩니다.
- IP 주소는 인터넷상의 각 기기에게 제공되며, 도로명 주소가 특정한 집을 찾기 위해 사용되는 것 처럼 적절한 인터넷 기기를 찾기 위해 필요합니다.
- 사용자가 웹페이지를 불러오려할 때, 사용자가 웹 브라우저에 입력한 주소와 (example.com) example.com 웹페이지의 위치를 찾는데 필요한 기계-친화적 주소 간에 변환이 이루어져야 합니다.
- DNS 확인 뒤의 프로세스를 이해하려면, DNS 쿼리가 전달해야하는 여러 하드웨어 구성요소에 대해 알아보는것이 중요합니다.
- 웹 브라우저의 경우, DNS lookup 뒤에서 발생하고 첫 요청 이외에 사용자 컴퓨터에서 상호작용이 필요하지 않습니다.

**There are 4 DNS servers involved in loading a webpage (웹페이지를 불러오는데 관련된 4개의 DNS 서버)**
- **DNS recursor**: **Recursor**는 도서관에 있는 특정한 책을 찾아달라는 요청을 받은 사서라고 생각할 수 있습니다.
  DNS recursor는 웹 브라우저와 같은 애플리케이션을 통해 클라이언트 기기로부터 쿼리를 수신하도록 설계된 서버입니다.
  일반적으로 recursor는 클라이언트의 DNS 쿼리를 만족시키기 위한 추가적인 요청을 할 의무가 있습니다.
- **Root nameserver**: **루트 서버**는 사람이 읽을 수 있는 호스트 이름을 IP 주소로 변환(해결)하는 첫 단계입니다.
  그것은 다른 책장을 가리키는 도서관의 색인(Index)처럼 생각할 수 있습니다. - 일반적으로 그것은 더 구체적인 장소를 가리키는 역할을 합니다.
- **TLD nameserver**: **최상위 도메인 서버 (TLD)**는 도서관의 특정 책장으로 생각할 수 있습니다.
  이 네임서버는 특정 IP 주소를 검색하는 다음 단계로, 호스트네임의 마지막 부분을 호스트합니다. (example.com에서 TLD 서버는 .com을 호스트합니다.)
- **Authoritative nameserver**: 이 최종 네임서버는 책장에 있는 사전으로 생각할 수 있으며, 여기서 특정한 이름은 그 정의로 번역될 수 있습니다.
  Authoritative nameserver는 네임서버 쿼리의 마지막 입니다.
  Authoritativa nameserver가 요청된 레코드에 접근할 수 있는 경우, 요청된 호스트네임의 IP 주소를 초기 요청을 만든 DNS Recrsor(사서)에게 반환합니다.

**What's the difference between an authoritative DNS server and a recursive DNS resolver?**
- 두 컨셉 모두 DNS 인프라에 필수적인 서버 (서버의 그룹들)를 언급하지만, 서로 다른 역할을 수행하며 DNS 쿼리의 pipeline 내부에 다른 위치에서 존재합니다.
- 차이점에 대해 생각해볼 수 있는 한가지 방법은 recursive resolver (DNS recursor)는 DNS 쿼리의 시작 부분에 있고 Authoritative nameserver는 끝에 존재하는 것입니다.

**Recursive DNS resolver**
- **Recursive resolver**는 클라이언트의 재귀적 요청으로부터 응답하고 DNS 레코드를 추적하는데 시간이 걸리는 컴퓨터입니다.
- 요청된 레코드에 대한 Authoritative DNS 네임서버에 도착할때까지 (또는 시간초과나 레코드를 찾을 수 없어서 오류를 반환할 때 까지) 연속적인 요청을 함으로써 작업을 수행합니다.
- 운 좋게도, **Recursive DNS resolver**는 클라이언트에 응답하는데 필요한 레코드를 추적하기 위해 항상 여러번의 요청을 할 필요는 없습니다; 캐싱은 DNS lookup 초기에 요청된 자원 레코드를 제공하여 필요한 요청을 짧게 끝내는데 도움을 주는 지속적인 프로세스입니다.
  ![What-is-dns-and-how-does-it-work-1](https://github.com/wooogi123/Development_Roadmap/blob/master/Backend/Internet/images/What-is-dns-and-how-does-it-work-1.png)
  
**Authoritative DNS server**
- 간단히 말해서, Authoritative DNS 서버는 실제 DNS 자원 레코드를 보유하며, 이를 담당하는 서버입니다.
- 이것은 DNS lookup 순서의 하단에 있는 서버로 쿼리된 자원 레코드로 응답하고, 궁극적으로 웹 브라우저가 웹사이트나 웹 자원에 접근하는데 필요한 IP 주소에 요청을 보낼 수 있게 합니다.
- Authoritative nameserver는 특정 DNS 레코드의 최종적인 근원이기 때문에 다른 서버에 쿼리를 보낼 필요 없이 가지고 있는 데이터에서 쿼리를 충족시킬 수 있습니다.
  ![What-is-dns-and-how-does-it-work-2](https://github.com/wooogi123/Development_Roadmap/blob/master/Backend/Internet/images/What-is-dns-and-how-does-it-work-2.png)
- 쿼리가 foo.example.com이나 blog.cloudflare.com과 같은 서브도메인에 대한 경우, Authoritative nameserver 다음에 추가적인 네임서버가 더해져 서브도메인의 CNAME 레코드를 저장을 담당합니다.
  ![What-is-dns-and-how-does-it-work-3](https://github.com/wooogi123/Development_Roadmap/blob/master/Backend/Internet/images/What-is-dns-and-how-does-it-work-3.png)
  
**What are the steps in a DNS lookup?**
- 대부분의 경우, DNS는 도메인 네임이 적절한 IP 주소로 변환되는 것과 관련이 있습니다.
- 이 프로세스가 어떻게 작동하는지 알면, 웹 브라우저에서 DNS lookup 프로세스를 거쳐 다시 돌아갈 때 DNS 조회 경로를 추적하는데 도움이 됩니다.

- 참고: DNS lookup 정보는 쿼리 컴퓨터 내부에서 로컬로 캐싱되거나 DNS 인프라에서 원격으로 캐싱되는 경우가 많습니다.
- DNS lookup에는 일반적으로 8개의 단계를 거쳐서 진행됩니다.
- DNS 정보가 캐싱되면, DNS lookup 프로세스에서 단계들을 건너 뛰면서 더 빠르게 처리합니다.
- 아래 예제에서는 아무것도 캐싱되지 않을 때의 8단계를 요약합니다.
**The 8 steps in a DNS lookup**
1. 사용자가 'example.com'을 웹 브라우저에 검색하면 쿼리는 인터넷을 돌며 재귀적 DNS Resolver에게 수신됩니다.
2. Resolver는 DNS 루트 네임서버 (.)에 쿼리합니다.
3. 루트 서버는 해당 도메인에 대한 정보를 저장하는 TLD(최고 레벨 도메인) DNS 서버(예를 들어 .com, .net)의 주소로 Resolver 에게 응답합니다. example.com을 검색할 때 우리의 요청은 .com TLD로 향하게 됩니다.
4. Resolver는 .com TLD에게 요청을 보냅니다.
5. TLD 서버는 도메인의 네임서버인 example.com의 IP 주소로 응답합니다.
6. 마지막으로, 재귀 Resolver는 도메인의 네임서버에 쿼리를 보냅니다.
7. example.com의 IP 주소는 네임서버에서 Resolver에게 반환(return)됩니다.
8. DNS Resolver는 처음에 요청된 도메인의 IP 주소로 웹 브라우저에 응답합니다.
  DNS lookup이 example.com의 IP 주소를 반환하게 되면, 브라우저는 웹페이지에 요청을 보낼 수 있습니다.
9. 브라우저는 IP 주소로 HTTP 요청을 보냅니다.
10. 해당 IP의 서버는 브라우저에서 보여줄 웹페이지를 반환합니다.
  ![What-is-dns-and-how-does-it-work-4](https://github.com/wooogi123/Development_Roadmap/blob/master/Backend/Internet/images/What-is-dns-and-how-does-it-work-4.png)
  
**What is a DNS resolver?**
- **DNS resolver**는 DNS lookup의 첫번째 정거장이며, 초기 요청을 만든 클라이언트의 처리를 담당합니다.
- Resolver는 궁극적으로 URL이 필요한 IP 주소로 변환되도록 하는 쿼리 시퀸스를 시작합니다.

- 참고: 일반적으로 캐시되지 않은 DNS lookup은 재귀적이거나 반복되는 쿼리를 모두 포함합니다.

- 재귀적인 DNS 쿼리와 Recursive DNS Resolver를 구별하는것이 중요합니다.
- 쿼리는 쿼리의 해결을 필요로 하는 DNS resolver에 대한 요청을 나타냅니다.
- DNS recursive resolver는 재귀적인 쿼리를 받아들이고 필요한 요청을 해서 응답을 처리하는 컴퓨터입니다.
  ![What-is-dns-and-how-does-it-work-5](https://github.com/wooogi123/Development_Roadmap/blob/master/Backend/Internet/images/What-is-dns-and-how-does-it-work-5.png)
  
**What are the types of DNS Queries?**
- 일반적인 DNS lookup에서는 세 가지 유형의 쿼리가 발생합니다.
- 이러한 쿼리의 조합을 사용하면 DNS 확인을 위해 최적화된 프로세스를 통해 쿼리가 돌아다니는 거리를 줄일 수 있습니다.
- 이상적인 상황에서는 캐시된 레코드 데이터를 사용하여 DNS 네임서버가 비-재귀적인 쿼리를 반환할 수 있습니다.

**3 types of DNS queries**
1. Recursive query: 재귀적인 쿼리에서, DNS 클라이언트는 DNS 서버 (일반적으로 DNS recursive resolver)가 요청된 자원 레코드나 레코드를 찾지 못할경우 오류 메세지로 클라이언트에 응답하도록 요구합니다.
2. Iterative query: 이 경우 DNS 클라이언트는 DNS 서버가 최고의 답을 반환하도록 허가합니다. 쿼리된 DNS 서버이 쿼리 이름과 맞지 않으면, 도메인 네임스페이스에 더 낮은 수준에 대해 권한이 있는 DNS 서버에 대한 주소를 반환합니다. 그 후 DNS 클라이언트는 반환된 주소로 쿼리를 만듭니다. 이 프로세스는 오류 또는 시간초과가 발생할 때까지 쿼리 체인에 추가적인 DNS 서버가 있는 상태로 계속됩니다.
3. Non-recursive query: 일반적으로 DNS resolver 클라이언트가 DNS 서버에 액세스 할 수 있는 레코드를 쿼리할때 해당 레코드에 대한 권한이 있거나 해당 레코드가 캐시 내에 존재해 발생합니다. 일반적으로, DNS 서버는 추가적인 대역폭 소비와 upstream 서버를 불러오는 것을 방지하기 위해 DNS 레코드를 캐시합니다.

**What is DNS caching? Where does DNS caching occur?**
- 캐싱의 목적은 데이터 요청에 대한 성능과 신뢰성이 향상되는 장소에 데이터를 일시적으로 저장하는 것입니다.
- DNS 캐싱은 요청하는 클라이언트에 더 가까이 데이터를 저장하여 DNS 쿼리를 더 일찍 해결하고 DNS lookup 체인의 추가 쿼리를 피해 불러오는 시간을 개선하고 대역폭/CPU의 소비를 줄입니다.
- DNS 데이터는 다양한 위치에 캐시될 수 있으며, 각 데이터에는 TTL(time-to-live)에 의해 결정된 정해진 시간동안 DNS 레코드가 저장됩니다.

**Browser DNS caching**
- 최신 웹 브라우저는 기본적으로 정해진 시간동안 DNS 레코드를 캐시하도록 설계되어 있습니다.
- DNS 캐싱이 웹 브라우저에 가까울수록, 캐시를 확인하고 IP 주소로 정확한 요청을 하기 위해 더 적은 처리 단계를 밟게 됩니다.
- DNS 레코드에 대한 요청이 있을 경우, 브라우저 캐시는 요청된 레코드에 대해 처음으로 확인되는 위치입니다.

**Operation system (OS) level DNS caching**
- 운영체제 수준의 DNS resolver는 DNS 쿼리가 시스템을 떠나기 전 두번째이자 마지막 정거장입니다. 운영체제 내에서 쿼리를 처리하도록 디자인된 프로세스를 일반적으로 **stub cleanver**나 DNS 클라이언트라 합니다.
- **stub resolver**가 어플리케이션으로부터 요청을 받으면, 먼저 캐시를 확인해 레코드를 가지고 있는지 확인합니다.
- 그렇지 않다면, DNS 쿼리 (재귀 플래그가 설정된 경우)를 로컬 네트워크 외부의 ISP(인터넷 서비스 공급업체) 내부의 DNS recursive resolver로 전송합니다.

**Recursive resolver DNS caching**
- ISP 내부의 recursive resolver가 DNS 쿼리를 받을 때, 요청된 호스트-IP 변환이 로컬 지속 계층에 이미 저장되어있는지 확인합니다.
- Recursive resolver는 또한 캐시에 있는 레코드의 유형에 따라 아래와 같은 추가적인 기능을 가지고 있습니다.
  1. Resolver에 A 레코드가 없지만 Authoritative nameserver에 대한 NS 레코드가 있는 경우 DNS 쿼리의 여러 단계를 거치지 않고 바로 해당 네임서버로 쿼리합니다. 이 길은 루트 밑 .com 네임서버 (예: example.com 검색)에서 조회를 방지하고 DNS 쿼리의 해결이 더 빨리 이루어지도록 도와줍니다.
  2. Resolver가 NS 레코드를 가지고 있지 않다면, TLD 서버로 쿼리를 전송하여 루트 서버를 건너뜁니다.
  3. Resolver가 TLD 서버를 가리키는 레코드를 가지고 있지 않으면, 루트 서버를 쿼리합니다. 이 이벤트는 일반적으로 DNS 캐시가 삭제된 이후에 발생합니다.
  
### Reference
  [What is dns?](https://www.cloudflare.com/learning/dns/what-is-dns/)
