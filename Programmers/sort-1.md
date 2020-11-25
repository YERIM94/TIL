:date: 2020.11.25

## 문제
sort-1. K번째 수

## Code
```java
import java.util.Arrays;
class Solution {
    public int[] solution(int[] array, int[][] commands) {
        int[] answer = new int[commands.length];
		
        for(int i=0;i<commands.length;i++) {
        	int start = commands[i][0];
        	int end = commands[i][1];
        	
        	int[] newArray = new int[end-start+1];
        	
        	for(int x=0;x<end-start+1;x++) {
        		newArray[x] = array[x-1+start];
        	}
        	
        	Arrays.sort(newArray);
        	answer[i] = newArray[commands[i][2]-1];
        }
        
        return answer;
    }
}
```
