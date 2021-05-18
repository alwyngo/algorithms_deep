题目:
给定一个整数数组 nums 和一个整数目标值 target，请你在该数组中找出 和为目标值 的那 两个 整数，并返回它们的数组下标。你可以假设每种输入只会对应一个答案。但是，数组中同一个元素在答案里不能重复出现。

题目解析：
数组中的同一个元素，只能返回一次，加入和为4， 数组为[1,2,3]， 则返回的下标只能为[0,2] 而 [1,1]之和也是4， 但是不满足

```java
class Solution {
    public int[] twoSum(int[] nums, int target) {
        int len = nums.length;
        // 初始长度为len - 1
        Map<Integer, Integer> hashMap = new HashMap<Integer, Integer>(len -1);
        for (int i = 0; i < nums.length; ++i) {
            int secondNumber = target - nums[i];
            if (hashMap.containsKey(secondNumber)) {
                return new int[]{hashMap.get(secondNumber), i};
            }
            hashMap.put(nums[i], i);
        }
        throw new IllegalArgumentException("No find two numbers sum as target");
    }
}
```
时间复杂度为 `O(N)`， 空间复杂度为`O(N)`
