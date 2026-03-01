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
# Isomorphic Strings  Optimal
```java
class Solution {
    // in case it only supports the lower case characters
    // TIME : O(N)
    // SPACE : 0(1)
    public boolean isIsomorphic(String s, String t) {
        int n = s.length();
        if(n!=t.length())
        {
            return false;
        }
        int f[] = new int[128];
        boolean ref[]=new boolean[128];

        for(int i=0;i<n;i++)
        {
            char x = s.charAt(i);
            if(f[x]==0)
            {
                if(ref[t.charAt(i)])
                {
                    return false;
                }
                f[x]=(t.charAt(i));
                ref[t.charAt(i)]=true;
            }
            else
            {
                if((t.charAt(i))!=f[x])
                {
                        return false;
                }
            }
        }
        return true;
    }
}
```
# Find all valid anagrams in a String
```java
class Solution {
// SPACE : O(1)
// TIME : O(N)
    public List<Integer> findAnagrams(String s, String p) {
        
        int n = s.length();
        int k =p.length();
        if(k>n)
        {
            return new ArrayList<>();
        }
        int ct=0;
        int f[]= new int[26];
        int pp[]= new int[26];
        int win[] = new int[26];
        for(int i=0;i<k;i++)
        {
            pp[p.charAt(i)-97]+=1;
        }
        List<Integer> l = new ArrayList<>();
        int cc=0;
        for(int i=0;i<k;i++)
        {
            char x = s.charAt(i);
            win[x-97]+=1;
        }
        if(Arrays.equals(win,pp))
        {
            l.add(0);
        }
        for(int i=1;i<=n-k;i++)
        {
            win[s.charAt(i-1)-97]-=1;
            win[s.charAt(i+k-1)-97]+=1;
            if(Arrays.equals(win,pp))
            {
                l.add(i);
            }
        }
        return l;
        }
    
}
```
