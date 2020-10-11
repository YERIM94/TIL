:date: 2020.10.09

## 문제
Coupang Tech Campus Recruiting Test - 3. 조작된 점수 제거하기(통과)

## Code
```java
import java.lang.*;
import java.util.*;

class solution {
  public int solution(int k, int[] score) {
  int answer = -1;

  int[] scoreDiff = scoreDiff (score); 
  int[][] dupCount = scoreCount(scoreDiff); 
  
  int i = 0; 
  while(i<dupCount.length) { 
    if(dupCount[i][0] != 0){
      break;
    }
    i++;
  }
  if(i==dupCount.length) {
    return 0;
  }

  answer = dupRemove(k, dupCount, scoreDiff); 
  return answer;
  }

  public int[] scoreDiff(int[] score) {
    int[] scorediff = new int[score.length]; 
    for(int i=0;i<score.length-1;i++) {
      scoreDiff[i+1] = score[i] - score[i+1];
    }
    return scoreDiff;
  }

  public int[][] scoreCount(int[] scoreDiff) {
    ArrayList<Integer> arrayList = new ArrayList<Integer>(); 

    for(int data:scoreDiff){ 
      if(!arrayList.contains (data)) {
        arrayList.add(data);
      }
    }

    int[][] dupCount = new int[arrayList.size()][2]; 
    for(int i=0; i<arrayList.size(); i++) {
      dupCount[i][0] = arrayList.get(i);
    }

    for(int i=0; i<scoreDiff.length; i++) {
      for(int y=0; y<dupCount.length;y++) {
        if(scoreDiff[i] == dupCount[y][0]) {
          dupCount[y][1] += 1;
        }
      }
    }

    return dupCount;
  }

  public int dupRemove(int k, int[][] dupCount, int[] scoreDiff) {
    int[] people = new int[scoreDiff.length]; 
    for (int i=0;i<dupCount.length; i++) { 
      if(dupCount[i][1] >= k) { 
        for (int x=1;x<scoreDiff.length;x++) { 
          if (dupCount[i][0] == scoreDiff[x]) {
            people[x-1] = 1; 
            people[x] = 1;
          }
        }
      }
    }

    int cnt = people.length; 
    for (int i=0;i<people.length; i++) { 
      if (people[i] == 1){
        cnt = cnt-1;
      }
    }
    return cnt;
  }
}
```
