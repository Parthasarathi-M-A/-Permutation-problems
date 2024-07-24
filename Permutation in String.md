### Permutation in String
Given two strings s1 and s2, return true if s2 contains a permutation of s1, or false otherwise.

In other words, return true if one of s1's permutations is the substring of s2.

### Example 1:
#### Input:
s1 = "ab", s2 = "eidbaooo"
#### Output:
true
#### Explanation: 
s2 contains one permutation of s1 ("ba").
### Example 2:
#### Input: 
s1 = "ab", s2 = "eidboaoo"
#### Output: 
false
### Code :
``` java
class Solution {
    public static boolean checkInclusion(String s1, String s2) {
        for(int i=0;i<=s2.length()-s1.length();i++){
            if(anagram(s1,s2.substring(i,i+s1.length())))return true;
        }
        return false;
    }
    public static boolean anagram(String s1,String s2){
        int[] ana=new int[26];
        for(int i=0;i<s1.length();i++){
            ana[s1.charAt(i)-'a']++;
            ana[s2.charAt(i)-'a']--;
        }
        for(int i=0;i<ana.length;i++)if(ana[i]!=0)return false;
        return true;
    }
  public static void main(String[] args){
   String s1="ab";
   String s2="eidboaoo";
   System.out.println(checkInclusion(s1,s2));
  }
}
```
 
