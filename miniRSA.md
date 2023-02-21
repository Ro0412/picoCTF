# Problem description
What happens if you have a small exponent? There is a twist though, we padded the plaintext so that (M ** e) is just barely larger than N. Let's decrypt this  

## Downloaded file

![image](https://user-images.githubusercontent.com/123538724/220416963-08c49ced-c56f-4bd8-a03f-743ac5123b16.png)

## Approach
Seeing e:3 and the cipher text a big number I thought of taking cube root  
Also when we cube a number it does not make it much larger  
One of the hints said the flag has pico but not in the start  
So I thought that maybe pico is in ASCII form in the flag and It does not look binary so could be hex  
So maybe pico is hidden in the form of hex 
So I found the cube root of the cipher text and put an if whenever hex of "pico" is found  

# from https://riptutorial.com/python/example/8751/computing-large-integer-roots

def nth_root(x, n):

    # Start with some reasonable bounds around the nth root.

    upper_bound = 1

    while upper_bound ** n <= x:

        upper_bound *= 2

    lower_bound = upper_bound // 2

    # Keep searching for a better result as long as the bounds make sense.

    while lower_bound < upper_bound:

        mid = (lower_bound + upper_bound) // 2

        mid_nth = mid ** n

        if lower_bound < mid and mid_nth < x:

            lower_bound = mid

        elif upper_bound > mid and mid_nth > x:

            upper_bound = mid

        else:

            # Found perfect nth root.

            return mid

    return mid + 1



for i in range(4000):

   st=("{:x}".format(nth_root(c+i*n,3)))

   if "7069636f" in st:  # "pico" in hex

      print(st)

      print(binascii.unhexlify(st))  
 
 Found this code for cube root and found the flag  
 
 ## FLAG
 picoCTF{e_sh0u1d_b3_lArg3r_a166c1e3}

