# Valid Anagram
``` java
class Solution {
    // TIME : O(N)
    // SPACE : O(1)
    public boolean isAnagram(String s, String t) {
        int n = s.length();
        int m = t.length();
        if (n != m) {
            return false;
        }
        int f[] = new int[26];
        for (int i = 0; i < n; i++) {
            f[s.charAt(i) - 97] += 1;
        }

        for (int i = 0; i < m; i++) {
            f[t.charAt(i) - 97] -= 1;
        }
        for (int i = 0; i < 26; i++) {
            if (f[i] != 0)
                return false;
        }
        return true;
    }

}
```
# Isomorphic Strings 1
``` java
class Solution {
    //TIME : O(N^2)
    //SPACE : O(N)
    public boolean isIsomorphic(String s, String t) {
        HashMap<Character,Character> map = new HashMap<>();
        int m = s.length();
        int n = t.length();
        for(int i=0;i<m;i++)
        {
            char idx = s.charAt(i);
            char val = t.charAt(i);

            if(map.containsKey(idx))
            {
                if(map.get(idx)!=val)
                {
                        return false;
                }
            }
            else if (map.containsValue(val))
            {
                    return false;
            }
            else
            {
                map.put(idx,val);
            }
        }
        return true;
    }
}
```
# Isomorphic Strings 2 Optimal
```java
```
