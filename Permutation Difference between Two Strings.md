### Permutation Difference between Two Strings
You are given two strings s and t such that every character occurs at most once in s and t is a permutation of s.

The permutation difference between s and t is defined as the sum of the absolute difference between the index of the occurrence of each character in s and the index of the occurrence of the same character in t.

Return the permutation difference between s and t.
### Example 1:

#### Input: 
s = "abc", t = "bac"

#### Output:
2

#### Explanation:

For s = "abc" and t = "bac", the permutation difference of s and t is equal to the sum of:

The absolute difference between the index of the occurrence of "a" in s and the index of the occurrence of "a" in t.
The absolute difference between the index of the occurrence of "b" in s and the index of the occurrence of "b" in t.
The absolute difference between the index of the occurrence of "c" in s and the index of the occurrence of "c" in t.
That is, the permutation difference between s and t is equal to |0 - 1| + |2 - 2| + |1 - 0| = 2.
### Code :
``` java 
class Solution {
    public int findPermutationDifference(String s, String t) {
        int ans=0;
        for(int i=0;i<s.length();i++)ans+=Math.abs(i-t.indexOf(s.charAt(i)));
        return ans;
    }
  public static void main(String[] args){
     String s="abc";
     String y="bac";
     System.out.println(findPermutationDifference(s,t));
   }
}
```
