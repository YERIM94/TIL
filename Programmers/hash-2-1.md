:date: 2020.11.25
## 문제
Hash-2-1. 전화번호 목록

## Code
```java
class Solution {
    public boolean solution(String[] phone_book) {
        boolean answer = true;
        
         for(int i=0;i<phone_book.length-1;i++) {
			for(int x=i+1;x<phone_book.length;x++) {
				if(phone_book[x].startsWith(phone_book[i])) { return false; }
        if(phone_book[i].startsWith(phone_book[x])) { return false; }
			}
		}
		
        return answer;
    }
}
```

왜 hash카테고리에 들어가있을까...
