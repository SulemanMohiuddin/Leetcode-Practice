# Reverse integer(medium)

Given a signed 32-bit integer x, return x with its digits reversed. If reversing x causes the value to go outside the signed 32-bit integer range [-231, 231 - 1], then return 0.

Assume the environment does not allow you to store 64-bit integers (signed or unsigned).

### Java Code

```java 

class Solution {
    public int reverse(int x) {
        List<Integer> list = new ArrayList<>();



    //this is to split the numbers and add them to 
     while (x != 0){
        list.add(x % 10);
         x /= 10;
        }
        
        int size=list.size();




        int output=0;

        for(int i=0;i<size;i++){
            int digit = list.get(i);
            
           // Check for overflow before updating output
            if (output > Integer.MAX_VALUE / 10 || (output == Integer.MAX_VALUE / 10 && digit > 7)) {
                return 0;
            }
            if (output < Integer.MIN_VALUE / 10 || (output == Integer.MIN_VALUE / 10 && digit < -8)) {
                return 0;
            }

            output = output * 10 + digit;
        }

        return output;
        
    }
}
