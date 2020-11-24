:date: 2020.11.24
## 문제
Hash-1. 완주하지 못한 선수

## Code
```java
import java.util.HashMap;
class Solution {
    public String solution(String[] participant, String[] completion) {
        String answer = "";
        
        HashMap<String, Integer> p = new HashMap<>();
		
		for(int i=0;i<participant.length;i++) {
			p.put(participant[i], p.getOrDefault(participant[i],0)+1);
		}
		
		for(int i=0;i<completion.length;i++) {
			if(p.containsKey(completion[i])){
				p.replace(completion[i],p.get(completion[i])-1);
			}
		}
		
		for(String key : p.keySet()) {
			if(p.get(key) != 0) {
				answer = key;
			}
		}
        
        return answer;
    }
}
```
