# Problem 1 : Get, Set , Clear Bits 
``` java
class Chu{
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
        return (1<<p)^n;
    }
    // return (1<<p)^n;
    public static void main(String args[])
    {
        System.out.println(getBit(5,0)==0?0:1); 
        System.out.println(getBit(5,1)==0?0:1);
        System.out.println(getBit(5,2)==0?0:1);
        System.out.println("");
        System.out.println("");
        System.out.println("");
        System.out.println();
        System.out.println(setBit(5, 1));
        System.out.println(clearBit(5,0));
        System.out.println(clearBit(5,2));
        System.out.println(toggleBit(5,2));
        System.out.println(toggleBit(10, 1));


    }
}
```
