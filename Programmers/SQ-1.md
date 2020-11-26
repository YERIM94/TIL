:date: 2020.11.26

## 문제
SQ(스택/큐)-1.주식가격

## Code
```java
class Solution {
    public int[] solution(int[] prices) {
        int[] answer = new int[prices.length];
        
        for(int i=0;i<prices.length;i++) {
        	int count = 0;
        	
        	if(i == prices.length-1) {
        		answer[i] = 0;
        		return answer;
        	}
        		
        	for(int j=i+1;j<prices.length;j++) {
        		if(prices[i]<=prices[j]) {
        			count++;
        			continue;
        		} else {
        			count++;
        			break;
        		}
        	}
        	answer[i] = count;
        }
        
        return answer;
    }
}
```
stack/queue 사용안했는데 통과,,
