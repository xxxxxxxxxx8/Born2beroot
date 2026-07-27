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

## ⚠️ NOTE: Whenever you are told to create a password, use the same password as everything.

5. Create a Host Name as your login, with 42 at the end (eg. prossi42) - write down your Host Name, as you will need this later on.
	
![1*r0fzgkzXOjK2DfsBCh7wEQ](https://user-images.githubusercontent.com/58959408/174729750-fbd2d215-b526-42c6-8ff0-b83f886c1f3c.png)

6. Leave this blank, press `enter` on Continue.
	
![1*81XjZBZg2bbNXunuxgnFPQ](https://user-images.githubusercontent.com/58959408/174729840-a85c3319-3a70-4922-9335-e4bb6f765ee9.png)

7. Create a Password for the Host Name - write this down as well, as you will need this later on. 
	
![1*ft498oj7syh4zVjI48U_tw](https://user-images.githubusercontent.com/58959408/174729894-d0fc794f-add8-49e7-9015-521f9e93958f.png)

8. Create a User Name without 42 at the end (eg. prossi) - write down your Host Name, as you will need this later on. 
	
![1*rhJWnMKN0TPBZwqRey9OeQ](https://user-images.githubusercontent.com/58959408/174729939-06933a35-5dd1-4924-848e-78d2023bb66e.png)

9. Create a Password for the User Name (you might as well use the same password as your Host Password) write this down as well, as you will need this later on. 

10. Press `enter` on your `Timezone` (The timezone your currently doing this project in).
	
![1*2i7svoURih_UIlRJ87rj5w](https://user-images.githubusercontent.com/58959408/174730349-76a4e74f-822b-4040-8d95-554d44fcb67c.png)

11. Press `enter` on `Guided - use entire disk and set up encrypted LVM` (Second to last option from the list).
	
![1*CsSx-ALmn8mMxvWicsNVAQ](https://user-images.githubusercontent.com/58959408/174730389-03e5dcd7-9472-4cab-bf88-fe3cc4dc0f4c.png)

12. Press `enter` on Select Disk to Partition.
	
![1*BTLz5sT6noL_SVQ7eq3u-A](https://user-images.githubusercontent.com/58959408/174730452-e267df43-2883-4760-85c4-010970fee329.png)

13. Press `enter` on Select `Separate /home, /var, and /tmp paritions` (Last option from the list).
	
![1*r5zFPA7R_9BtIqwyOpCCVw](https://user-images.githubusercontent.com/58959408/174730481-2641b9c0-c50d-4f2b-9e71-3896a0760e10.png)

14. Select `Yes` and press `Enter` to write the changes to disks and configure LVM.
	
![1*NHdo3JbApICz0Co2epPLFA](https://user-images.githubusercontent.com/58959408/174730521-780f5eb2-4955-48df-8c59-af9914674ee7.png)

15. Press `Enter` to `cancel` Erasing data as you won't need this for your Virtual Machine.
	
![1*KHmnCUJUWhf1minIdHNS4g](https://user-images.githubusercontent.com/58959408/174730626-c132041c-3070-405f-a8d8-60d620a1d770.png)

16. Create a Encryption passphrase - write this down as well, as you will need this later on.
	
![1*B0QL-gX7rZW5-RJyTD1uWw](https://user-images.githubusercontent.com/58959408/174730733-f306e051-4b0e-40de-93ab-56f2cdce45d5.png)

17. Retype the Encryption passphrase you just created.
	
![1*xE1owXa0ttpvcioaEwnutA](https://user-images.githubusercontent.com/58959408/174730804-796f6db1-8b59-4f8e-900c-1416f957db30.png)

18. Type in `max`and press enter on `Continue` to assign the amount of volume group to use for guided partitioning.
	
![1*SUFMu-qy3rBwIe9B0Bq3kg](https://user-images.githubusercontent.com/58959408/174730857-2de10217-3d42-41ca-8f43-fc91fddb64c6.png)

19. Press enter on `Finish partitioning and write changes to disk`. 

<img width="806" alt="Screen_Shot_2022-09-05_at_5 33 43_PM" src="https://user-images.githubusercontent.com/58959408/188408125-7c93acc1-b37f-4b9f-8189-b3cc4a83da8c.png">

20. Press enter on `Yes` for Partition Disks.
	
![1*yfXpHyGD37OGAOX7qs1Avw](https://user-images.githubusercontent.com/58959408/174730895-f70df93e-eb7e-493c-9374-edf58a47408c.png)

21. Press enter on `No` for Configure the package manager.
	
![1*Mfb1YHt4K3pZJ12TF2dXAw](https://user-images.githubusercontent.com/58959408/174730933-615891f8-d9fa-4312-ad78-d691bd648773.png)

22. Press `enter` in the country that your in.
	
![1*vqV-bN3zDMqTBAKz_u548w](https://user-images.githubusercontent.com/58959408/174731009-ca532fcf-ac41-4cde-bdae-2cf18c8bf519.png)

23. Press `enter` on deb.debian.org.
	
![1*bLnFC6MebhW1-YZlI2n9_A](https://user-images.githubusercontent.com/58959408/174731066-6bef2e53-c891-477f-8a29-7e9984a6d911.png)

24. Leave this blank and press `enter` on continue.
	
![1*e08pS8shLNmhZuFUrmuBwA](https://user-images.githubusercontent.com/58959408/174731175-bf4949d2-a832-4a1f-9282-c91195203c84.png)

25. Press `enter` on `no` for Configuring popularity-contest.
	
![1*1I6fHG3MHuovrarqj9PNnA](https://user-images.githubusercontent.com/58959408/174731301-88d7c53d-f5e2-46c3-b221-a8b40f70f81f.png)

26. Deselect `SSH server` and `standard system utilities` by pressing the `Space key` and then press `enter` on `Continue`.
	
![1*lGsuAQEwT0WBhb4kdUMp9g](https://user-images.githubusercontent.com/58959408/174731387-b4859ded-9a9f-409a-a9c9-57d1ec77cbfd.png)

