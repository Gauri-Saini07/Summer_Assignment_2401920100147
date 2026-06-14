1) Reverse words in a string III
   class Solution {
    public String reverseWords(String s) {
     String[] words=s.split(" ");
     StringBuilder result= new StringBuilder();
     for(int i=0; i<words.length;i++){
        StringBuilder temp=new StringBuilder(words[i]);
        result.append(temp.reverse());
        if(i!= words.length-1){
            result.append(" ");
        }
     } 
     return result.toString();  
    }
}

2) Decode string
    class Solution {
    public String decodeString(String s) {
        //decode string
       Stack<Integer> nums=new Stack<>();
       Stack<String>  strs=new Stack<>();
       String curr="";
       int num=0;
       for(char ch:s.toCharArray()){
        if(Character.isDigit(ch)){
            num=num*10+(ch-'0');
        }
        else if(ch=='['){
 nums.push(num);
strs.push(curr);
num=0;
 curr="";
}
else if(ch==']'){
            int repeat=nums.pop();
            String prev=strs.pop();
            curr=prev+curr.repeat(repeat);
        }
        else{
            curr += ch;
        }
       }
       return curr;
    }
}

 3) Generate paranthesis
    class Solution {
    public List<String> generateParenthesis(int n) {
        List <String> result= new ArrayList<>();
        backtrack(result,"",0,0,n);
        return result;
        }
        private void backtrack(List<String> result, String curr,int open,int close,int n ){
            if(curr.length()==2*n){
                result.add(curr);
                return;
            }
            if(open<n){
                backtrack(result,curr+"(",open+1,close,n);
            }
            if(close<open){
                backtrack(result,curr+")",open, close+1,n);
            }
        }
}
