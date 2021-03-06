# ARTS-week-08-eleven

### 1. Algorithm
> 编程训练和学习

##### 描述
```
给定一个整数数组 nums 和一个目标值 target，请你在该数组中找出和为目标值的那 两个 整数，并返回他们的数组下标。

你可以假设每种输入只会对应一个答案。但是，你不能重复利用这个数组中同样的元素。

示例:

给定 nums = [2, 7, 11, 15], target = 9

因为 nums[0] + nums[1] = 2 + 7 = 9
所以返回 [0, 1]

```
##### 思路一
将数组的值存在Map中，数组中的元素当作key，然后判断是否存在。空间换时间的做法
```
public static int[] twoSum(int[] nums,int target) {
    Map<Integer,Integer> map = new HashMap<>();

    for (int i=0; i<nums.length; i++) {
        map.put(nums[i],i);
    }

    for (int i=0; i<nums.length; i++) {
        if(map.containsKey(target - nums[i]) && map.get(target - nums[i]) != i) {
            return new int[]{i,map.get(target - nums[i])};
        }
    }
    return null;
}
```



### 2. Review
> 英文学习
---

---
### 3. Tip
> 工作知识点、技巧

在日常开发中，有时需要抓取各种数据包，最近使用了[WireShark](https://www.wireshark.org/),支持多种平台，使用非常方便
，配上这篇[博客](https://blog.csdn.net/chenzhisi/article/details/49814769),根据需要进行信息过滤
### 4. Share
> 思考、总结、感悟

公司是做交易所的，最近和市场运营的同事们交流，他们说了一句印象深刻的话：韭菜的记忆只有8秒