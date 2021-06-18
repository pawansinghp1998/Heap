Q.1.(215).Given an integer array nums and an integer k, return the kth largest element in the array.
          Note that it is the kth largest element in the sorted order, not the kth distinct element.
          
 Input: nums = [3,2,1,5,6,4], k = 2
Output: 5

Input: nums = [3,2,3,1,2,4,5,5,6], k = 4
Output: 4

class Solution {
    public int findKthLargest(int[] nums, int k) {
        int arr1[]=new int[k];
        int n=nums.length;
       PriorityQueue<Integer> minheap=new PriorityQueue<Integer>();      //this store number in ascending order
        for(int i=0;i<k;i++)
        {
            minheap.add(nums[i]);                                        //it will automatically store k number in ascending order
        }
        for(int i=k;i<n;i++)
        {
            if(minheap.peek()>nums[i])                                 //if min of k number is grater than nums[i] then continue
                continue;
            else
            {
                minheap.poll();                                        //else remove smallest of k number and add the one which is greater
                minheap.add(nums[i]);
            }
                
        }
        return minheap.poll();                         //it will be smallest of all k number stored
        }
    }


 
