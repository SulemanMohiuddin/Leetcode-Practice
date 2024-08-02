# Roman to Integer


### Java Code

```java

class Solution {
    public int romanToInt(String s) {
        int total = 0;
        int prevValue = 0;

        for (int i = 0; i < s.length(); i++) {
            int currentValue = 0;
            switch (s.charAt(i)) {
                case 'I': currentValue = 1; break;
                case 'V': currentValue = 5; break;
                case 'X': currentValue = 10; break;
                case 'L': currentValue = 50; break;
                case 'C': currentValue = 100; break;
                case 'D': currentValue = 500; break;
                case 'M': currentValue = 1000; break;
                default: break; 
            }

            if (currentValue > prevValue) {
                total += currentValue - 2 * prevValue;
            } else {
                total += currentValue;
            }
            prevValue = currentValue;
        }

        return total;
    }
}

```
![image](https://github.com/user-attachments/assets/cc3faaa8-d549-46fa-9987-d64c5df910ea)
