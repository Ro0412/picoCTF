# Problem Description
Figure out how they moved the flag.

## Attachment
![Screenshot from 2023-02-22 06-02-25](https://user-images.githubusercontent.com/123538724/220490125-3bb3d738-4b1a-40bf-b8bf-ddaedd76850a.png)

## Approach
File > Export Objects > TFTP and Saved all  
5 files were downloaded  

### File 1
![image](https://user-images.githubusercontent.com/123538724/220490539-a0ae0fe4-5175-4d04-9558-97f5bd5a6ca6.png)
It looks like an encryption and my first go to was rot13 so used rot13 decoder
![image](https://user-images.githubusercontent.com/123538724/220490872-aa6fe5f1-124e-4b92-bbf2-f76ea17c88c4.png)

### File 2
I opened the file called plan and decoded using rot13
![image](https://user-images.githubusercontent.com/123538724/220491071-ab587d40-5086-4196-98d4-8802d8d059a9.png)

### File 3
There were 3 photos but nothing seemed off but I checked out programme since it said use the Programme  
I used 7zip which is a file archeiver with high compression ratio  
Learned about steghide from https://www.2daygeek.com/easy-way-hide-information-inside-image-and-sound-objects/

![image](https://user-images.githubusercontent.com/123538724/220492727-eb9de213-9b6a-4508-9c2e-ae37f972701b.png)
Here a passphrase was needed to see the embedded data
When decoding plan.txt it said with-DUEDILIGENCE so that was the passphrase

## FLAG
![image](https://user-images.githubusercontent.com/123538724/220492933-085aeafb-9fc5-40b5-81e2-eb06f89cd880.png)

