:date: 2021.02.07

## 문제
#### Cos Pro 1급 Java 예시 6회
```java
// 다음과 같이 import를 사용할 수 있습니다.
import java.util.*;

class Solution {	
    public String solution(String s1, String s2, int p, int q) {
        // 여기에 코드를 작성해주세요.
        String answer = "";
        
        StringBuilder sb = new StringBuilder();
        StringBuilder new_s1 = sb.append(s1).reverse();
        int idx = 0;
        double ten_s1 = 0;
        while(idx < new_s1.length()) {
        	ten_s1 += Integer.parseInt(Character.toString(new_s1.charAt(idx))) * (Math.pow(p, idx));
        	idx++;
        }
        
        StringBuilder sb2 = new StringBuilder();
        StringBuilder new_s2 = sb2.append(s2).reverse();
        idx = 0;
        double ten_s2 = 0;
        while(idx < new_s2.length()) {
        	ten_s2 += Integer.parseInt(Character.toString(new_s2.charAt(idx))) * (Math.pow(p, idx));
        	idx++;
        }
        
        System.out.println("s1: "+ten_s1+" s2: "+ten_s2);
        int num = (int)(ten_s1+ten_s2);
        System.out.println("num: "+num);
        
        StringBuilder number = new StringBuilder();
        while(num != 1) {
        	number.append(num%q);
        	num /= q;
        }
        
        number.append("1");
        answer = number.reverse().toString();
        
        
        return answer;
    }
    
    // 아래는 테스트케이스 출력을 해보기 위한 main 메소드입니다.	
    public static void main(String[] args) {
    	Solution sol = new Solution();
    	String s1 = new String("112001");
        String s2 = new String("12010");
        int p = 3;
        int q = 8;
    	String ret = sol.solution(s1, s2, p, q);
    	
        // [실행] 버튼을 누르면 출력 값을 볼 수 있습니다.
        System.out.println("solution 메소드의 반환 값은 " + ret + " 입니다.");
   }
}
```

음..코드 더럽^^..
