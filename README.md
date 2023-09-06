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


The next part will walk you through how to install the Domain Controller ISO on an Oracle VirtualBox Virtual Machine.
If you need to download Virtualbox go to https://www.virtualbox.org/ and you can download the latest version as seen below

<img width="2339" alt="Screen Shot 2023-09-02 at 10 45 30 AM" src="https://github.com/Prevail24/ADlabBuild/assets/47503200/354ba526-c481-4f8a-811f-a5d233b7023d">

15. Once your download is complete and you finish the install, click on the "New" button with the blue star icon on the top menu bar as shown below;

![Screen Shot 2023-09-02 at 10 50 16 AM](https://github.com/Prevail24/ADlabBuild/assets/47503200/fbb76df6-eaba-4eb0-95ff-f4c72bdb6d43)

16. Now the Create Virtual Machine Window will pop up and here you will enter or select the info to see underlined in red. I named this DomainController-2022 to keep it simple as seen below. Also, there will be no naming errors that you will run into. But you can name it whatever you would like. 

![Screen Shot 2023-09-02 at 10 59 22 AM](https://github.com/Prevail24/ADlabBuild/assets/47503200/49719af8-537c-490b-82d3-0bbbf97b1c6d)

17. Next go to the Hardware dropdown menu and here we will select how much memory and processing speed our computer will allocate to this VM running the Windows Server 2022.
    As you can see in the screenshot below will be allocating 8000MB (of 32768 MB available) of RAM and 2 CPU processors. (of 8 CPU processors available). Depending on your computer's processors and available RAM yours will probably be different. the minimum I would select would be 4 MB of RAM and 1 CPU. You 
    can do more but overdoing it will take away from your computer's memory and computing speed and could cause it to crash. We will build this with more and then set it back down once we have setup the domain controller. You will be able to change the memory and CPU allocation from the settings later so don't worry if its a little higher than you would like now.

![Screen Shot 2023-09-02 at 11 13 29 AM](https://github.com/Prevail24/ADlabBuild/assets/47503200/a23b13d8-b809-4f40-8a4b-82eaef0d67e1)


18. Now go to the Hard Disk drop-down menu and everything is how we would like it to be. So we will now click the Finish button on the bottom.

19. Now we will have to change the storage from the top menu from the Floppy drive and click the little CD icon on the side as shown below;

![Screen Shot 2023-09-02 at 11 36 34 AM](https://github.com/Prevail24/ADlabBuild/assets/47503200/def5b58b-9cbf-48e1-995a-2974a4145be2)

20. After you have selected the CD icon you will see this menu pop up;

![Screen Shot 2023-09-02 at 11 38 26 AM](https://github.com/Prevail24/ADlabBuild/assets/47503200/8fccd427-08cd-45d0-a8c7-49af217e6751)

21. Here you will select the name of the downloaded file of the Windows Server 2022 we downloaded in steps 5 and 6.    

22. This will automatically start the Windows Server 2022 that we named 'DomainController-2022'

23. If you run into the error shown below, you will need to go back up and redo steps 19, 20, and 21!

![Screen Shot 2023-09-02 at 11 21 18 AM](https://github.com/Prevail24/ADlabBuild/assets/47503200/1c824b00-3fc3-4864-b066-05337950c9cb)

24. Once the initial setup is complete you will see a screen like this;

![Screen Shot 2023-09-02 at 11 48 17 AM](https://github.com/Prevail24/ADlabBuild/assets/47503200/22ff3ff1-bc92-4f87-b9c4-a52d90f150dc)

25. Select Next

![Screen Shot 2023-09-02 at 11 51 32 AM](https://github.com/Prevail24/ADlabBuild/assets/47503200/7a916dd9-3d9e-4a67-b708-621714f9f475)

26. Now select Install Now

![Screen Shot 2023-09-02 at 11 51 32 AM](https://github.com/Prevail24/ADlabBuild/assets/47503200/b08be313-fb2d-4de7-8148-9c755370e1e0)

27. Now make sure to select the 'Windows Server 2022 Standard Evaluation (Desktop Experience)' as shown below and select next.

![Screen Shot 2023-09-02 at 11 53 57 AM](https://github.com/Prevail24/ADlabBuild/assets/47503200/3b416295-b7d5-4386-8911-208e0e705a28)

28. Next check the box for the terms and conditions and select Next.

![Screen Shot 2023-09-02 at 11 56 37 AM](https://github.com/Prevail24/ADlabBuild/assets/47503200/1f7c3d74-d437-450d-ab28-26dd35f3c7f8)

29. Now select the 'Custom: Install Microsoft Server Operating System only (advanced)'

![Screen Shot 2023-09-02 at 11 57 31 AM](https://github.com/Prevail24/ADlabBuild/assets/47503200/2428d747-2e27-4383-bc78-a404fa9c113b)

29. Now Select 'New'

![Screen Shot 2023-09-02 at 12 00 15 PM](https://github.com/Prevail24/ADlabBuild/assets/47503200/8a32ac4c-7090-4b48-9fe3-b0d088a27022)

30. Select 'Apply'

![Screen Shot 2023-09-02 at 12 02 16 PM](https://github.com/Prevail24/ADlabBuild/assets/47503200/6b06b233-fcca-405e-89a9-aaa622fe700e)

31. Then select 'Ok' and it should have split the drive into multiple partitions as seen below;

![Screen Shot 2023-09-02 at 12 05 03 PM](https://github.com/Prevail24/ADlabBuild/assets/47503200/e620a358-3034-4c52-a964-9ddc464c121f)

32. Now this will start installing everything and will take a little while depending on how much memory and CPUs have been allocated to the VM. After it installs it will reboot.

33. Next we will be asked for a password for the Administrators account. I will be using a weak password to start this as there will be no personal information on it. Feel free to use whatever password you would like and click the finish button.

![Screen Shot 2023-09-02 at 12 31 10 PM](https://github.com/Prevail24/ADlabBuild/assets/47503200/b2dc22ce-2413-4f45-b639-5d9bc670ccb1)

34. Now you should be returned to this locked login screen. You will need to press Ctrl+Alt+Delete to unlock to be able to log in. 

![Screen Shot 2023-09-02 at 12 35 49 PM](https://github.com/Prevail24/ADlabBuild/assets/47503200/270eff4c-5c8a-4da0-aaab-df4f7282bc1c)

35. First a pop-up will ask if you want to make your network discoverable select 'Yes'. Now that we have logged in we will have a couple of settings to change.

<img width="1017" alt="Screen Shot 2023-09-02 at 12 39 42 PM" src="https://github.com/Prevail24/ADlabBuild/assets/47503200/ec6e0b67-d4e5-4668-b399-2334337c5b55">

36. First we will change the name of our machine, in the search bar at the bottom type in 'name'. Select the 'View your PC name' option that pops up.

![Screen Shot 2023-09-06 at 11 48 42 AM](https://github.com/Prevail24/ADlabBuild/assets/47503200/8b126730-6900-4457-b508-df922670779e)

37. Now select the 'Rename this PC' button.

![Screen Shot 2023-09-06 at 11 50 23 AM](https://github.com/Prevail24/ADlabBuild/assets/47503200/bb28ad1a-6ad8-40ab-b0ed-23309b869dca)

38. Now I will rename this 'DomainController-2022-DC' which will make things much easier when we have several machines connected to our network. then click 'Next'

![Screen Shot 2023-09-06 at 11 54 40 AM](https://github.com/Prevail24/ADlabBuild/assets/47503200/4d8ee358-9e2d-4803-856d-c811f90958af)

39. Now we will have to restart the machine in order for the changes to take effect. Let's do that now. Select the 'Restart now' button

![Screen Shot 2023-09-06 at 11 59 23 AM](https://github.com/Prevail24/ADlabBuild/assets/47503200/6796b291-1153-4159-a1e6-ccda9087092d)

40. Once our machine restarts, on the top menu bar, select the 'Manage' button and from the dropdown menu select the 'Add Roles and Features' option;

![Screen Shot 2023-09-06 at 11 34 11 AM](https://github.com/Prevail24/ADlabBuild/assets/47503200/87119633-94da-4b5c-9f31-a765708f3150)

41. Now select the 'Next' button on the following three screens as shown below;

![Screen Shot 2023-09-06 at 11 41 04 AM](https://github.com/Prevail24/ADlabBuild/assets/47503200/32b4fc77-6b24-4b8c-911b-8834313e76c5)
![Screen Shot 2023-09-06 at 11 44 18 AM](https://github.com/Prevail24/ADlabBuild/assets/47503200/0514e9e2-d438-4288-89df-5cf868128090)
![Screen Shot 2023-09-06 at 12 08 11 PM](https://github.com/Prevail24/ADlabBuild/assets/47503200/cce9980b-ce7d-427c-9068-85ac6f32a93c)

42. On the fourth screen, check the 'Active Directory Domain Services' box which will allow us to have our domain. This is commonly referred to as A.D.D.S.

![Screen Shot 2023-09-06 at 12 09 47 PM](https://github.com/Prevail24/ADlabBuild/assets/47503200/bdb07261-9b68-4a24-949c-1914c9dcf76a)

43. On the pop-up Wizard select 'Add Features' as seen below;

![Screen Shot 2023-09-06 at 12 13 24 PM](https://github.com/Prevail24/ADlabBuild/assets/47503200/c6366466-0c76-4444-b5f4-8dedaeb06d41)

44. Now click the 'Next' button;

![Screen Shot 2023-09-06 at 12 16 00 PM](https://github.com/Prevail24/ADlabBuild/assets/47503200/c3fc0942-5183-45d6-91a9-b4622175b0d8)

45. On the Confirm installations selections window, check the 'Restart the destination server automatically if required' box and select the 'Yes' box on the pop-up window as seen below.

![Screen Shot 2023-09-06 at 12 19 02 PM](https://github.com/Prevail24/ADlabBuild/assets/47503200/b40f8159-ad85-460a-8744-616b92746e15)

46. Now click 'Install'. 

![Screen Shot 2023-09-06 at 12 42 05 PM](https://github.com/Prevail24/ADlabBuild/assets/47503200/b2f133ff-77e5-448a-83aa-db643b48fb5d)

47. Now its going to install our domain controller. After the installation is finished move on to the next step.

![Screen Shot 2023-09-06 at 12 44 48 PM](https://github.com/Prevail24/ADlabBuild/assets/47503200/536f1934-559a-40da-b942-3f5414884027)

48.

49.

50.

51.

52.
