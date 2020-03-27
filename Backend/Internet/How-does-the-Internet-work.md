## 인터넷은 어떻게 작동될까요?

**Summary (요약)**
- **Internet**은 웹(**Web**)의 핵심적인 기술로, 웹을 가능하게 하는 기술 인프라입니다.
- 기본적으로, 인터넷은 모두 함께 통신하는 대규모 컴퓨터 네트워크입니다.
- 인터넷은 1960년대 미군이 기금을 조성한 연구 프로젝트로 시작되어, 1980년대 많은 국립 대학과 사기업의 지원으로 인해 공공 인프라로 발전하였습니다.
- 인터넷을 지원하는 다양한 기술들은 시간이 지남에 따라 발전했지만, 그 동작 방식은 크게 변하지 않았습니다.
- 인터넷은 컴퓨터를 모두 연결하고, 무슨 일이 있어도 연결 상태를 유지할 수 있는 방법을 찾는 방법입니다.

**A simple network (단순한 네트워크)**
- 두 대의 컴퓨터가 통신해야 할 때 물리적(**이더넷 케이블**) 또는 무선(**Wi-fi** 또는 **Bluetooth** 등)으로 연결해야 합니다.
- 모든 현대의 컴퓨터들은 이러한 연결 중 하나를 이용하여 연결을 지속할 수 있습니다.
  ![How-does-the-Internet-work-1](https://github.com/wooogi123/Development_Roadmap/blob/master/Backend/Internet/images/How-does-the-Internet-work-1.png)
- 이러한 네트워크는 두 대의 컴퓨터로 제한되지 않고 원하는 만큼의 컴퓨터를 연결할 수 있습니다. 하지만 연결할수록 매우 복잡해집니다.
- 예를 들어, 10대의 컴퓨터를 연결하려는 경우, 컴퓨터 당 9개의 플러그가 있는 45개의 케이블이 필요합니다.
  ![How-does-the-Internet-work-2](https://github.com/wooogi123/Development_Roadmap/blob/master/Backend/Internet/images/How-does-the-Internet-work-2.png)
- 이 문제를 해결하기 위해 네트워크의 각 컴퓨터는 라우터(**Router**)라는 특수한 소형 컴퓨터에 연결됩니다.
- 이 라우터는 단 하나의 작업만을 가지고 있는데, 지정된 컴퓨터에서 보낸 메세지가 올바른 대상 컴퓨터에 도착하는지 확인합니다.
- B 컴퓨터에게 메세지를 보내려면 A 컴퓨터가 메세지를 라우터로 보내야 하며, 라우터는 메세지를 B 컴퓨터로 전달하고 메세지가 C 컴퓨터로 배달되지 않고록 해야합니다.
- 이 라우터를 시스템에 추가하면 10대의 컴퓨터 네트워크에는 10개의 케이블만 필요하고, 각 컴퓨터마다 단일 플러그와 10개의 플러그가 있는 하나의 라우터가 필요합니다.
  ![How-does-the-Internet-work-3](https://github.com/wooogi123/Development_Roadmap/blob/master/Backend/Internet/images/How-does-the-Internet-work-3.png)
  
**A network of network (네트워크의 네트워크)**
- 소규모의 컴퓨터를 연결하는 것은 괜찮지만 수백, 수천, 수십억 대의 컴퓨터를 연결하는 것은 어떨까요?
- 하나의 라우터가 그 정도까지는 확장할 수 없습니다. 하지만, 라우터는 다른 컴퓨터와 마찬가지로 컴퓨터입니다.
- 즉, 두 대의 라우터를 서로 연결할 수 있습니다.
  ![How-does-the-Internet-work-4](https://github.com/wooogi123/Development_Roadmap/blob/master/Backend/Internet/images/How-does-the-Internet-work-4.png)
- 컴퓨터를 라우터에 연결한 다음, 라우터를 라우터에 연결하면 무한히 확장할 수 있습니다.
  ![How-does-the-Internet-work-5](https://github.com/wooogi123/Development_Roadmap/blob/master/Backend/Internet/images/How-does-the-Internet-work-5.png)
- 이러한 네트워크는 우리가 인터넷이라고 하는 것과 아주 유사하지만, 무엇인가 빠져있습니다.
- 우리는 목적을 가지고 네트워크를 구축했습니다. 하지만, 그 밖에 다른 사람들 - 친구, 이웃 누구든지 - 컴퓨터로 이루어진 그들만의 네트워크를 가질 수 있습니다.
- 우리의 네트워크와 다른 지역 사이에 이더넷 케이블을 연결할 수는 없습니다.
- 이 문제를 어떻게 처리할 수 있을까요?
- 이미 사람들의 집에는 전력과 전화 케이블이 연결되어 있습니다. 전화 인프라는 전 세계의 모든 사람과 집을 연결하므로, 우리가 필요로 하는 완벽한 케이블입니다.
- 우리의 네트워크를 전화 인프라에 연결하기 위해서는, 모뎀(**Modem**)이라는 특수 장비가 필요합니다.
- 모뎀은 우리 네트워크의 정보를 전화 인프라에서 처리 할 수 있는 정보로 바꾸며, 그 반대의 경우도 마찬가지입니다.
  ![How-does-the-Internet-work-6](https://github.com/wooogi123/Development_Roadmap/blob/master/Backend/Internet/images/How-does-the-Internet-work-6.png)
- 그렇게 우리의 네트워크는 전화 인프라에 연결됩니다.
- 다음 단계는 우리의 네트워크에서 도달하고자 하는 네트워크로 메세지를 보내는 것입니다.
- 이를 위해, 네트워크를 ISP(**인터넷 서비스 제공 사업자**)에 연결합니다.
- ISP는 서로 연결된 특수한 라우터를 관리하고, ISP의 라우터에도 액세스 할 수 있는 회사입니다.
- 따라서 우리 네트워크의 메세지는 ISP 네트워크의 네트워크를 통해 대상 네트워크로 전달됩니다.
- 인터넷은 이러한 전체 네트워크의 인프라로 구성됩니다.
  ![How-does-the-Internet-work-7](https://github.com/wooogi123/Development_Roadmap/blob/master/Backend/Internet/images/How-does-the-Internet-work-7.png)

**Finding computers (컴퓨터 찾기)**
- 컴퓨터로 메세지를 보내는 경우, 메세지를 받을 대상 컴퓨터를 지정해야 합니다. 따라서 네트워크에 연결된 모든 컴퓨터에는 IP 주소(**Internet Protocol**)라고 하는 고유한 주소가 있습니다.
- **192.168.0.1** 과 같이 점으로 구분되어 있는 4개의 숫자로 구성된 주소입니다.
- IP 주소는 컴퓨터에게 완벽하지만, 사람은 그런 종류의 주소를 기억하기 어렵습니다.
- 그래서 사람이 읽을 수 있는, 도메인 네임이라는 IP 주소의 이름을 지정할 수 있습니다.
- 예를 들어, **google.com**은 IP 주소로 **173.194.121.31**입니다.
- 따라서, 도메인 네임을 사용하는 것이 인터넷을 통해 컴퓨터에 접근하는 가장 쉬운 방법입니다.

**Internet and the web (인터넷과 웹)**
- 웹 브라우저로 웹을 탐색할 때에는 일반적으로 도메인 네임을 사용해서 웹 사이트에 접속합니다.
- 그렇지만 인터넷과 웹이 같다고 하기엔 간단하지 않은 문제입니다.
- 인터넷은 수십억 대의 컴퓨터를 모두 연결하는 기술 인프라입니다.
- 이러한 컴퓨터 중 일부 컴퓨터(**웹 서버**)는 웹 브라우저가 이해할 수 있는 메세지를 보낼 수 있습니다.
- 즉, **Internet**은 인프라이며, **Web**은 인프라를 기반으로 구축된 서비스입니다.
- 웹 뿐만 아니라, 인터넷을 기반으로 구축된 몇 가지 다른 서비스들 (이메일 및 IRC 등등)도 있습니다.
