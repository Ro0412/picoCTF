# Problem Description
This website can be rendered only by picobrowser, go and catch the flag!   
https://jupiter.challenges.picoctf.org/problem/28921/

## Approach

- Opened the link
- Tried to click on flag but it said you are not picobrowser

![Screenshot from 2023-02-22 00-19-44](https://user-images.githubusercontent.com/123538724/220433134-3fd00b72-9261-41a4-ac3b-2fcc55878eb2.png)
- HInt said that no new browser had to be installed
- Went to souce code and tried to read it through but did not find anything
- Went to inspections and storage but did not find anything
- Went to network and in the file named flag saw the information given like gzip was the encoding and the User-Agent was Mozilla/5.0 (X11; Ubuntu; Linux x86_64; rv:109.0) Gecko/20100101 Firefox/109.0
![Screenshot from 2023-02-22 00-22-01](https://user-images.githubusercontent.com/123538724/220433595-b3abdddc-fc4d-4883-99a6-b96bb5c506f4.png)

- So downloaded Modify Header extension for firefox and changed User-Agent to picobrowser



![Screenshot from 2023-02-22 00-27-00](https://user-images.githubusercontent.com/123538724/220434713-e3d0794d-fb19-4a16-a525-840f4688e32d.png)
![Screenshot from 2023-02-22 00-27-22](https://user-images.githubusercontent.com/123538724/220434720-7f81b449-2a6e-4161-b8d9-c28dd5bf9b13.png)

## FLAG
picoCTF{p1c0_s3cr3t_ag3nt_84f9c865}
