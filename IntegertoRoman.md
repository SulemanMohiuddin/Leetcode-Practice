# Integer to Roman


### Java Code

```java


class Solution {
    public String intToRoman(int num) {
    int[] VALUES = {
        1000, 900, 500, 400, 100, 90, 50, 40, 10, 9, 5, 4, 1
    };

    String[] SYMBOLS = {
        "M", "CM", "D", "CD", "C", "XC", "L", "XL", "X", "IX", "V", "IV", "I"
    };

            StringBuilder roman = new StringBuilder();
        
        for (int i = 0; i < VALUES.length; i++) {
            while (num >= VALUES[i]) {
                roman.append(SYMBOLS[i]);
                num -= VALUES[i];
            }
        }
        
        return roman.toString();

        
    }
}
