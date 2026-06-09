1) Valid Anagram
   class Solution {
    public boolean isAnagram(String s, String t) {
        //Anagram
      if(s.length()!=t.length()) return false;
      HashMap<Character,Integer> map=new HashMap<>();
      for(int i=0;i<s.length();i++){
        char ch=s.charAt(i);
        map.put(ch,map.getOrDefault(ch,0)+1);
      } 
      for(int i=0;i<t.length();i++){
        char ch=t.charAt(i);
        if(!map.containsKey(ch)) return false;
        int freq=map.get(ch);
        if(freq==0)return false;
        map.put(ch,freq-1);
      }
      return true;
    }
}

2) First unique character in a string
   class Solution {
    public int firstUniqChar(String s) {
        HashMap <Character,Integer> map = new HashMap<>();
        for(int i =0; i < s.length(); i++){
            char ch = s.charAt(i);
            map.put(ch,map.getOrDefault(ch,0)+1);
        }
        for(int i =0; i<s.length();i++){
            if(map.get(s.charAt(i))==1){
                return i;
            }
        }
    return -1;
    }
}

3) Ransom note
   class Solution {
    public boolean canConstruct(String ransomNote, String magazine) {
        HashMap< Character, Integer>map=new HashMap<>();
        for(int i =0;i<magazine.length();i++){
         char ch= magazine.charAt(i);
         map.put(ch,map.getOrDefault(ch,0)+1);
        } 
        for(int i=0;i<ransomNote.length();i++){
            char ch=ransomNote.charAt(i);
            if(!map.containsKey(ch)||map.get(ch)==0){
                return false;
            }
            map.put(ch,map.get(ch)-1);
        }  
        return true;
        }
}
