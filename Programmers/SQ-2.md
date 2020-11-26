:date: 2020.11.26

## 문제
SQ-2. 기능개발

## Code
```java
import java.util.LinkedList;
import java.util.Queue;
class Solution {
    public int[] solution(int[] progresses, int[] speeds) {
        int[] workday = new int[progresses.length];
        Queue<Integer> q = new LinkedList<>();
        
        for(int i=0;i<progresses.length;i++) {
        	int work = (100-progresses[i])/speeds[i];
        	int work2 = (100-progresses[i])%speeds[i];
        	if(work2 != 0) {
        		workday[i] = work+1;
        	} else {
        		workday[i] = work;
        	}
        	q.add(workday[i]);
        }
        
        Queue<Integer> result = new LinkedList<>();
        while(!q.isEmpty()) {
        	int count = 1;
        	int start = q.poll();
        	while(q.peek()!=null && start>=q.peek()) {
        		count++;
        		q.poll();
        	}
        	result.add(count);
        }
        
        int[] answer = new int[result.size()];
        int i=0;
        while(!result.isEmpty()) {
        	answer[i] = result.poll();
        	i++;
        }
        
        return answer;
    }
}
```
