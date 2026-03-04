# Max Len Sub Array
```java
// Online Java Compiler
// Use this editor to write, compile and run your Java code online
//SPACE : O(N)
//TIME : O(N)
// if they mentioned questions with sub array of length k
// go for hashing and prefix
// if it is positive only then just go for variable sliding window
import java.util.*;
class Main {
    static int maxlen(int arr[], int k)
    {
        Map<Integer,Integer> mp = new HashMap<>();
        mp.put(0,-1);
        int s=0;
        int n = arr.length;
        int ml=Integer.MIN_VALUE;
        for(int i=0;i<n;i++)
        {
            s+=arr[i];
            int p =(s-k);
            if(mp.containsKey(p))
            {
              int l=i-mp.get(p);
              ml=Math.max(ml,l);
            }
            else 
            {
                mp.put(s,i);
            }
        }
        return ml;
        
    }
    
    //brute force
    // O(n*n)
    //o(1) space
    // static int maxlen(int arr[],int k)
    // {
    //     //brute force
    //     int n = arr.length;
    //     int mx=Integer.MIN_VALUE;
    //     for(int i=0;i<n;i++)
    //     {
    //         int curr=0;
    //         for(int j=i;j<n;j++)
    //         {
    //             curr+=arr[j];
    //             if(curr==k)
    //             {
    //                 mx=Math.max(mx,(j-i+1));
    //             }
    //         }
            
    //     }
    //     return mx;
    // }
    public static void main(String[] args) {
        int arr[]={-1,1,1,2,3};
        System.out.println(maxlen(arr,3));
    }
}
```
