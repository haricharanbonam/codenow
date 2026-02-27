# Bit Manipulation
## Check Set bit, Set bit , Clear Bit
```java
    static int getBit(int n ,int p)
    {
        // get its bit
        
        return (1<<p)&n;
    }
    static int setBit(int n , int p)
    {
        // set the bit to 1 
        return (1<<p) | n;
    }
    static int clearBit(int n , int p)
    {
        //  u can either use this single line or the one with if condition
        // return ~(1<<p)&n;
        if(((1<<p)&n)!=0)
        {
            return (1<<p)^n;
        }
        return n;
    }
```
## Toggle Bit 
```java
    static int toggleBit(int n , int p)
    {
        // int val = getBit(n, p);
        // if(val==0)
        // {
        //     return setBit(n, p);
        // }
        // else
        // {
        //    return clearBit(n, p);
        // }
        return (1<<p)^n; //can just use this
    }
```
## Count Ones
```java
    static int countOnes(int n)
    {
        int k =1;
        int ct=0;
        while(n!=0)
        {
                ct+=(1&n)==0?0:1;
                // n=n>>1;
                n/=2;
                // we can also use n/=2 but its not as fast as right shift, 
        }
        return ct;
    }

```
