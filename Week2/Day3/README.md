1) Find the index of the first occurence of a string
class Solution {
    public int strStr(String haystack, String needle) {
      for(int i=0;i<=haystack.length()-needle.length();i++) {
        int j =0;
        while(j<needle.length() && haystack.charAt(i+j)==needle.charAt(j)){
            j++;
        }
        if(j==needle.length()){
            return i;
        }
      }
      return -1;
    }
}

2) Is subsequence
   class Solution {
    public boolean isSubsequence(String s, String t) {
      int i=0;
      int j =0;
      while(i<s.length() && j <t.length()){
        if(s.charAt(i)==t.charAt(j)){
            i++;
        }
        j++;
      }  
      return i==s.length();
    }
}

3) Repeated substring pattern
   class Solution {
    public boolean repeatedSubstringPattern(String s) {
    int n =s.length();
    for(int len=1; len<=n/2; len++){
        if(n % len==0){
            String sub=s.substring(0,len);
            StringBuilder sb= new StringBuilder();
            int times= n/len;
            for(int i=0; i<times; i++){
                sb.append(sub);
            }
            if(sb.toString().equals(s)){
                return true;
            }
        }
    }  
    return false; 
    }
}
