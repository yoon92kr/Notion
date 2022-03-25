
# Hole Punching

*	일반적으로 P2P 연결을 하기위해선 서로의 IP와 PORT를 알아야 연결이 가능하지만, 사설IP를 사용하는 NAT는 연결이 어렵다.

*	여기서 Relay서버가 다리역할을 하여, 클라이언트의 NAT 정보를 확인 후 클라이언트간의 통신이 가능한 터널을 생성해준다.

#####	일반적인 P2P 구현을 위한 Hole punching 응용 예시
![image](https://user-images.githubusercontent.com/73813647/158103862-0a8be5e7-2d37-4aa4-b6b9-0e35d192eb18.png)

#####	서버와 단말 간의 Hole punching 응용 예시
![image](https://user-images.githubusercontent.com/73813647/160056366-5c49e8b7-c090-4785-97ea-1fe84c46d5ce.png)
위의 상황과 같이 단말에서 서버측에 데이터를 송신할때는 아무 문제가 없다.

![image](https://user-images.githubusercontent.com/73813647/160056378-5fe47c5d-c473-41ce-a1e5-7dc9b568a184.png)

그러나 NAT에서 해당 연결이 끝나고 난 뒤, NAT Table을 Timeout(초기화)를 시키기 때문에, 서버측에서 단말에 통신을 하기 위한 방법이 사라지게된다.
![image](https://user-images.githubusercontent.com/73813647/160056426-5ca1436c-c61a-488d-942f-875fb2881184.png)
그러므로 단말에서는 NAT Table 초기화 방지를 위해 지속적으로 서버에 패킷을 전송하고, 이를 통해 서버에서는 단말을 관리하기위한 IP를 알 수 있기 때문에 실시간 통신이 가능하게 된다.
