# Palindrome Checker

This code checks if a given integer is a palindrome. 

### Java Code

```java

class Solution {
    public boolean isPalindrome(int x) {
        List<Integer> list = new ArrayList<>();
// this means that number that are negative can never be palindrome and numbers that have a 0 in the last cant be palindrome
        if(x < 0 || (x != 0 && x % 10 == 0)){
           return false;
        }
//this is to split the numbers and add them to 
        while (x != 0){
             list.add(x % 10);
            x /= 10;
        }

//this is the part the checks the list for any palindrome

                int left = 0;
        int right = list.size() - 1;

        while (left < right) {
            if (!list.get(left).equals(list.get(right))) {
                return false; 
            }
            left++;
            right--;
        }
        return true;
        
    }
}
