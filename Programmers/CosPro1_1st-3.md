:date: 2020.12.10

## 문제
Cos Pro 1급 Java 예시 1회

## Code
```java
// You may use import as below.
//import java.util.*;

class Solution {
    public int solution(String pos) {
        // Write code here.
        String[][] board = new String[8][8];
        String column = pos.subString(0,1);
        int row = pos.subString(1,1);
        int col = 0;

        switch(column){
            case "A" :
            col = 0;
            break;

            case "B" :
            col = 1;
            break;

            case "C" :
            col = 2;
            break;

            case "D" :
            col = 3;
            break;

            case "E" :
            col = 4;
            break;

            case "F" :
            col = 5;
            break;

            case "G" :
            col = 6;
            break; 

            case "H" :
            col = 7;
            break;

            case "I" :
            col = 8;
            break;

        }

        int count = 0;
        int i = row;
        int j = col;

        if(i+2 < 8 && j+1 <8) count++;
        if(i+2 < 8 && j-1 >= 0) count++;
        if(i-2 >= 0 && j+1 <8) count++;
        if(i-2 >= 0 && j-1 >= 0) count++;
        if(j+2 < 8 && i+1 <8) count++;
        if(j+2 < 8 && i-1 >= 0) count++;
        if(j-2 >= 0 && i+1 <8) count++;
        if(j-2 >= 0 && i-1 >= 0) count++;

        return count;
    }


    // The following is main method to output testcase.
    public static void main(String[] args) {
        Solution sol = new Solution();
        String pos = "A7";
        int ret = sol.solution(pos);

        // Press Run button to receive output. 
        System.out.println("Solution: return value of the method is " + ret + " .");
    }
}
```
