# ActiveDerectoryLabBuild
A walkthrough of how to build and set up a Free Microsoft AD lab (1 Domain Controller and 2 Windows Workstations) using Windows Server 2022 and Windows Enterprise 10 onto an Oracle VM VirtualBox


Lab Requirements
1 Windows Server
2 Windows Workstations (2 Windows 10 Enterprise Workstations)
60 GB Disk Space
16 GB RAM


1. First we will download the ISOs from Microsoft, so Open the browser and search for "Microsoft evaluation center"

-  
 <img width="2378" alt="Screen Shot 2023-09-01 at 1 46 40 PM" src="https://github.com/Prevail24/ADlabBuild/assets/47503200/978084e4-bb55-457e-bf92-b1386332c8c7">
-

2. Click the "Evaluate Now" on the Windows Server 2022 Card as shown below

-
<img width="2378" alt="Screen Shot 2023-09-01 at 1 48 23 PM" src="https://github.com/Prevail24/ADlabBuild/assets/47503200/93d5a6c1-7b6e-4fc6-8d84-e0ed20df3654">
-

3. Now click on the "Download the ISO" button to start the download of the 2022 Windows Server

-
<img width="2378" alt="Screen Shot 2023-09-01 at 1 53 26 PM" src="https://github.com/Prevail24/ADlabBuild/assets/47503200/cfd9ae8b-d510-4719-9333-15c01933dc06">
-

4. This will bring you to a screen where you will need to register to start the download. You do not need to enter your real name so feel free to enter a fake name and number and only really need an email address.

-
<img width="2378" alt="Screen Shot 2023-09-01 at 2 02 04 PM" src="https://github.com/Prevail24/ADlabBuild/assets/47503200/0b513e2b-e025-4a47-84f8-19056e12efd3">
-

5. Now you can select the ISO download in the language of your choice as shown in the screenshot below. 

-
<img width="2378" alt="Screen Shot 2023-09-01 at 2 05 43 PM" src="https://github.com/Prevail24/ADlabBuild/assets/47503200/4e019705-8e4a-4d76-b6a2-94c2e71a8ba1">
-

6. This will start the download, and at the time of writing this the Windows Server 2022 ISO is approximately 4.7 GB so it can take a little bit to download so next we will move on to download the Windows user machines


7. Next we will download the Windows 10 Enterprise and the Windows 11 Enterprise. We will need to go back to the Microsoft Evaluation Center landing page and you will see on the top menu bar, Select from the "Windows" drop-down menu as shown below;

-
<img width="2378" alt="Screen Shot 2023-09-01 at 2 17 05 PM" src="https://github.com/Prevail24/ADlabBuild/assets/47503200/ac1da4e8-843e-4d6d-99aa-743101eb2db5">
-

8. Now select "Download the ISO - Enterprise"

-
<img width="2378" alt="Screen Shot 2023-09-01 at 2 23 15 PM" src="https://github.com/Prevail24/ADlabBuild/assets/47503200/22af3e49-ddc3-4b40-9ea2-235cf1aa1755">
-

9. Now we are brought to the same register screen, The same thing goes. Enter the fake info if you would like and like the download button at the bottom, You will then be brought to the screen that will allow you to start your download.

-  
<img width="2378" alt="Screen Shot 2023-09-01 at 2 26 03 PM" src="https://github.com/Prevail24/ADlabBuild/assets/47503200/9598ea31-c5e6-4198-a90a-326fd1d79937">
-

10. Now select the language you would like, and select the ISO - Enterprise Downloads - 64-bit edition as shown below;

-
<img width="2378" alt="Screen Shot 2023-09-01 at 2 26 03 PM" src="https://github.com/Prevail24/ADlabBuild/assets/47503200/66fb100e-258b-4736-be4b-5fd94eb61d37">
-

11. You can continue with this next step and download the Windows 11 ISO (5.2 GB) if you would like or you can skip it and use 2 Windows 10 Enterprise (4.7 GB) workstations for this lab

    
12. Next we will download the Windows 11 ISO. It will be just like the Windows 10 download. So on the top menu bar select the "Windows" drop-down menu and select the "Windows 11 Enterprise" option

-
<img width="2378" alt="Screen Shot 2023-09-01 at 2 36 39 PM" src="https://github.com/Prevail24/ADlabBuild/assets/47503200/bdb4a984-7ee5-40ca-b4d3-a99ada9ac0ca">
-

13. Now enter the info you wish to share, none of it has to be real and can be 100% fake. select the Download button at the bottom. Now select the 64-bit ISO in the language you would like to start the download.


14. Great Job!! We now have all we need to start our Windows AD Lab!!




The next part will walk you through how to install the Domain Controller ISO on an Oracle VirtualBox Virtual Machine.
If you need to download Virtualbox go to https://www.virtualbox.org/ and you can download the latest version as seen below

-
<img width="2339" alt="Screen Shot 2023-09-02 at 10 45 30 AM" src="https://github.com/Prevail24/ADlabBuild/assets/47503200/354ba526-c481-4f8a-811f-a5d233b7023d">
-

15. Once your download is complete and you finish the install, click on the "New" button with the blue star icon on the top menu bar as shown below;


![Screen Shot 2023-09-02 at 10 50 16 AM](https://github.com/Prevail24/ADlabBuild/assets/47503200/fbb76df6-eaba-4eb0-95ff-f4c72bdb6d43)


16. Now the Create Virtual Machine Window will pop up and here you will enter or select the info to see underlined in red. I named this DomainController-2022 to keep it simple as seen below. Also, there will be no naming errors that you will run into. But you can name it whatever you would like. 

-
![Screen Shot 2023-09-02 at 10 59 22 AM](https://github.com/Prevail24/ADlabBuild/assets/47503200/49719af8-537c-490b-82d3-0bbbf97b1c6d)
-

17. Next go to the Hardware dropdown menu and here we will select how much memory and processing speed our computer will allocate to this VM running the Windows Server 2022.
    As you can see in the screenshot below will be allocating 8000MB (of 32768 MB available) of RAM and 2 CPU processors. (of 8 CPU processors available). Depending on your computer's processors and available RAM yours will probably be different. the minimum I would select would be 4 MB of RAM and 1 CPU. You 
    can do more but overdoing it will take away from your computer's memory and computing speed and could cause it to crash. We will build this with more and then set it back down once we have setup the domain controller. You will be able to change the memory and CPU allocation from the settings later so don't worry if its a little higher than you would like now.

-
-
![Screen Shot 2023-09-02 at 11 13 29 AM](https://github.com/Prevail24/ADlabBuild/assets/47503200/a23b13d8-b809-4f40-8a4b-82eaef0d67e1)
-
-

18. Now go to the Hard Disk drop-down menu and everything is how we would like it to be. So we will now click the Finish button on the bottom.


19. Now we will have to change the storage from the top menu from the Floppy drive and click the little CD icon on the side as shown below;

-
![Screen Shot 2023-09-02 at 11 36 34 AM](https://github.com/Prevail24/ADlabBuild/assets/47503200/def5b58b-9cbf-48e1-995a-2974a4145be2)
-

20. After you have selected the CD icon you will see this menu pop up;

-
![Screen Shot 2023-09-02 at 11 38 26 AM](https://github.com/Prevail24/ADlabBuild/assets/47503200/8fccd427-08cd-45d0-a8c7-49af217e6751)
-

21. Here you will select the name of the downloaded file of the Windows Server 2022 we downloaded in steps 5 and 6.    


22. This will automatically start the Windows Server 2022 that we named 'DomainController-2022'


23. If you run into the error shown below, you will need to go back up and redo steps 19, 20, and 21!

-
![Screen Shot 2023-09-02 at 11 21 18 AM](https://github.com/Prevail24/ADlabBuild/assets/47503200/1c824b00-3fc3-4864-b066-05337950c9cb)
-

24. Once the initial setup is complete you will see a screen like this;

-
![Screen Shot 2023-09-02 at 11 48 17 AM](https://github.com/Prevail24/ADlabBuild/assets/47503200/22ff3ff1-bc92-4f87-b9c4-a52d90f150dc)
-

25. Select Next

-
![Screen Shot 2023-09-02 at 11 51 32 AM](https://github.com/Prevail24/ADlabBuild/assets/47503200/7a916dd9-3d9e-4a67-b708-621714f9f475)
-

26. Now select Install Now

-
![Screen Shot 2023-09-02 at 11 51 32 AM](https://github.com/Prevail24/ADlabBuild/assets/47503200/b08be313-fb2d-4de7-8148-9c755370e1e0)
-

27. Now make sure to select the 'Windows Server 2022 Standard Evaluation (Desktop Experience)' as shown below and select next.

-
![Screen Shot 2023-09-02 at 11 53 57 AM](https://github.com/Prevail24/ADlabBuild/assets/47503200/3b416295-b7d5-4386-8911-208e0e705a28)
-

28. Next check the box for the terms and conditions and select Next.

-
![Screen Shot 2023-09-02 at 11 56 37 AM](https://github.com/Prevail24/ADlabBuild/assets/47503200/1f7c3d74-d437-450d-ab28-26dd35f3c7f8)
-

29. Now select the 'Custom: Install Microsoft Server Operating System only (advanced)'

-
![Screen Shot 2023-09-02 at 11 57 31 AM](https://github.com/Prevail24/ADlabBuild/assets/47503200/2428d747-2e27-4383-bc78-a404fa9c113b)
-

29. Now Select 'New'

-
![Screen Shot 2023-09-02 at 12 00 15 PM](https://github.com/Prevail24/ADlabBuild/assets/47503200/8a32ac4c-7090-4b48-9fe3-b0d088a27022)
-

30. Select 'Apply'

-
![Screen Shot 2023-09-02 at 12 02 16 PM](https://github.com/Prevail24/ADlabBuild/assets/47503200/6b06b233-fcca-405e-89a9-aaa622fe700e)
-

31. Then select 'Ok' and it should have split the drive into multiple partitions as seen below;

-
![Screen Shot 2023-09-02 at 12 05 03 PM](https://github.com/Prevail24/ADlabBuild/assets/47503200/e620a358-3034-4c52-a964-9ddc464c121f)
-

32. Now this will start installing everything and will take a little while depending on how much memory and CPUs have been allocated to the VM. After it installs it will reboot.


33. Next we will be asked for a password for the Administrators account. I will be using a weak password to start this as there will be no personal information on it. Feel free to use whatever password you would like and click the finish button.

-
![Screen Shot 2023-09-02 at 12 31 10 PM](https://github.com/Prevail24/ADlabBuild/assets/47503200/b2dc22ce-2413-4f45-b639-5d9bc670ccb1)
-

34. Now you should be returned to this locked login screen. You will need to press Ctrl+Alt+Delete to unlock to be able to log in. 

-
![Screen Shot 2023-09-02 at 12 35 49 PM](https://github.com/Prevail24/ADlabBuild/assets/47503200/270eff4c-5c8a-4da0-aaab-df4f7282bc1c)
-

35. First a pop-up will ask if you want to make your network discoverable select 'Yes'. Now that we have logged in we will have a couple of settings to change.

-
<img width="1017" alt="Screen Shot 2023-09-02 at 12 39 42 PM" src="https://github.com/Prevail24/ADlabBuild/assets/47503200/ec6e0b67-d4e5-4668-b399-2334337c5b55">
-

36. First we will change the name of our machine, in the search bar at the bottom type in 'name'. Select the 'View your PC name' option that pops up.

-
![Screen Shot 2023-09-06 at 11 48 42 AM](https://github.com/Prevail24/ADlabBuild/assets/47503200/8b126730-6900-4457-b508-df922670779e)
-

37. Now select the 'Rename this PC' button.

-
![Screen Shot 2023-09-06 at 11 50 23 AM](https://github.com/Prevail24/ADlabBuild/assets/47503200/bb28ad1a-6ad8-40ab-b0ed-23309b869dca)
-

38. Now I will rename this 'DomainController-2022-DC' which will make things much easier when we have several machines connected to our network. then click 'Next'

-
![Screen Shot 2023-09-06 at 11 54 40 AM](https://github.com/Prevail24/ADlabBuild/assets/47503200/4d8ee358-9e2d-4803-856d-c811f90958af)
-

39. Now we will have to restart the machine in order for the changes to take effect. Let's do that now. Select the 'Restart now' button

-
![Screen Shot 2023-09-06 at 11 59 23 AM](https://github.com/Prevail24/ADlabBuild/assets/47503200/6796b291-1153-4159-a1e6-ccda9087092d)
-

40. Once our machine restarts, on the top menu bar, select the 'Manage' button and from the dropdown menu select the 'Add Roles and Features' option;

-
![Screen Shot 2023-09-06 at 11 34 11 AM](https://github.com/Prevail24/ADlabBuild/assets/47503200/87119633-94da-4b5c-9f31-a765708f3150)
-

41. Now select the 'Next' button on the following three screens as shown below;

-
![Screen Shot 2023-09-06 at 11 41 04 AM](https://github.com/Prevail24/ADlabBuild/assets/47503200/32b4fc77-6b24-4b8c-911b-8834313e76c5)
![Screen Shot 2023-09-06 at 11 44 18 AM](https://github.com/Prevail24/ADlabBuild/assets/47503200/0514e9e2-d438-4288-89df-5cf868128090)
![Screen Shot 2023-09-06 at 12 08 11 PM](https://github.com/Prevail24/ADlabBuild/assets/47503200/cce9980b-ce7d-427c-9068-85ac6f32a93c)
-

42. On the fourth screen, check the 'Active Directory Domain Services' box which will allow us to have our domain. This is commonly referred to as A.D.D.S.

-
![Screen Shot 2023-09-06 at 12 09 47 PM](https://github.com/Prevail24/ADlabBuild/assets/47503200/bdb07261-9b68-4a24-949c-1914c9dcf76a)
-

43. On the pop-up Wizard select 'Add Features' as seen below;

-
![Screen Shot 2023-09-06 at 12 13 24 PM](https://github.com/Prevail24/ADlabBuild/assets/47503200/c6366466-0c76-4444-b5f4-8dedaeb06d41)
-

44. Now click the 'Next' button;

-
![Screen Shot 2023-09-06 at 12 16 00 PM](https://github.com/Prevail24/ADlabBuild/assets/47503200/c3fc0942-5183-45d6-91a9-b4622175b0d8)
-

45. On the Confirm installations selections window, check the 'Restart the destination server automatically if required' box and select the 'Yes' box on the pop-up window as seen below.

-
![Screen Shot 2023-09-06 at 12 19 02 PM](https://github.com/Prevail24/ADlabBuild/assets/47503200/b40f8159-ad85-460a-8744-616b92746e15)
-

46. Now click 'Install'. 

-
![Screen Shot 2023-09-06 at 12 42 05 PM](https://github.com/Prevail24/ADlabBuild/assets/47503200/b2f133ff-77e5-448a-83aa-db643b48fb5d)
-

47. Now it will install our domain controller. After the installation is finished, move on to the next step.

-
![Screen Shot 2023-09-06 at 12 44 48 PM](https://github.com/Prevail24/ADlabBuild/assets/47503200/536f1934-559a-40da-b942-3f5414884027)
![Screen Shot 2023-09-06 at 12 51 59 PM](https://github.com/Prevail24/ADlabBuild/assets/47503200/6f86d433-4b57-4a9d-8e12-b91e8ebf4d54)
-

48. Now select the 'Promote this server to a domain controller' option. You can also click on the flag on the top menu bar and change it that way.

-
<img width="1819" alt="Screen Shot 2023-09-06 at 12 54 04 PM" src="https://github.com/Prevail24/ADlabBuild/assets/47503200/814c5807-d68a-42e6-b96d-0eb017447d28">
![Screen Shot 2023-09-06 at 12 57 30 PM](https://github.com/Prevail24/ADlabBuild/assets/47503200/e0131794-ca32-40d2-82e2-4dd34d8f4666)
-

49. Next we will select the 'Add a new forest' option and to keep it simple with the naming conventions will be calling this FOREST.local. Select next and will take a moment to load.

-
![Screen Shot 2023-09-06 at 1 00 19 PM](https://github.com/Prevail24/ADlabBuild/assets/47503200/cad220f0-ad2e-4164-a9d6-e845224d2fea)
-

50. On the 'Domain Controller Options' Wizard window, you can enter the same password as the admin account to keep it simple, and select 'Next'. The password is 'Password123'. You will want a much stronger password if setting this up for real use.

-
![Screen Shot 2023-09-06 at 1 05 30 PM](https://github.com/Prevail24/ADlabBuild/assets/47503200/b0b62fcb-cf11-4f3c-a039-bb3eb3c2c102)
-

51. On the following window select 'Next'

-
![Screen Shot 2023-09-06 at 1 09 31 PM](https://github.com/Prevail24/ADlabBuild/assets/47503200/ad12b5fc-e523-4089-b91d-9e5e09c0a324)
-

52. Now our name will take a second to load on our NetBIOS, once that is finished select 'Next';

-
![Screen Shot 2023-09-06 at 1 20 04 PM](https://github.com/Prevail24/ADlabBuild/assets/47503200/3bd77ed5-cbce-426f-a1ac-a6290f121dc9)
-

53. On the following screen, select 'Next';

-
![Screen Shot 2023-09-06 at 1 21 34 PM](https://github.com/Prevail24/ADlabBuild/assets/47503200/7bb59c55-6d4a-4a01-80d3-f0c39e7be177)
-

54. On the following screen, select 'Next';

-
![Screen Shot 2023-09-06 at 1 22 57 PM](https://github.com/Prevail24/ADlabBuild/assets/47503200/0eef3fac-8b66-4c58-a1a9-505a12f75d81)
-

55. It will now review the prerequisites and once you see the green check mark at the top it is complete;

-
![Screen Shot 2023-09-06 at 1 25 15 PM](https://github.com/Prevail24/ADlabBuild/assets/47503200/305fed5e-2bfa-4c34-98c1-4c513baedecb)
-

56. Now click the install button at the bottom;

-
![Screen Shot 2023-09-06 at 1 25 15 PM](https://github.com/Prevail24/ADlabBuild/assets/47503200/5aece20a-95aa-45bb-83bd-c59c6b1759e1)
-

57. Now it will install and after a moment we will need to restart our machine and we will then be able to login to our new Domanin Controller!

-
![Screen Shot 2023-09-06 at 1 28 41 PM](https://github.com/Prevail24/ADlabBuild/assets/47503200/ae6795df-66a0-43c6-b719-c889a7d4f00d)
-

58. After the machine reboots, you will see that we will be able to login to the FOREST/Administrator 

-
![Screen Shot 2023-09-06 at 1 33 19 PM](https://github.com/Prevail24/ADlabBuild/assets/47503200/7fe5afc0-8faa-4080-b476-14e2addf3ef2)
-

59. That is it for this part of the Domain Controller setup. You can now shut down the domain controller. We will now move on to setting up our two identical (almost!) user Workstations.


-
-
*********************
Part 2
*********************
-
-

*** Here we will be setting up two identical user workstations. I will not show the steps to the second machine as they are the exact same aside from the user name. 
If your computer has enough power and memory you can install both at the same time. aside from the name of the machine you will run this next part twice! If not you will have to run each one separately. 
Again, This guide will walk you through only one workstation as this is already a long walk-through.  ***

1. We will now start a new VM from our Oracle VirtualBox. Once again Select the 'New' button on the top menu

![Screen Shot 2023-09-07 at 3 15 51 PM](https://github.com/Prevail24/ActiveDirectoryLabBuild/assets/47503200/85bef7e4-9031-40ad-a54a-f9ac71fc5e34)

2. We will name this machine User1 to keep it simple. Select the Windows 10 ISO image, and it should be recognized as Windows 10 and it will fill in the rest for us.

![Screen Shot 2023-09-07 at 3 21 03 PM](https://github.com/Prevail24/ActiveDirectoryLabBuild/assets/47503200/8607ea56-4195-4bc1-83c5-5beea1fbeed3)

3. I will be giving this machine 4MB RAM to start and not change the rest of the settings. Use the appropriate amount for your machine based on your computer specs. You can use 2MB and that will be fine.

![Screen Shot 2023-09-07 at 3 25 25 PM](https://github.com/Prevail24/ActiveDirectoryLabBuild/assets/47503200/3f06a315-a53f-4264-833f-edd1e64a3bd2)

4. Now we will have to change the storage from the top menu and remove the Floppy drive by clicking the little hard-disk icon on the side as shown below;

![Screen Shot 2023-09-07 at 3 29 53 PM](https://github.com/Prevail24/ActiveDirectoryLabBuild/assets/47503200/48a3aa2d-cccc-4544-bea5-1565303a706e)

5. Now Select the Start button on the top menu bar. After it loads we will be taken through the setup similar to the server we did previously. Select Next, and then Select the 'Install Now' button

![Screen Shot 2023-09-07 at 3 33 50 PM](https://github.com/Prevail24/ActiveDirectoryLabBuild/assets/47503200/ba9e59a0-85e3-4b6e-9c07-7150ec321364)
![Screen Shot 2023-09-07 at 3 35 31 PM](https://github.com/Prevail24/ActiveDirectoryLabBuild/assets/47503200/c0a53cf2-a0d3-47d4-8e18-c6c0d9915140)

6. Accept the terms and click next

![Screen Shot 2023-09-07 at 3 40 29 PM](https://github.com/Prevail24/ActiveDirectoryLabBuild/assets/47503200/8a1726f3-a5ca-49b2-86a8-d52cc7786698)

7. Select 'Custom Install' just as before with our domain controller.

![Screen Shot 2023-09-07 at 3 43 54 PM](https://github.com/Prevail24/ActiveDirectoryLabBuild/assets/47503200/088317fe-8a42-4929-bf6e-d997d3a32672)

8. Select the 'New' button with the star next to it, then click Apply when the size option pops up, then select 'OK' on the pop-up window;

![Screen Shot 2023-09-07 at 3 45 24 PM](https://github.com/Prevail24/ActiveDirectoryLabBuild/assets/47503200/65723603-0325-4535-8a8c-f1f41dbc4788)
![Screen Shot 2023-09-07 at 3 47 12 PM](https://github.com/Prevail24/ActiveDirectoryLabBuild/assets/47503200/f20afc86-101c-41e9-ac1a-4d01ce4dd6f6)

9. Now click 'Next';

![Screen Shot 2023-09-07 at 3 49 07 PM](https://github.com/Prevail24/ActiveDirectoryLabBuild/assets/47503200/c86cf4f1-2331-47c5-9973-240cc4e721d9)

10. It will now begin Installing and will take a few moments. You can take this time to start and do the exact same steps on your second User workstation if you would like. I will be calling mine, you guessed it! User2
11. Once it finishes installing select your Region.

![Screen Shot 2023-09-07 at 4 04 58 PM](https://github.com/Prevail24/ActiveDirectoryLabBuild/assets/47503200/45754ee8-6f0f-4d9e-90e3-a1efe7570aaf)

12. Select you Keyboard layout. If you dont know, select US, then skip the second layout screen;

![Screen Shot 2023-09-07 at 4 06 42 PM](https://github.com/Prevail24/ActiveDirectoryLabBuild/assets/47503200/d9b7b181-2b7a-4d21-9948-a1e01e871090)

13. You will be brought to a screen where you can enter an email address as seen below. Select 'Domain join instead' at the bottom

![Screen Shot 2023-09-07 at 4 11 44 PM](https://github.com/Prevail24/ActiveDirectoryLabBuild/assets/47503200/cc029e2d-eb6b-4b5a-988c-6e927371bbff)

14. On this screen you can enter the user name of the person using this. here i will enter my name to keep it simple. Select next and enter your password and the confirm it;

![Screen Shot 2023-09-07 at 4 15 43 PM](https://github.com/Prevail24/ActiveDirectoryLabBuild/assets/47503200/400f9b23-fb95-479e-939e-14ab39ba8bfb)
![Screen Shot 2023-09-07 at 4 16 39 PM](https://github.com/Prevail24/ActiveDirectoryLabBuild/assets/47503200/7fa9086f-79e0-4de8-a581-209e5c670b6f)
![Screen Shot 2023-09-07 at 4 17 15 PM](https://github.com/Prevail24/ActiveDirectoryLabBuild/assets/47503200/88ea9aff-d102-40c1-8754-0273bf5a1191)

15. Now select your security questions.

![Screen Shot 2023-09-07 at 4 18 17 PM](https://github.com/Prevail24/ActiveDirectoryLabBuild/assets/47503200/d0e9932c-0cec-4aa4-a16c-79c15862dfa7)

16. Next, because this is just a Lab build meant to learn and experiment and to even break-in, we will turn all the privacy settings to 'No' and click accpet

![Screen Shot 2023-09-07 at 4 20 43 PM](https://github.com/Prevail24/ActiveDirectoryLabBuild/assets/47503200/1030152c-aed0-4c7a-82b4-e0a0659fa90b)

17. Now click 'Not now' for the Cortana settings.

![Screen Shot 2023-09-07 at 4 21 40 PM](https://github.com/Prevail24/ActiveDirectoryLabBuild/assets/47503200/c43e39cc-20a8-461e-9c16-3b0b9047ff70)

18. Now this will take several mins. Take this time to do the same steps with your second workstation, using a different username.
19. Once it loads we will now change the PC name just like before. Type in 'name' in the bottom search bar and select 'View your PC name' from the option at the top;

![Screen Shot 2023-09-07 at 4 30 09 PM](https://github.com/Prevail24/ActiveDirectoryLabBuild/assets/47503200/e8638571-ea2c-4605-a5d6-57ca7bdff90c)

21. Select 'Rename this PC'

![Screen Shot 2023-09-07 at 4 31 47 PM](https://github.com/Prevail24/ActiveDirectoryLabBuild/assets/47503200/f3543224-584f-4f4e-a825-a6d1a6792490)

22. Name it what you would like it to be.

![Screen Shot 2023-09-07 at 4 33 28 PM](https://github.com/Prevail24/ActiveDirectoryLabBuild/assets/47503200/0acfbf63-51e2-43e9-b043-3f7b9c6d5d84)

23. We will now restart our machine for the changes to take effect;

![Screen Shot 2023-09-07 at 4 34 03 PM](https://github.com/Prevail24/ActiveDirectoryLabBuild/assets/47503200/90246c94-7c87-42c1-be14-06c0ad22328b)

24. Great job, If you did everything correctly you will now have two user workstations that are ready to connect to the domain controller.





