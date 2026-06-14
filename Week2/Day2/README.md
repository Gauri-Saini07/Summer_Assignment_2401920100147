Day2_Work
1) Longest Substring without repeating characters
   class Solution {
    public int lengthOfLongestSubstring(String s) {
        //longest substring
       HashSet<Character> set=new HashSet<>();
       int left=0;
       int maxlen=0;
       for(int right=0;right<s.length();right++){
        while(set.contains(s.charAt(right))){
            set.remove(s.charAt(left));
            left++;
        }
        set.add(s.charAt(right));
        maxlen=Math.max(maxlen,right-left+1);
       } 
       return maxlen;
    }
}

2) Permutation in string
   class Solution {
    public boolean checkInclusion(String s1, String s2) {
        if(s1.length()>s2.length()){
            return false;
        }
        int[] count1=new int[26];
        int[] count2=new int[26];
        for(int i =0;i<s1.length();i++){
            count1[s1.charAt(i)-'a']++;
            count2[s2.charAt(i)-'a']++;
        }
        if(matches(count1,count2)){
            return true;
        }
        for(int i=s1.length();i<s2.length();i++){
            count2[s2.charAt(i)-'a']++;
            count2[s2.charAt(i-s1.length())-'a']--;
            if(matches(count1,count2)){
                return true;
            }
        }
        return false; 
        }
        private boolean matches(int[]count1,int[]count2){
            for(int i=0;i<26;i++){
                if(count1[i]!=count2[i]){
                    return false;
                }
            }
            return true;
        }
   }

   3)Find all anagrams in a string
   class Solution {
    public List<Integer> findAnagrams(String s, String p) {
      List<Integer> result=new ArrayList<>();
      if(p.length()>s.length()){
        return result;
      } 
      int[] pCount= new int[26];
      int[] windowCount=new int[26];
      for(int i =0;i<p.length();i++){
        pCount[p.charAt(i)-'a']++;
        windowCount[s.charAt(i)-'a']++;
      } 
      if(matches(pCount,windowCount)){
        result.add(0);
      }
      for(int i=p.length();i<s.length();i++){
        windowCount[s.charAt(i)-'a']++;
        windowCount[s.charAt(i-p.length())-'a']--;
        if(matches(pCount,windowCount)){
            result.add(i-p.length()+1);
        }
      }
      return result;
    }
    private boolean matches(int[]a,int[]b){
        for(int i=0;i<26;i++){
            if(a[i]!=b[i]){
                return false;
            }
        }
        return true;
    }
}
