# day5

## 1.移除元素

给定一个数组 nums 和一个值 val，你需要原地移除所有数值等于 val 的元素，返回移除后数组的新长度。

不要使用额外的数组空间，你必须在原地修改输入数组并在使用 O(1) 额外空间的条件下完成。

元素的顺序可以改变。你不需要考虑数组中超出新长度后面的元素。
**示例1：**
给定 nums = [3,2,2,3], val = 3,

函数应该返回新的长度 2, 并且 nums 中的前两个元素均为 2。

你不需要考虑数组中超出新长度后面的元素。
**示例2：**
给定 nums = [0,1,2,2,3,0,4,2], val = 2,

函数应该返回新的长度 5, 并且 nums 中的前五个元素为 0, 1, 3, 0, 4。

注意这五个元素可为任意顺序。

你不需要考虑数组中超出新长度后面的元素。

**代码：**
```
class Solution:
    def removeElement(self, nums: List[int], val: int) -> int:
        nums.remove(val)
        return len(nums)
```

## 2.最长公共前缀
编写一个函数来查找字符串数组中的最长公共前缀。

如果不存在公共前缀，返回空字符串 ""。
**示例1：**

```
输入: ["flower","flow","flight"]
输出: "fl"
```
**示例2：**
```
输入: ["dog","racecar","car"]
输出: ""
解释: 输入不存在公共前缀。
```
**代码：**
```
class Solution:
    def longestCommonPrefix(self, strs): 
        s1=min(strs)
        s2=max(strs)
        if s1[0]!=s2[0]:
            return ''
        for i,x in enumerate(s1):
            if x!= s2[i]:
                return s2[:i]
        return s1 
```
**解释：**

python两种让你拍大腿的解法，时间复杂度你想象不到，短小精悍。 1、利用python的max()和min()，在Python里字符串是可以比较的，按照ascII值排，举例abb， aba，abac，最大为abb，最小为aba。
所以只需要比较最大最小的公共前缀就是整个数组的公共前缀
