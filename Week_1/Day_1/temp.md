1. Two Sum :-

   
int* twoSum(int* nums, int numsSize, int target, int* returnSize) {
    static int ans[2];
    for(int i = 0; i < numsSize; i++) {
        for(int j = i + 1; j < numsSize; j++) {
            if(nums[i] + nums[j] == target) {
                ans[0] = i;
                ans[1] = j;
                *returnSize = 2;
                return ans;
            }
        }
    }
    *returnSize = 0;
    return ans;
}


2. Remove Duplicates from Sorted Array :-

   int removeDuplicates(int* nums, int numsSize) {
    if(numsSize == 0) {
        return 0;
    }
    int unique = 1;
    for(int i = 1; i < numsSize; i++) {
        if(nums[i] != nums[i - 1]) {
            nums[unique] = nums[i];
            unique++;
        }
    }
    return unique;
}


3. Best Time to Buy and Sell Stock :-

   int maxProfit(int* prices, int pricesSize) {
    int buy = prices[0];
    int profit = 0;
    for(int i = 1; i < pricesSize; i++) {
        if(prices[i] < buy) {
            buy = prices[i];
        }
        int currentProfit = prices[i] - buy;
        if(currentProfit > profit) {
            profit = currentProfit;
        }
    }
    return profit;
}


