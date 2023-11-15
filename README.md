# First-Missing-Positive-using-Java-Leetcode

    class Solution {
        public static int sort(int[] arr){
           int i =0;
           while(i<arr.length)
           {
               int correct = arr[i] - 1;
               if(arr[i]>0 && arr[i]<=arr.length && arr[i] != arr[correct]){
                    swap(arr,i,correct);
               }else{
                   i++;
               }
           }
           for(int j =0; j < arr.length;j++){
               if(arr[j]!=j+1){
                   return j+1;
               }
           }
           return arr.length+1;
        }
        public static void swap(int[] arr,int i, int correct){
            int temp;
            temp = arr[i];
            arr[i] = arr[correct];
            arr[correct] = temp;
        }
        public int firstMissingPositive(int[] nums) {
            Solution ob = new Solution();
            int result = ob.sort(nums);
            return result;
        }
    }
