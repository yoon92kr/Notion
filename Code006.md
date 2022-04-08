


완주하지 못한 선수

출처 : https://programmers.co.kr/learn/courses/30/lessons/42576


# 문제 설명


수많은 마라톤 선수들이 마라톤에 참여하였습니다. 단 한 명의 선수를 제외하고는 모든 선수가 마라톤을 완주하였습니다.

마라톤에 참여한 선수들의 이름이 담긴 배열 participant와 완주한 선수들의 이름이 담긴 배열 completion이 주어질 때, 완주하지 못한 선수의 이름을 return 하도록 solution 함수를 작성해 주세요.



# 제한사항


· 마라톤 경기에 참여한 선수의 수는 1명 이상 100,000명 이하입니다.

· completion의 길이는 participant의 길이보다 1 작습니다.

· 참가자의 이름은 1개 이상 20개 이하의 알파벳 소문자로 이루어져 있습니다.

· 참가자 중에는 동명이인이 있을 수 있습니다.



# 입출력 예


0열 선택0열 다음에 열 추가
1열 선택1열 다음에 열 추가
2열 선택2열 다음에 열 추가
0행 선택0행 다음에 행 추가
1행 선택1행 다음에 행 추가
2행 선택2행 다음에 행 추가
3행 선택3행 다음에 행 추가
셀 전체 선택
열 너비 조절
행 높이 조절
participant

completion

return

["leo", "kiki", "eden"]

["eden", "kiki"]

"leo"

["marina", "josipa", "nikola", "vinko", "filipa"]

["josipa", "filipa", "marina", "nikola"]

"vinko"

["mislav", "stanko", "mislav", "ana"]

["stanko", "ana", "mislav"]

"mislav"

셀 병합
행 분할
열 분할
너비 맞춤
삭제

# 입출력 예 설명


예제 #1

"leo"는 참여자 명단에는 있지만, 완주자 명단에는 없기 때문에 완주하지 못했습니다.

예제 #2

"vinko"는 참여자 명단에는 있지만, 완주자 명단에는 없기 때문에 완주하지 못했습니다.

예제 #3

"mislav"는 참여자 명단에는 두 명이 있지만, 완주자 명단에는 한 명밖에 없기 때문에 한 명은 완주하지 못했습니다.



# 1차 시도


import java.util.HashMap;
import java.util.Map;

class Solution {
    public String solution(String[] participant, String[] completion) {
               
        String answer = "";
        Map<String, String> participantMap = new HashMap<String, String>();
        Map<String, String> completionMap = new HashMap<String, String>();

        // 인자로 받은 배열 객체를 HashMap 형태로 변환
        for(int i = 0 ; i < participant.length ; i++) {  
          
            participantMap .put(Integer.toString(i), participant[i]);   
         
        }
      
        for(int i = 0 ; i < completion.length ; i++) {    
        
            completionMap .put(Integer.toString(i), completion[i]);   
         
        }   
        
        for(int i = 0 ; i < participantMap.size() ; i++) {

            for(int j = 0 ; j < completionMap.size() ; j++) {

               // 출전 선수와 완주 선수가 일치할 경우, 해당 값들을 변경하여 동명이인을 방지
                if(participantMap.get(Integer.toString(i)).equals(completionMap.get(Integer.toString(j)))) {
                    participantMap.replace(Integer.toString(i), "!!");
                    completionMap.replace(Integer.toString(j), "@@");
                }

            }

        }
        
       for(int i = 0 ; i < participantMap.size(); i++) {  
      
           // 이전의 for 반복문에서 변경한 값이 아닌 선수를 확인 후 반환
           if (participantMap.get(Integer.toString(i)) != "!!") {
               answer = participantMap.get(Integer.toString(i));
           }

       }
        
        return answer;
    }
}
내용을 입력하세요.

# 1차 시도 구현 설명


해당 문제에 대해 출전 선수 리스트의 각 원소를, 완주한 선수 리스트와 비교하며 출전 선수 리스트에서 하나씩

제외하고자 하였다.

그리하여 최종적으로 남게 되는 하나의 원소가 완주하지 못한 선수가 됨으로 정확한 답을 추출해 낼 수 있을 것이라 판단하였고 배열 객체의 각 원소들을 비교하는 것은 가능하더라도, 재배치 및 삭제가 불가능하기에 HashMap으로 구현을 하였다.


# 1차 시도 테스트 결과



사진 삭제
사진 설명을 입력하세요.

# 1차 시도 채점 결과



사진 삭제
사진 설명을 입력하세요.


﻿
