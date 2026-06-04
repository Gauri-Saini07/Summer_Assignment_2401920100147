Day_1 work
1) two sum.java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        for(int i =0;i<nums.length;i++){
            for(int j =i+1;j<nums.length;j++){
                if(nums[i]+nums[j]==target){
                    int[] result={i,j};
                    return result;
                }
            }
        }
        int[] result = {};
        return result;
    }
}

2) Remove duplicates from java
   class Solution {
    public int removeDuplicates(int[] nums) {
        // remove duplicates.java
       int i=0;
       for(int j=1;j<nums.length;j++){
        if(nums[j]!=nums[i]){
            i++;
            nums[i]=nums[j];
        }
       }
       return i+1; 
    }
}
3) Best time to buy and sell
4) class Solution {
    public int maxProfit(int[] prices) {
        //buyandsell
       int minprice=prices[0];
       int maxprofit=0;
       for(int i=1;i<prices.length;i++){
        if(prices[i]<minprice){
            minprice=prices[i];
        }
        else{
           int profit= prices[i]-minprice;
           if(profit>maxprofit){
            maxprofit=profit;
           }
        }
       } 
       return maxprofit;
    }
}
