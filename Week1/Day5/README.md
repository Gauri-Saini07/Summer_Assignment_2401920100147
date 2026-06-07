Day5_work
1) Valid Palindrome
  class Solution {
    public boolean isPalindrome(String s) {
        //valid palindrome
       int left=0;
       int right =s.length()-1;
       while(left< right){
       while(left<right && !Character.isLetterOrDigit(s.charAt(left))){
              left++;
           }
           while(left< right && !Character.isLetterOrDigit(s.charAt(right))){
            right--;
           }
           if(Character.toLowerCase(s.charAt(left))!=Character.toLowerCase(s.charAt(right))){
            return false;
           }
       left++;
       right--;
       } 
       return true;
    }
}

2) Reverse String
class Solution {
    public void reverseString(char[] s) {
        // reverse string
    int left=0;
    int right=s.length-1;
    while(left<right){
        char temp= s[left];
        s[left]=s[right];
        s[right]=temp;
        left++;
        right--;
    }
    }
}

3) Longest Common Prefix
class Solution {
    public String longestCommonPrefix(String[] strs) {
        //LONGEST COMMON PREFIX
        String prefix= strs[0];
        for( int i =1;i<strs.length;i++){
            while(!strs[i].startsWith(prefix)){
                prefix=prefix.substring(0,prefix.length()-1);
            }
        }
        return prefix;
    }
}
