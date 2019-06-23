// you can also use imports, for example: import java.util.*;

// you can write to stdout for debugging purposes, e.g. // System.out.println("this is a debug message");

class Solution {
 public int solution(int[] A) {

  if (A.length <= 1)
   return 0;

  int least = A[0];
  int highest = 0;
  int profit = 0;

  for (int i = 1; i < A.length; i++) {
   Boolean flag = false;

   if (A[i] > highest)
    highest = A[i];

   if (A[i] < least) {

    for (int j = i + 1; j < A.length; j++) {

     if ((A[j] - A[i]) > profit) {
      highest = A[j];
      flag = true;
      break;
     }
    }
    if (flag)
     least = A[i];

   }
   profit = highest - least;
  }




  if (profit > 0) {
   return profit;
  } else {
   return 0;
  }
 }
}
