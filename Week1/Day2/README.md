Day_2 work
1)Maximum subarray
class Solution {
    public int maxSubArray(int[] nums) {
        //subarray
            int currsum=0;
            int maxsum=Integer.MIN_VALUE;
            for(int val:nums){
                currsum+=val;
                maxsum=Math.max(currsum,maxsum);
                if(currsum<0){
                    currsum=0;
                }
            }
            return maxsum;
    }
}
