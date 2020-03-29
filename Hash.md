# Stack,Queue

## 탑
<a href="https://programmers.co.kr/learn/courses/30/lessons/42576" target="_blank"> 문제 설명 <a>

#### 나의 코드 1
hash를 이용하지 않았다.

	def solution(participant, completion):
	
	   participant.sort()
	   completion.sort()
	
	   for p, c in zip(participant, completion):
	       if p != c:
	           return p
	   
	   return participant[-1]


#### 나의 코드 2
hash를 이용하였다.

	def solution(participant, completion):
	
	    answer = ''
	    temp = 0
	    dic = {}
	    
	    for p in participant:
	        dic[hash(p)] = p
	        temp += int(hash(p))

	    for c in completion:
	        temp -= hash(c)
	        
	    answer = dic[temp]
	
	    return answer
