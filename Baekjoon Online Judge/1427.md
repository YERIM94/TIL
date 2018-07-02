## 문제
- 180314
- 백준알고리즘
- 1427번 소트인사이드

## 코드
```java
import java.util.Scanner;

public class hi {
	public static void main(String[] args){
		Scanner scan = new Scanner(System.in);
		double num = scan.nextInt();
		double num_copy = num;
		int count = 0;
		int temp;
		int a=0;
		
		while(num>=1){
			num/=10;
			count++;
		}
		
		int[] array = new int[count];
		
		while(num_copy>=1){
		
			array[a] = (int)(num_copy%10);
			num_copy/=10;
			
			a++;
		}
		
		for(int x=array.length-1;x>=1;x--){
			for(int i=0;i<x;i++){
				if(i!=(array.length-1) && (array[i]<=array[i+1])){
					temp = array[i+1];
					array[i+1] = array[i];
					array[i] = temp;
				}
			}	
		}
		
		for(int i=0; i<array.length;i++){
			System.out.print(array[i]);
		}
	}
}
```
