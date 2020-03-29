# Stack,Queue

## 탑
<a href="https://programmers.co.kr/learn/courses/30/lessons/42588" target="_blank"> 문제 설명 <a>

#### 나의 코드 1
	def solution(heights):
	    
	    n = len(heights)
	    answer = [0 for _ in range(n)]
	    
	    for i in range(n-1, -1, -1):
	        for j in range(i, -1, -1):
	            if heights[i] < heights[j]:
	                answer[i] = j+1
	                break
	
	    return answer
	    
## 기능개발
<a href="https://programmers.co.kr/learn/courses/30/lessons/42586" target="_blank"> 문제 설명 <a>

#### 나의 코드 1
	import math
	
	def solution(progresses, speeds):
	    
	    if len(progresses) == 1:
	        return [1]
	
	    days_to_work = [int(math.ceil((100-progress)/speed)) for progress, speed in zip(progresses, speeds)]
	
	    answer = []
	    prev = days_to_work[0]
	    number_of_works = 1
	
	    for post in days_to_work[1:]:
	        
	        if prev < post:
	            answer.append(number_of_works)
	            number_of_works = 1
	            prev = post
	            
	        else:
	            number_of_works += 1 
	
	    answer.append(number_of_works)
	
	    return answer
	    