:date: 2020.12.10

## 문제
Cos Pro 1급 Java
</br>Part3-3. 메모장

## Code
```java
// 다음과 같이 import를 사용할 수 있습니다.
import java.util.*;

class Solution {
    public int solution(int K, String[] words) {
        int line = 0;
        int word = 0;
        int i=0;
        int start = words[0].length();
        
        while(i<words.length){
        	if(i==0) {
        		word += start;
        	}
        	
        	if(word > K){
                line++;
                if(i == words.length-1) {
                	line++;
                	return line;
                }
                word = words[i].length();
            }else if(word == K){
            	if(i == words.length-1) {
                	line++;
                	return line;
                }
                line++;
                i++;
                word = words[i].length();
            }else if(word < K){
            	if(i == words.length-1) {
                	line++;
                	return line;
                }
                i++;
                word += words[i].length()+1;
            }
        }
        return line;
    }

    // 아래는 테스트케이스 출력을 해보기 위한 main 메소드입니다.
    public static void main(String[] args) {
        Solution sol = new Solution();
        int K = 10;
        String[] words = {new String("nice"), new String("happy"), new String("hello"), new String("world"), new String("hi")};
        int ret = sol.solution(K, words);

        // [실행] 버튼을 누르면 출력 값을 볼 수 있습니다.
        System.out.println("solution 메소의 반환 값은 " + ret + " 입니다.");
    }
}
```
</br>
코드 개더럽^^ 이건 푼거라고 할 수도 없다 아오씨
