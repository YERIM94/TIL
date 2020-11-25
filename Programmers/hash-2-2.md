:date: 2020.11.25
## 문제
Hash-2-2. 위장

## Code
```java
import java.util.HashMap;
class Solution {
    public int solution(String[][] clothes) {
        int answer = 1;
        
        HashMap<String, Integer> c = new HashMap<>();
        
        for(int i=0;i<clothes.length;i++) {
        	c.put(clothes[i][1], c.getOrDefault(clothes[i][1], 0)+1);
        }
        
        for(int count : c.values()) {
        	answer *= (count+1);
        }
        
        answer -= 1;
        return answer;
    }
}
```
</br>
내 머리로 푼 거 아님..^^..
</br>수학적 사고력 다 중동 갔나보다.
</br>간단해 보이는데 내 머리론 도저히 생각 안남 흑흑.
</br>이렇게 푼 사람 천재같다 진짜ㅠㅠ
