# Binary Search
By using the divide and conquer approach, this algorithm allows us to look for elements in a **sorted** array in an efficient manner, as it reduces the search space by 2 at every iteration.

**Input** 

1. nums = array of ints, **sorted** in ascending order. All the elements in nums are **unique**.
1. target = int

**Output**: If target exists in nums, return its index. Otherwise, return -1

**Time complexity**: O(Log(n))

**Space complexity**: O(1)

=== "C++"

    ``` c++ linenums="1" title="Binary Search"
    #include <vector>

    int search(vector<int>& nums, int target) {
        int left = 0;
        int right = nums.size() - 1;
        int mid;

        while (left <= right){

            mid = (left + right)/2;

            if (nums[mid] == target)
                return mid;
            else if (target > nums[mid])
                left = mid + 1;
            else
                right = mid - 1;
        }
        return -1;
    }
    ```

=== "Python"

    ``` py linenums="1" title="Binary Search"
    def search(nums: list[int], target: int) -> int:
        left = 0 
        right = len(nums) - 1

        while left <= right:
            mid = (left + right)//2

            if nums[mid] == target:
                return mid
            elif target > nums[mid]:
                left = mid + 1
            else:
                right = mid - 1

        return -1
    ```