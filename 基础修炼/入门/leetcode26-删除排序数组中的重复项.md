![image-20200921152433823](C:\Users\xiaodong\AppData\Roaming\Typora\typora-user-images\image-20200921152433823.png)

java编码

```java
class Solution {
    public int removeDuplicates(int[] nums) {
        if (nums.length == 0) return 0;
        int i = 0;
        for (int j = 1; j < nums.length; j++){
            if (nums[j] != nums[i]){
                i++;
                nums[i] = nums[j];
            }
        }
        return i+1;
    }
}
```

已知题目是排序数组，只需要按顺序判断相邻两个是否相同即可，涉及两个元素对比，立即推双指针。

如果碰到相同元素，则 j + 1再去遍历，此时慢指针 i 不动，当快慢指针不相同时，将慢指针加一，使其下一个位置为快指针的元素。这样最终得到的nums，慢指针最终的位置加1，则无重复的长度为n+1

时间复杂度On，空间复杂度O1

打乱的数组怎么做？先排序就好啦，只求ac