# ADlabBuild
A walkthrough of how I built and set up a Free Microsoft AD lab using Windows Server 2022 and Windows Enterprise 10 and 11 onto Oracle VM VirtualBox and VMware Workstation


Lab Requirements
1 Windows Server
2 Windows Workstations (1 Windows 10 Enterprise and 1 Windows 11 Enterprise)
60 GB Disk Space
16 GB RAM


1. First we will download the ISOs from Microsoft, so Open the browser and search for "Microsoft evaluation center"
  
 <img width="2378" alt="Screen Shot 2023-09-01 at 1 46 40 PM" src="https://github.com/Prevail24/ADlabBuild/assets/47503200/978084e4-bb55-457e-bf92-b1386332c8c7">

2. Click the "Evaluate Now" on the Windows Server 2022 Card as shown below

<img width="2378" alt="Screen Shot 2023-09-01 at 1 48 23 PM" src="https://github.com/Prevail24/ADlabBuild/assets/47503200/93d5a6c1-7b6e-4fc6-8d84-e0ed20df3654">

3. Now click on the "Download the ISO" button to start the download of the 2022 Windows Server

<img width="2378" alt="Screen Shot 2023-09-01 at 1 53 26 PM" src="https://github.com/Prevail24/ADlabBuild/assets/47503200/cfd9ae8b-d510-4719-9333-15c01933dc06">

4. This will bring you to a screen where you will need to register to start the download. You do not need to enter your real name so feel free to enter a fake name and number and only really need an email address.

<img width="2378" alt="Screen Shot 2023-09-01 at 2 02 04 PM" src="https://github.com/Prevail24/ADlabBuild/assets/47503200/0b513e2b-e025-4a47-84f8-19056e12efd3">

5. Now you can select the ISO download in the language of your choice as shown in the screenshot below. 

<img width="2378" alt="Screen Shot 2023-09-01 at 2 05 43 PM" src="https://github.com/Prevail24/ADlabBuild/assets/47503200/4e019705-8e4a-4d76-b6a2-94c2e71a8ba1">

6. This will start the download, and at the time of writing this the Windows Server 2022 ISO is approximately 4.7 GB so it can take a little bit to download so next we will move on to download the Windows user machines

7. Next we will download the Windows 10 Enterprise and the Windows 11 Enterprise. We will need to go back to the Microsoft Evaluation Center landing page and you will see on the top menu bar, Select from the "Windows" drop-down menu as shown below;

<img width="2378" alt="Screen Shot 2023-09-01 at 2 17 05 PM" src="https://github.com/Prevail24/ADlabBuild/assets/47503200/ac1da4e8-843e-4d6d-99aa-743101eb2db5">

8. Now select "Download the ISO - Enterprise"

<img width="2378" alt="Screen Shot 2023-09-01 at 2 23 15 PM" src="https://github.com/Prevail24/ADlabBuild/assets/47503200/22af3e49-ddc3-4b40-9ea2-235cf1aa1755">

9. Now we are brought to the same register screen, The same thing goes. Enter the fake info if you would like and like the download button at the bottom, You will then be brought to the screen that will allow you to start your download.
    
<img width="2378" alt="Screen Shot 2023-09-01 at 2 26 03 PM" src="https://github.com/Prevail24/ADlabBuild/assets/47503200/9598ea31-c5e6-4198-a90a-326fd1d79937">

10. Now select the language you would like, and select the ISO - Enterprise Downloads - 64-bit edition as shown below;

<img width="2378" alt="Screen Shot 2023-09-01 at 2 26 03 PM" src="https://github.com/Prevail24/ADlabBuild/assets/47503200/66fb100e-258b-4736-be4b-5fd94eb61d37">

11. You can continue with this next step and download the Windows 11 ISO (5.2 GB) if you would like or you can skip it and use 2 Windows 10 Enterprise (4.7 GB) workstations for this lab
    
12. Next we will download the Windows 11 ISO. It will be just like the Windows 10 download. So on the top menu bar select the "Windows" drop-down menu and select the "Windows 11 Enterprise" option

<img width="2378" alt="Screen Shot 2023-09-01 at 2 36 39 PM" src="https://github.com/Prevail24/ADlabBuild/assets/47503200/bdb4a984-7ee5-40ca-b4d3-a99ada9ac0ca">

13. Now enter the info you wish to share, none of it has to be real and can be 100% fake. select the Download button at the bottom. Now select the 64-bit ISO in the language you would like to start the download.
14. Great Job!! We now have all we need to start our Windows AD Lab!!

The next part will walk you through how to install the ISOs on Oracle VirtualBox and VMware Workstation
