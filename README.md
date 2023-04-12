# Question
Next greater element to the right:
class Solution:
    def nextGreaterElement(self, nums1: List[int], nums2: List[int]) -> List[int]:
        need, ready, next_greater = set(nums1), set(), {}
        for n in nums2:
            for k in ready:
                if k < n:
                    next_greater[k] = n
            ready = {k for k in ready if k not in next_greater}
            if n in need and n not in next_greater and n not in ready:
                ready.add(n)
        return [next_greater[k] if k in next_greater else -1 for k in nums1]
        
        ______________________________________________________________________________________________________________________________________________________________________
 Next greater element to the left:
         def nearest_greater_to_left(arr):
          result = []
          for i in range(0, len(arr)):
            for j in range(i-1,-1,-1):
              if arr[i] < arr[j]:
                result.append(arr[j])
                break
            else:
                result.append(-1)
          return result
          ______________________________________________________________________________________________________________________________________________________________________
  Next smaller element to the right:
            def nearest_smaller_to_right(arr):
              result = []
              for i in range(0, len(arr)):
                  for j in range(i+1, len(arr)):
                      if arr[i] > arr[j]:
                          result.append(arr[j])
                          break
                  else:
                    result.append(-1)
              return result
            arr = [9, 7, 1, 5, 6]
            print(nearest_smaller_to_right(arr))
_______________________________________________________________________________________________________________________________________________________________________
Next smaller element to the left:
            def nearest_smaller_to_left(arr):
                result = []
                for i in range(0, len(arr)):
                    for j in range(i-1, -1, -1):
                        if arr[i] > arr[j]:
                            result.append(arr[j])
                            break
                    else:
                        result.append(-1)
                return result
            arr = [7, 3, 16, 82, 65]
            print(nearest_smaller_to_left(arr))
 ___________________________________________________________________________________________________________________________________________________________________
 Valid parnetheses:
 class Solution:
    def isValid(self, s: str) -> bool:
        if len(s) % 2 != 0:
            return False
        dict = {'(' : ')', '[' : ']', '{' : '}'}
        stack = []
        for iin s:
            if i in dict.keys():
                stack.append(i)
            else:
                if stack == []:
                    return False
                a = stack.pop()
                if i!= dict[a]:
                    return False
        return stack == []
