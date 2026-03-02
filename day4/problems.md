```java
class Solution {
    public String largestOddNumber(String num) {
        int n = num.length() - 1;
        while (n != -1) {
            if (((num.charAt(n)) & 1) == 0) {
                n -= 1;
                continue;
            } else {
                break;
            }
        }

        return num.substring(0, n + 1);
    }
}
```
# Merge two Strings Alternatively
```java
class Solution {
    // TIME : O(MAX(M,N))
    //SPACE : O(M+N)
    public String mergeAlternately(String word1, String word2) {
        StringBuilder sb = new StringBuilder();
        int m = word1.length();
        int n = word2.length();
        int k = Math.min(m,n);
        int c=0;
        if(m<n)
        {
            c=n;
        }
        else
        {
            c=m;
        }
        int i=0;
        while(i<k){
            sb.append(word1.charAt(i));
            sb.append(word2.charAt(i));
            k+=1;
        }

        while(i<m)
        {
              sb.append(word1.charAt(i));
              i+=1;
        }
        while(i<n)
        {
              sb.append(word2.charAt(i));
              i+=1;
        }
        return new String(sb);
    }
}
```
