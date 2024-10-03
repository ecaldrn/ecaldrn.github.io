# Reverse a linked list


**Input** 

1. .
1. .

**Output**: 1

**Time complexity**: O()

**Space complexity**: O

=== "C++"

    ``` c++ linenums="1" title="Binary Search in C++"
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

    ``` py linenums="1" title="Binary Search in Python"
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