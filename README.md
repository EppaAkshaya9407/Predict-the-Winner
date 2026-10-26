# Predict-the-Winner
class Solution:
    def predictTheWinner(self, nums: List[int]) -> bool:
        n=len(nums)
        r=nums[:]
        if n<=2:
            return True
        for i in range(n-2,-1,-1):
            for j in range(i+1,n):
                r[j]=max(nums[i]-r[j],nums[j]-r[j-1])
        if r[n-1]>=0:
            return True
        else:
            return False
