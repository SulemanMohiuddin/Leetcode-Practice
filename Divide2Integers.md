# Divide Two Integers


### Java Code

```java

class Solution {
    public int divide(int dividend, int divisor) {
        if (dividend == Integer.MIN_VALUE && divisor == -1) {
            return Integer.MAX_VALUE;
        }
        
        boolean isNegative = (dividend < 0) ^ (divisor < 0);
        long longDividend = Math.abs((long) dividend);
        long longDivisor = Math.abs((long) divisor);
        
        int quotient = 0;
        
        while (longDividend >= longDivisor) {
            long tempDivisor = longDivisor, multiple = 1;
            while (longDividend >= (tempDivisor << 1)) {
                tempDivisor <<= 1;
                multiple <<= 1;
            }
            
            longDividend -= tempDivisor;
            quotient += multiple;
        }
        
        return isNegative ? -quotient : quotient;
    }
}


```

![image](https://github.com/user-attachments/assets/d579c492-0ba0-4c69-872b-c830fcc07715)
