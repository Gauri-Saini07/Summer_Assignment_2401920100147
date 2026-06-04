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

2) Contains duplicate
class Solution {
    public boolean containsDuplicate(int[] nums) {
        HashMap <Integer,Integer> map = new HashMap<>();
        for(int i =0;i<nums.length;i++){
            if(map.containsKey(nums[i])){
                return true;
            }
            map.put(nums[i],i);
        }
        return false;
    }
}
