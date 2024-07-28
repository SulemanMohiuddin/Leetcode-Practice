# Maximum Odd Binary Number
what i did basically just found out the numbers of 1s and 0s and then put all the 1s in the front and all the 0s afterwards
and put the final 1 in the end.<br>
-in case of only 1 it will be placed at the end<br>
-in case of only 0 well the ans will be 0


### Java Code

```java


class Solution {
    public String maximumOddBinaryNumber(String s) {
        int count1 = 0;
        int count0 = 0;
        
        //seperating each character and counting the number of 1s and 0s
        for (char c : s.toCharArray()) {
            if (c == '1') {
                count1++;
            } else if (c == '0') {
                count0++;
            }
        }
        

        StringBuilder result = new StringBuilder();
        //adding all the 1s to the start and leaving only 1
        for (int i = 0; i < count1 - 1; i++) {
            result.append('1');
        }
        // adding all 0s now
        for (int i = 0; i < count0; i++) {
            result.append('0');
        }
        //adding the last 1 to make the bit valid and the biggest
        result.append('1');
        

        //outputiing the string
        return result.toString();
    }
}
