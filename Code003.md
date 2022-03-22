# SNMP (Simple Network Management Protocol) 

네트워크 망 관리를 위한 NMS(Network Management System), SMS(System Management System) 사용 시 필요한 프로토콜로, 즉 TCP/IP 프로토콜을 사용하는 네트워크에 있는 단말관리를 위한 프로토콜이다. MIB / OID 값을 가지고 정보를 수집한다.

	*	MIB (Management Information Base) : OID가 갖고 있는 값 (VALUE)
    
	*	OID (Object Identifier) : SNMP에 의해 관리될 수 있는 단말의 규격 정보를 담고있는 KEY (숫자 형식으로 설정 )
    

**특징** : 정보 지향적이며 특정 정보 변수에 대한 단순한 요청/응답 메카니즘을 갖고있다 (Get/Set/Trap)

*	모든 단말에 대한 통신을 지원하지 않는다



**장비** : 관리하는 시스템(Manger)과 관리되는 장비(Agent)로 구분된다

**프로토콜** : UDP / 161(메세지 전송 포트) 162(트랩 메세지 전송)

**Trap / Inform** : 네트워크 단말에서 Event 발생 시, Manager이 요청하지 않더라도 스스로 발생되는 메세지


![image](https://user-images.githubusercontent.com/73813647/158713529-187bd8d9-c207-4aac-abb8-5259b9cb4f34.png)

< 출처 : http://www.ktword.co.kr/test/view/view.php?m_temp1=2483 >

# TR-069 (Technical Report 069)

**CPE WAN Management Protocol** 로 정의되며 양방향 SOAP/HTTP를 기반으로 CPE와 ACS 간 통신을 가능하게 하는 프로토콜이다. SNMP 프로토콜 이후 생성되었다.

	*	CPE (customer premises equipment) : 댁내 단말(셋톱박스, 인터넷전화 등)
	*	WAN (Wide Area Network) : LAN과 LAN사이를 연결하는 네트워크. 주로 ISP를 통해 이용한다
	*	LAN (Local Area Network) : 한정된 공간에 네트워크를 구성한것으로 스위치 또는 공유기를 기준으로 형성된 네트워크
	*	ISP (Internet Service Provider) : 인터넷 제공 기업(국내의 SKT, KT, LGU+)
	*	ASC (Auto Configuration Servers) : 자동 설정 서버(정확한 의미를 구글링하기 어려워, 우선 시스템 서버로 이해한다)

*	TR-069는 모든 CPE와 통신하기 위한 규격이다
*	다양한 명령을 지원한다 (Get/Set/Trap/Create/Delete/File download/File Upload/...)
*	SNMP는 데이터 모니터링을 지원하지 않지만, TR-069는 지원한다

![image](https://user-images.githubusercontent.com/73813647/158723715-51bf4054-438b-43c9-9ae0-5d4fabc569b3.png)
