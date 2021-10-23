Given an integer array nums, return all the triplets [nums[i], nums[j], nums[k]] such that i != j, i != k, and j != k, and nums[i] + nums[j] + nums[k] == 0.

Notice that the solution set must not contain duplicate triplets.

noob:
```python
class Solution:
    def threeSum(nums):
        result = []
        unique = []
        for i in range(len(nums)):
            for j in range(i, len(nums)):
                for k in range(j, len(nums)):
                    temp = []
                    if i != j:
                        if i != k:
                            if j != k:
                                if nums[i]+nums[j]+nums[k] == 0:
                                    temp.append(nums[i])
                                    temp.append(nums[j])
                                    temp.append(nums[k])
                                    result.append(temp)
        for x in result:
            x.sort()
        for x in result:
            if x not in unique:
                unique.append(x)
        return unique
```
pro:
```python
class Solution:
	def threeSum(self, nums: List[int]) -> List[List[int]]:
		ans = []
		nums.sort()
		length = len(nums) - 1
		for index, num in enumerate(nums):
			if index > 0 and nums[index - 1] == nums[index]:
				continue
				
			left, right = index + 1, length
			while left < right:
				if num + nums[left] + nums[right] < 0: left += 1
				elif num + nums[left] + nums[right] > 0: right -= 1
				else:
					ans.append([num, nums[left], nums[right]])
					left += 1
					while left < right and nums[left] == nums[left - 1]:
						left += 1
		return ans
```

I am the noob
