#	Load balancing

컴퓨터 네트워크 기술의 일종으로 중앙처리장치 및 저장장치와 같은 컴퓨터 자원들에게 작업을 분산하는것을 의미한다

증가하는 트래픽을 대처할 수 있는 방법은 다음과 같다.

		Scale up : 서버 성능자체를 향상시키는 것.
    
		Scale out : 여러대의 서버를 두는것
    

이때 Scale out 방식을 사용할 때 로드 밸런싱이 필요하다.


*	Round Robin
	*	순차적으로 연결된 서버로 분산

*	Least Connction
	*	연결 갯수가 가장 적은 서버를 선택
	*	트래픽으로 인해 세션이 길어지는 경우 권장

*	Source
	*	사용자의 IP를 hashing하여 분배하는 방식
	*	사용자는 항상 같은 서버로 연결되는것을 보장

![image](https://user-images.githubusercontent.com/73813647/159228798-ce37d56c-34d3-4df5-b794-4d242b8a048f.png)
