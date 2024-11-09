2024-11-09 09:30

Status:

Tags:

# Kadane's Algorithm


```
def Kadane(nums):
	maxSum = nums[0]
	currSum = 0

	for n in nums:
		currSum = max(currSum, 0)
		currSum += n
		maxSum = max(currSum, maxSum)

	return maxSum


```

Sliding Window Variation

![[Screenshot 2024-11-09 at 9.33.13 AM.png]]
# References


