Original：

Given an array of integers, return indices of the two numbers such that they add up to a specific target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

------------------------------------
Example:

Given nums = [2, 7, 11, 15], target = 9,

Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1].

------------------------------------


译：有一整型数组 nums，和一个目标值 target，在整型数组中找到两个值相加刚好等于目标值 target。

你可以假设每种输入都有解，并且你不能两次都使用同一个元素。

原题链接： [https://leetcode.com/problems/two-sum/description/](https://note.youdao.com/)

Solution：


```
public class Solution {
    public int[] TwoSum(int[] nums, int target) {
            int[] relsuts = new int[2];
            
            for (int i = 0; i < nums.Length-1; i++)
            {
               
                for (int j = i + 1; j < nums.Length; j++)
                {
                  
                    if (nums[i] + nums[j] == target)
                    {
                        relsuts[0] = i;
                        relsuts[1] = j;
                        break;
                    }

                }

            }
            return relsuts;
    }
}
```


Submission Detail:

![image](https://github.com/yucaoye/leetcode/blob/master/images/Twosum.PNG)


Approach：

从头循环数组每一个元素 x，然后在x元素后面寻找到另一个元素 y，使得 x + y = target；找到元素后返回 x，y的下标。

Complexity Analysis：

Time complexity : O(n^2)，每个元素都要再循环数组后面的元素，这里花费 O(n)。两层循环，总共花费 O(n^2)。

Space complexity : O(1)

Better Solution：

![image](https://github.com/yucaoye/leetcode/blob/master/images/towsum1.PNG)

这是其他用户写得方案，他这里用到了字典，先是将数组的值和下标复制到了字典中，在循环数组，在字典中找到一个值 y = target - x(当前元素) ，如果 y 所在下标不是 x 所在下标，则成功找到，返回 x，y的下标。

此方案用到了其他的数据结构 字典 ，如果字典查找键值的函数时间复杂度是O(n)，那么总的时间复杂度也将是O(n^2)。但此方案开销的空间，空间复杂度是O(n)。

感觉他的这个方案总体来说不如我的方案，时间复杂度一样，我的空间复杂度是O(1)。但是leetcode官方测试他的用时更少，leetcode是如何测试用户提交上去的算法?



