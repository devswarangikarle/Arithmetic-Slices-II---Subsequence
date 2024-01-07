# Arithmetic-Slices-II---Subsequence

class Solution:
    def numberOfArithmeticSlices(self, nums):
        n = len(nums)
        total_count = 0
        dp = [{} for _ in range(n)]

        for i in range(n):
            for j in range(i):
                diff = nums[i] - nums[j]
                count_j_diff = dp[j].get(diff, 0)
                total_count += count_j_diff
                dp[i][diff] = dp[i].get(diff, 0) + count_j_diff + 1

        return total_count


nums1 = [2, 4, 6, 8, 10]
nums2 = [7, 7, 7, 7, 7]

sol = Solution()
output1 = sol.numberOfArithmeticSlices(nums1)
output2 = sol.numberOfArithmeticSlices(nums2)

print(output1)  
print(output2)  
