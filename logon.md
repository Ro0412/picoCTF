# Problem Description
The factory is hiding things from all of its users. Can you login as Joe and find what they've been looking at? 
https://jupiter.challenges.picoctf.org/problem/44573/ 

## Approach
Tried signing in as admin but did not work
![Screenshot from 2023-02-22 00-45-25](https://user-images.githubusercontent.com/123538724/220437961-64ad1955-9f91-4af5-bba0-1309b4b5a7be.png)
Tried logging in as JOe but needed the password
Inspected the page specifically storage  
looked at the source code of page but did not find anything useful  
In storage permissions for admin were false so changed it to True and reloaded

![Screenshot from 2023-02-22 00-47-18](https://user-images.githubusercontent.com/123538724/220438587-6eb346b7-21e1-4f2f-8024-d460b1694292.png)

## FLAG
picoCTF{th3_c0nsp1r4cy_l1v3s_0c98aacc}
![Screenshot from 2023-02-22 00-48-19](https://user-images.githubusercontent.com/123538724/220438578-65759d91-6cb6-454f-abfa-ecd8e3051921.png)
