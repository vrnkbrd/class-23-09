# class-23-09
Task: If we list all the natural numbers below 10 that are multiples of 3 or 5, we get 3, 5, 6 and 9. The sum of these multiples is 23.
Finish the solution so that it returns the sum of all the multiples of 3 or 5 below the number passed in. Additionally, if the number is negative, return 0 (for languages that do have them).
Note: If the number is a multiple of both 3 and 5, only count it once. 

My solution:
public class Solution {

  public int solution(int number) {
    int k = 0;
    int sum=0;
    while (k<number){
      if (k%3==0) sum=sum+k;
      else if (k%5==0) sum=sum+k;
      k=k+1;
    }
    return sum;
  
  }
}
Fav solution:
import java.util.stream.*;

public class Solution {

  public int solution(int number) {
    return IntStream.range(3, number).filter(n -> n % 3 == 0 || n % 5 == 0).sum();
  }
}
Actually there is the same algorithm but the autor used streams and it seems interesting

Diff: 6 

Task: Given an array of integers, find the one that appears an odd number of times.

There will always be only one integer that appears an odd number of times.

My solution: 
public class FindOdd {
	public static int findIt(int[] a) {
    int odd=0;
    int[]b=new int[a.length];
    for (int i=0; i<a.length; i++){
      for (int j=0; j<a.length; j++){
        if (a[i]==a[j]) b[i]=b[i]+1;
      }
    }
    for (int k=0; k<b.length; k++){
      if (b[k]%2==1) odd=a[k];
    }
  	return odd;
  }
}
Fav solution:
import static java.util.Arrays.stream;

public class FindOdd {
  public static int findIt(int[] arr) {
    return stream(arr).reduce(0, (x, y) -> x ^ y);
  }
}
