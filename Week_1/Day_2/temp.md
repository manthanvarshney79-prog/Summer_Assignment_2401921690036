1. Maximum Subarray :-

int maxSubArray(int* nums, int numsSize) {
    int currentSum = nums[0];
    int maxSum = nums[0];
    for(int i = 1; i < numsSize; i++) {
        if(currentSum < 0) {
            currentSum = nums[i];
        }
        else {
            currentSum += nums[i];
        }
        if(currentSum > maxSum) {
            maxSum = currentSum;
        }
    }
    return maxSum;
}
   


3. Contains Duplicate:-

class Solution:
    def hasDuplicate(self, nums: List[int]):
        for i in range(len(nums)):
            for j in range(i + 1, len(nums)):
                if nums[i] == nums[j]:
                    return True
        return False




3. Maximum Average Subarray I :-

   double findMaxAverage(int* nums, int numsSize, int k) {
    int currentSum = 0;
    for(int i = 0; i < k; i++) {
        currentSum += nums[i];
    }
    int maxSum = currentSum;
    for(int i = k; i < numsSize; i++) {
        currentSum = currentSum + nums[i] - nums[i - k];
        if(currentSum > maxSum) {
            maxSum = currentSum;
        }
    }
    return (double)maxSum / k;
}



        
   
