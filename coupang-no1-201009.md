:date: 2020.10.09

## 문제
Coupang Tech Campus Recruiting Test - 1. 자릿수 곱(통과)

## Code
```java
import java.lang.*;

class Solution { 
  public int[] solution (int N) {
  int k = 2; 
  int mulNum = 1;
  
  for(int i=2; i<10; i++) {
    StringBuilder sb = new StringBuilder();
    sb = changer(N, i); 
    
    int mulSb = multiply(sb); 
    if(mulSb > mulNum) {
      k = i;
      mulNum = mulSb;
    } else if (i>k && mulSb == mulNum) {
      k = i;
      }
    }
      int[] answer = {k, mulNum}; 
      return answer;
  }

  public int multiply(StringBuilder sb) {
    int result = 1; 
    for(int i=0;i<sb.length(); i++) {
      int num = Integer.parseInt(sb.substring(i,i+1)); 
        if(num!=0) {
          result *= num;
        }
     }
    return result;
  }
    
  public StringBuilder changer (int n, int k) {
    StringBuilder sb = new StringBuilder(); 
    int num = n; 
    int b = k;
    
    while(num != 0){
      long r = num % b; 
      if(r > 9) {
        sb.append((char) (r+55)); 
      } else{
        sb.append(r);
      }
      num = num/b;
    }
    return sb;
  }
}
```
