:date: 2020.11.25

## 문제
BP-1. 모의고사

## Code
```java
class Solution {
    public int[] solution(int[] answers) {
        int a = 0;
        int b = 0;
        int c = 0;
        
        int[] aAnswer = {1,2,3,4,5};
        int[] bAnswer = {2,1,2,3,2,4,2,5};
        int[] cAnswer = {3,3,1,1,2,2,4,4,5,5};
        
        for(int i=0;i<answers.length;i++) {
        	if(aAnswer[i%5] == answers[i]) {
        		a++;
        	}
        	if(bAnswer[i%8] == answers[i]) {
        		b++;
        	}
        	if(cAnswer[i%10] == answers[i]) {
        		c++;
        	}
        }
        
        
        int count = 0;
        String result = "";
        int max = Math.max(Math.max(a, b),c);
        if(max == a) { result += "1"; count++; }
        if(max == b) { result += "2"; count++; }
        if(max == c) { result += "3"; count++; }
        
        int[] answer = new int[count];
        String[] r = result.split("");
        for(int i=0;i<r.length;i++) {
        	answer[i] = Integer.parseInt(r[i]);
        }
        
        
        return answer;
    }
}
```
