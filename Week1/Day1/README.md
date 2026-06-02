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
3) class Solution {
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
