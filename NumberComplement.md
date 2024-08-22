# Complement of integer


### Java Code

```java

class Solution {
  public static int findComplement(int num) {
        String binary = Integer.toBinaryString(num);
        
        StringBuilder complementBinary = new StringBuilder();
        for (char bit : binary.toCharArray()) {
            complementBinary.append(bit == '0' ? '1' : '0');
        }
        return Integer.parseInt(complementBinary.toString(), 2);
    }
}


```
![image](https://github.com/user-attachments/assets/9c7ab2e1-e885-4ced-84bb-4ebdae744141)

CODE THAT GPT GAVE

```java
    public static int findComplement(int num) {
        // Step 1: Create a mask with all bits set to 1, which has the same number of bits as the original number
        int mask = (Integer.highestOneBit(num) << 1) - 1;
        
        // Step 2: XOR the original number with the mask to get the complement
        return num ^ mask;
    }
```
