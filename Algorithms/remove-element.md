# 27. Remove Element

## 描述
给定一个数组和一个值，删除该值相等的所有元素，并返回新数组的长度。

不要使用额外空间来新建一个数组，您必须使用常数空间来进行完成此题。

元素的顺序可以改变。 但无所谓超过新数组长度的数组后部分元素是多少。

**例：**
给定输入数组*nums* = `[3,2,2,3]`，*val* = `3`

你的函数应该返回length = 2，数组nums的前两个元素是2。

提示：
1.尝试使用两个指针。
2.您是否尝试使用 “更改元素的顺序” 这一特性？
3.当要删除的元素很少时会发生什么？

## 解析
使用两个指针，一前一后，快指针用于遍历新元素。
当快指针指向的元素与待删除的值不同时，则将快指针指向的元素覆盖到慢指针指向的元素；
当快指针发现待删除的值时，则跳过，这时慢指针不动。

- 时间复杂度：O(n)  
- 空间复杂度：O(1)
- 语言：C++

```C++
{
public:
    int removeElement(vector<int>& nums, int val) 
    {
        int length = 0;
        for(int i=0,j=0;j<nums.size();j++)
        {
            if(nums[j] != val)
            {
                nums[i] = nums[j];
                i++;
                length ++;
            }
        }
        return length;
    }
};
```

