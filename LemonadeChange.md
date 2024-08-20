# Lemonade Change
This was pretty easy just count the bills and deduct them.

### Java Code

```java
class Solution {
    public boolean lemonadeChange(int[] bills) {
        int fiveBill = 0;
        int tenBill = 0;

        for (int bill : bills) {
            if (bill == 5) {
                fiveBill++; 
            } else if (bill == 10) {
                if (fiveBill > 0) {
                    fiveBill--;  
                    tenBill++;   
                } else {
                    return false;  
                }
            } else if (bill == 20) {
                if (tenBill > 0 && fiveBill > 0) {
                    tenBill--;  
                    fiveBill--; 
                } else if (fiveBill >= 3) {
                    fiveBill -= 3;  
                } else {
                    return false;  
                }
            }
        }

        return true;  
    }
}

```

![image](https://github.com/user-attachments/assets/0ffee62e-3788-4bcc-b051-c8943f0ae752)
