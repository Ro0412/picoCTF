# Problem description
We found this file. Recover the flag.

## Approach
![image](https://user-images.githubusercontent.com/123538724/220493481-a2d94939-378f-4961-a7f9-78e9c5b71bfe.png)
This occured whenever I tried to open it  
So maybe some size issue
Used Bless Hex editor
![image](https://user-images.githubusercontent.com/123538724/220493774-403dfd43-7698-445e-bff0-d285718124ea.png)
Saw that type is BITMAP (BM)  
Changed the file to .bmp but the problem persisted
So I downloaded an actual .bmp file to compare it and BA D0 was repeated twice in our problem file
Changed it according to the sample file
![image](https://user-images.githubusercontent.com/123538724/220494033-1a03c5a7-53fd-4acb-aabd-b1766a0bcf49.png)


Figured out what source code controls size and resolution  
Downloaded libimage-exiftool-perl to use exiftool  

![image](https://user-images.githubusercontent.com/123538724/220495453-0f25436e-bfe8-4423-9dbe-cd8b804dedbf.png)
Here we see the size is 1134 * 36  
Then I saw the hex values for the same so I know which code is responsible for size  
46E and 132  
Looked for the same in Bless Hex editor and saw bytes are written in reverse
![image](https://user-images.githubusercontent.com/123538724/220495793-4523f72c-f2c9-4dd6-a66a-dd262800d23a.png)
So I zoomed out the image changing that code 

## FLAG
![image](https://user-images.githubusercontent.com/123538724/220495985-dfaaacb5-ffec-448b-84d9-2c60d6432696.png)

