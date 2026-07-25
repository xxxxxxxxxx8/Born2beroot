## Born2BeRoot Guide 
This guide has 8 Parts: 
- Part 1 - Downloading Your Virtual Machine
- Part 2 - Installing Your Virtual Machine
- Part 3 - Starting Your Virtual Machine
- Part 4 - Configurating Your Virtual Machine
- Part 5 - Connecting to SSH
- Part 6 - Continue Configurating Your Virtual Machine
- Part 7 - Signature.txt
- Part 8 - Your Born2BeRoot Defence Evaluation with Answers

## Part 1 - Downloading Your Virtual Machine

1. Click on this link <ins>**https://cdimage.debian.org/debian-cd/current/amd64/iso-cd/**

2. Scroll to the bottom of the website and click `debian-xx.x.x-amd64-netinst.iso`

### Part 1.1 - Sgoingfre (Only 42 Adelaide Students)

1. Head over to iTerm2

<img width="622" alt="Screen Shot 2022-07-26 at 4 26 06 PM" src="https://user-images.githubusercontent.com/58959408/180943494-9c25b321-4cae-4c39-89bb-92271a245489.png">

2. Then type `cd sgoinfre/students`

<img width="622" alt="Screen Shot 2022-07-26 at 4 26 27 PM" src="https://user-images.githubusercontent.com/58959408/180943649-42dba828-3bd3-45ee-92ea-4e7218d65674.png">

3. Then type `mkdir <your intra username>`

<img width="622" alt="Screen Shot 2022-07-26 at 4 26 38 PM" src="https://user-images.githubusercontent.com/58959408/180943705-d9705f63-59a9-4b2d-9130-75d8711a25d3.png">

4. Then type `chmod 700 <your intra username>`

<img width="622" alt="Screen Shot 2022-07-26 at 4 26 48 PM" src="https://user-images.githubusercontent.com/58959408/180943745-09427be5-f0ff-4100-aaa3-56b4cfcea2af.png">

5. Find your Debian Download from Part 1 - Downloading Your Virtual Machine and put that download in this sgoinfre folder that you have just created.

### Part 1.2 - Virtual Box

#### Now head over to Virtual Box to continue on.
<img width="264" alt="Screen Shot 2022-06-24 at 12 18 12 PM" src="https://user-images.githubusercontent.com/58959408/175452234-79c7f008-10b2-4e4b-a602-95886d9e2508.png">

#### Don't have Virtual Box Installed?
Download it from Managed Software Center on an Apple Computer/Laptop.

<img width="1307" alt="Screen Shot 2022-06-24 at 12 27 24 PM" src="https://user-images.githubusercontent.com/58959408/175453219-e30d058a-946c-482b-85de-4feaad7b970d.png">


## Part 2 - Installing Your Virtual Machine

1. Click on `New`

![1*tkjZEbnHKqPGN24HQw_kRA](https://user-images.githubusercontent.com/58959408/174700376-2862e8e9-0a7a-4681-af3b-e82dbc7d9aa5.png)

2. Change Machine Folder to `sgoinfre/students/your_intra_login/Virtual Machine Name` and then click `continue` to move to the next step.

![1*WyFDl98AZfft999XCKD6kA](https://user-images.githubusercontent.com/58959408/174700651-8dc8e0a9-7709-4202-8a12-12a384ff6e3e.png)

3. Set Memory Size as `1024 MB` and click continue.

![1*SoVNIKT340ARlLvQ7RuwDA](https://user-images.githubusercontent.com/58959408/174701125-7a285b0d-7036-4bef-926b-271b0032d7ad.png)

4. Click `Create a Virtual Hard Disk Now` and then click `Create` to create the Hard Disk.

![1*PzVboJLyLTs7qJmgbdoBYA](https://user-images.githubusercontent.com/58959408/174701209-a5d10ea3-c634-4d49-b099-01d538fe0517.png)

5. Click `VDI (VirtualBox Disk Image)` and then click `Continue` to select VDI.

![1*6_D9jIyOW0jE3a6vF_UzXg](https://user-images.githubusercontent.com/58959408/174701340-d84f6c80-e09b-43ae-b31a-6dd5d6306f23.png)

6. Click `Dyamically Allocated` and then click `Continue` to only use space on your Hard Disk.

![1*HagpR-UD0HWCb7zRTeSQXQ](https://user-images.githubusercontent.com/58959408/174744677-eac5b679-49f7-4881-a59b-00a420cbe640.png)

7. Set Size as `12.00 GB` and then click `Continue` this should be enough for this project.

![1*rYdYJbPswCVCUa5pwKcRZA](https://user-images.githubusercontent.com/58959408/174745855-73880988-be69-45cc-bb6d-7c6c1a40c1ac.png)

8. Click `Settings` and then click `Storage` to view your Virtual Machine Storage.
	
<img width="1309" alt="Screen Shot 2022-06-24 at 12 51 09 PM" src="https://user-images.githubusercontent.com/58959408/175455682-e1b4c977-2f33-41cf-b3cc-3ad78b3254ce.png">

9. Click on `Optical Drive` (Optical Drive - far right blue small box).
	
![1*je75kGWjXl0M6PlqEzHgoA](https://user-images.githubusercontent.com/58959408/174701924-0c69938f-10ec-498f-adec-bacf073b4b99.png)

10. Click on `Choose a disk file...` (2nd option in the drop down).
	
![1*VDy31g0tePnUOuJ1cZQsxQ](https://user-images.githubusercontent.com/58959408/174702002-9b4fe4d2-3008-4375-9ec1-57f5e1425eb8.png)

11. Then click on the Virtual Machine file (.iso). 
	
![1*FOldzHFaQ2JS_phe6z6T4g](https://user-images.githubusercontent.com/58959408/174702161-957eb0b6-2803-407f-b018-c02f7615f027.png)

12. Click on your `Virtual Machine` and then click `'ok` to confirm you Virtual Machine Storage.
	
![1*Evj7Z2EOq102A1zUVgUnQg](https://user-images.githubusercontent.com/58959408/174702820-824e0acf-f919-4bfb-a619-eea8068fe309.png)

13. Click `Start` (The Green Arrow ➡️) to start your Virtual Machine.
	
![1*Yg53c1-01g4VzTqhcVEEcA](https://user-images.githubusercontent.com/58959408/174702806-1bd8fce3-aac6-44b3-84d9-c76252dfecd8.png)


## Part 3 - Accessing Your Virtual Machine

#### In the Virtual Machine, you will not have access to your mouse and will only use your Keyboard to operate your Virtual Machine. 

0. To increase your Virtual Machine size, press `command` + `c` on your Apple Keyboard at the same time and then use your mouse to drag the screen to the size you wish or do the following: 

<img width="666" alt="178788620-61064b58-0c0c-4f48-815e-60b4a8eaecae" src="https://user-images.githubusercontent.com/58959408/181727316-9a16b307-ea00-4116-a20a-261512f63a20.png">
	
1. Use the arrow keys on your keyboard 🔼 🔽 and press `Enter` on `Install` (This will start the installation proccess).

![1*-tV-M-4g6MH8h6pWJ27bCg](https://user-images.githubusercontent.com/58959408/174728861-fb9435a5-04e5-402c-80a3-f366c9b51be8.png)

2. Press `enter` on `English - English` or your language of preference.

![1*xeb8quQ-ccd5X51d8ToZRw](https://user-images.githubusercontent.com/58959408/174729529-f51630be-4206-4bfc-a13f-6278c67eb633.png)

3. Press `enter` on `Australia` or the country your installing this Virtual Machine.

![1*WixFq3GJF9OjeH-zTBTN7Q](https://user-images.githubusercontent.com/58959408/174729594-92ba0cdc-483c-4499-84ee-2d8f3b62f0b3.png)

4. Press `enter` on `American English` or your keyboard of preference.

![1*zKUk6R9tls_jiyY81ue8kA](https://user-images.githubusercontent.com/58959408/174729629-4f111978-4fc1-47ae-891f-aea693929480.png)

