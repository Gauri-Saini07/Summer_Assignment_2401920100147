Day_3 work
1) Move zeroes
 class Solution {
    public void moveZeroes(int[] nums) {
        int index=0;
        for(int i =0;i<nums.length;i++){
            if(nums[i]!=0){
                nums[index]=nums[i];
                index++;
            }
        }
        while(index<nums.length){
            nums[index]=0;
            index++;
        }
    }
}
2) squares of sorted array
 class Solution {
    public int[] sortedSquares(int[] nums) {
        // squares of sorted aaray
        int[]ans=new int [nums.length];
        for(int i =0;i<nums.length;i++){
            ans[i]=nums[i]*nums[i];
        }
        insertion(ans);
         return ans;}
        static void insertion(int []arr){
            for(int i =0;i<arr.length-1;i++){
                for(int j =i+1;j>0;j--){
                    if(arr[j]<arr[j-1]){
                        swap(arr,j,j-1);
                    }
                    else{
                        break;
                    }
                }
            }
        }
        static void swap(int []arr,int first,int second){
            int temp=arr[first];
            arr[first]=arr[second];
            arr[second]=temp;
        }  
}
3) Container with most water
 class Solution {
    public int maxArea(int[] height) {
      int left=0;
      int right=height.length-1;
      int maxArea=0;
      while(left<right){
        int width=right-left;
        int h=Math.min(height[left],height[right]);
        int area=width*h;
        maxArea= Math.max(maxArea,area);
        if(height[left]<height[right]){
            left++;
        }
        else{
            right--;
        }
      }
      return maxArea; 
    }
}
