1) Group anagrams
   class Solution {
    public List<List<String>> groupAnagrams(String[] strs) {
        //group anagrams
       Map <String, List<String>> map=new HashMap<>();
       for(String str:strs){
        char[] arr=str.toCharArray();
        Arrays.sort(arr);
        String key=new String(arr);
        map.putIfAbsent(key,new ArrayList<>());
        map.get(key).add(str);
       }
       return new ArrayList<>(map.values()); 
    }
} 

2) String compression
   class Solution {
    public int compress(char[] chars) {
        //String compression
      int i =0;
      int index=0;
      while(i< chars.length){
        char curr=chars[i];
        int count=0;
        while(i<chars.length &&  chars[i]==curr){
            count++;
            i++;
        }
        chars[index++]=curr;
        if(count>1){
            String str=String.valueOf(count);
            for(char c:str.toCharArray()){
                chars[index++]=c;
            }
        }
      }  
      return index;
    }
   }

3) Longest palindrome substring
   class Solution {
    public String longestPalindrome(String s) {
   int start=0;
   int maxlen=0;
   for(int i =0;i<s.length();i++){
    int len1=expand(s,i,i);
    int len2=expand(s,i,i+1);
    int len=Math.max(len1,len2);
    if(len>maxlen){
        maxlen=len;
        start=i-(len-1)/2;
    }
   }
   return s.substring(start,start+maxlen);     
    }
    private int expand(String s,int left, int right){
        while(left>=0 && right<s.length() && s.charAt(left)==s.charAt(right)){
            left--;
            right++;
        }
        return right-left-1;
    }
}
