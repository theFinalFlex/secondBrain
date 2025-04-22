bCvvRTcj4e-hOLJ0pAfbl  
kUDT4xB1Kr-tEPTcxJdQ0  
QIfnQsrz81-a6l6rdFCUG  
SieewIBLqh-fjFLEyTo4r  
JEqUYMGLj0-CaQwTlZxvZ  
4sRmWRs1bz-578deBAJqx  
wALPWf7qxM-bdRQLwU66P  
IFiZVDKHBk-4nrSkDnMUP

https://quizlet.com/sg/623978238/btl1-flash-cards/

# Lab) Hard Drive Investigation Solution

1. Digital Forensics
2. Disk Analysis With Autopsy
3. Lab) Hard Drive Investigation Solution

Complete

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/c1ff2d282d803e4fca88280eeb0ce5901eb160526800a58653a7433edf87484afe1bba3db286f0d7a3e1ab559c23.PNG)

After opening Autopsy, found within the ‘Autopsy For Disk Analsis’ folder on the Desktop, we'll be asked if we want to open a case, or create a new one - click on Create New Case. You'll be asked to provide some information, you can name the case anything you want.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/13f9edd4c729e15c595cd2199e6b0703a01ea836299bca63ea0a331650403e02f938a0fa6a2451565acf51858b21.PNG)

We need to select a Base Directory for our investigation, which needs to be an empty folder. Click on Browse, go to the Desktop, then click the icon in the top-right to create a new folder.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/5d34bf297cfe83965d5c7a803acd1395d0646ab8227c9d40ee611cc9760be7c11302f9d2c54a4e8f82df4c7416c1.PNG)

After clicking Next we'll have our case created within Autopsy. We need to click ‘Add Data Source’ in the top-left corner. When asked to select a host, leave it as the default option (first option) and click Next. We are now asked to import an image, leave it as the first option and browser to the Autopsy For Disk Analysis folder, then Laptop Image, and select the below file.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/39492c9e84c80f0c0fe6176f75eb3e7d357244565e64db93668175ff7206677fb2027603b2b9b3d097236523e788.PNG)

For Step 4 we're asked what Ingest Modules we want to run on the disk image, to help us quickly retrieve interesting information. Click Deselect All, and tick the two modules shown below.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/fb2583fa8fe48aa217531565c9dae4f3ef077d811e0a8e573f5f72ea0a1b96387e1cd24152b913c9f6da00a6d9f6.PNG)

Autopsy will now begin importing and processing the disk image and ingest modules. Leave this to run for about 10 minutes, then you'll be ready to start answering the questions!

---

**Question 1 - What operating system (and version of OS) is the suspect laptop running?**

To find the Operating System of the device we can look under ‘Data Artifacts > Operating System Information’. Scrolling to the right within the table in the left panel, we can see the OS listed as ‘Program Name’.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/1be2a1be291a99f3c17fcd219bb8ea939f28492bfa453aae6dbcdb9ff706c20aded629a6fe86f2e3d2f364d3133b.PNG)

---

**Question 2 - What is the hostname of the system?**

On the same section as above, towards the left of the table, we can see the Hostname listed as ‘Name’.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/86b49231cdca4045fb384a813423cfd8824b554d1a13992ec9ef4a292b44ac387bffafd8db54fe04a85f89e3f8ef.PNG)

---

**Question 3 - Look at Web Downloads that have been retrieved from the disk image. What file was downloaded at 2013-12-18 20:05:57 GMT?**

Still looking at the ‘Data Artifacts’ heading on the left panel, we have been asked to investigate Web Downloads. In the table on the right we can see ‘Date Accessed’, so we need to find the row that has the date from the timestamp in the question!

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/98e263d93f3005b866b084c2d0ad0188c13ddb9bc854fdea5a3d6a321720039930ac5f82eb4a8489e13524c2b40f.PNG)

---

**Question 4 - What is the full URL of the file that was downloaded at 2013-12-18 03:02:50 GMT?**

Looking in the same location, we need to find the row in the table that matches the timestamp in the question. After finding it, we can see the full URL in the column titled ‘URL’.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/fbed000932dc3e33e95733c1e60cad9bfa0c81a1e299283bc0cbadbd3f45ce6cd6b3d28003751ee56e47746e5257.PNG)

---

**Question 5 - Looking at Recent Documents, what is the full path for the file Pier.jpg?**

Remember LNK files, that we covered earlier in this domain? Files that are used as shortcuts to the real file located on disk. We can use LNK to identify when files have been accessed, and where they are stored. The sample applies here! Looking at the ‘Recent Documents’ menu item, we can find the Pier.lnk file, which is used to represent Pier.jpg - we can get the file path from the ‘Path’ column.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/cf87f0f201455b719ab993a4ce4e35372f076228bd4e338591ef614607688e65ca8902f24608bcd1f26ce575def7.PNG)

---

**Question 6 - Double click on vol2 to enter the virtual filesystem. Navigate to Program Files > GIMP 2. What is the file size of the directory named "lib"?**

Let's view the virtual file system, as if we were on the computer itself! Double-click on vol2, the largest partition within the filesystem.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/e35f317e223a0c36ca9a7dc152987cf8843c0724b58442b5ccf542f0dac10faeba99d2625e349cc671ff9bd86e5b.PNG)

Moving to Program Files, GIMP 2, we can see the folder we're interested in. The file size is shown as a column at the end of the highlighted section!

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/83c0a4401f11a2cd594e7ec40d723250bbf3a598cccc90449430ce33d655fb78a99605e57df29b18c2f8a380aa74.PNG)

---

**Question 7 - Go to the OS Accounts tab. When was the local administrator account last accessed? (Format: YYYY-MM-DD HH:MM:SS)**

Looking under the ‘OS Accounts’ section, we can see every local user that is on this computer. At the bottom we can see the Administrator account, giving us the time it was last accessed.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/7c416bfdae41f2a64e72ec29580c5c90997afc79988bc143825a91e0556d2e30a0c9a85c5ebbd5187af93dd7d628.PNG)

#### Great! You've made it to the end 💪

Domains List

# Lab) Metadata and File Carving Solution

1. Digital Forensics
2. Forensics Fundamentals
3. Lab) Metadata and File Carving Solution

Complete

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/6d8067908a09674cd3e45611172403324355329da4c6f65db9a5e6df8d07d2f1c84443dbe7671600286529b1131b.PNG)

All questions in this lab require a terminal session in the `Metadata and File Carving` directory, within the Desktop directory. Open the terminal from the icon on the bottom taskbar and type `**cd /home/ubuntu/Desktop/Metadata**` then press [Tab] to auto-complete the folder name, and press [Enter]. You will now be in the right location.

---

**Question 1 - [Metadata Analysis] Identify the author of the file "dummy.pdf"**

From the open terminal session run the command, the output of which will give you the author of the PDF.

`**exiftool dummy.pdf**`

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/77c6407396f82ebcc6a40e02e3572711b7d2b844a36d10f62b49cb8b60214d08fad39fd788133d2d3863fadca98f.png)

---

**Question 2 - [Metadata Analysis] Identify the camera model used for taking the picture "picture.jpg"**

In the same terminal session as the previous question, running the command will give you the answer to which camera took the picture.

`**exiftool picture.jpg**`

Alternatively, you can use grep to show only lines that feature the string ‘camera’ using `**exiftool picture.jpg | grep camera**`

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/3faff76732b2cc6404e27fba43185ac2d359d3b42ac93f55bbe65c1e30d67edbfde42d0ee2dc7adf118fee4c4655.png)

---

**Question 3 - [File Carving] Carve1.img is a disk image of a memory stick formatted in NTFS. Using carving methods (scalpel), find the unique image that has been deleted. What is the MD5 of the image?**

This is an updated guide to the following question. Please follow the steps exactly as written and displayed. If you prefer the old walkthrough, please find it below.

Open the terminal by right-clicking on the desktop and clicking on "Open Terminal Here". (DO NOT USE THE BLACK TERMINAL ON THE BOTTOM DASHBOARD, DOES NOT WORK WITH THIS METHOD).

![](https://i.imgur.com/5p8sZYP.png)

Enter the command: "sudo cp /etc/scalpel/scalpel.conf ./q3.conf" (q3.conf will appear on the left side of your terminal on the desktop with a lock icon).

![](https://i.imgur.com/OKg3N70.png)

Enter the command: "sudo chown ubuntu q3.conf" (The lock icon on q3.conf will disappear).

![](https://i.imgur.com/pPbLyUt.png)

Enter the command: "nano q3.conf" in the terminal.

Scroll down to "Graphics Files" and remove the #s on the "gif" and "jpg" (there will be 3 total). Then press CTRL+X, then "Y", and press "ENTER".

![](https://i.imgur.com/agEmWOa.png)

Enter the command: "mkdir outputq3" (outputq3 folder will appear on the left side of the terminal)

**Very Important:** DRAG THE OUTPUTQ3 FOLDER AND Q3.CONF INTO THE METADATA AND FILE CARVING FOLDER

![](https://i.imgur.com/dnTA3pm.png)

**Very Important:** RIGHT-CLICK ON THE METADATA AND FILE CARVING FOLDER AND CLICK "OPEN TERMINAL HERE"

![](https://i.imgur.com/FTPvGCm.png)

Enter the command "scalpel -c q3.conf carve1.img -o outputq3".

![](https://i.imgur.com/6sBSFXL.png)

Click on Metadata and File carving folder, click on outputq3 folder, click on jpg-2-0 folder, and right click on the white space where 00000000.jpg is located (not directly on it!) then click "open terminal here"

![](https://i.imgur.com/uQTUByk.png)

Enter the command "md5sum 00000000.jpg"

![](https://i.imgur.com/ksJns3Q.png)

**Old Walkthrough:**

First we'll start off by making a copy of the default **scalpel.conf** to the current directory, and set the owner of the newly copied file to the `ubuntu` user.  
`**sudo cp /etc/scalpel/scalpel.conf ./q3.conf**`  
`**sudo chown ubuntu q3.conf**`

Open up the **q3.conf** file for editing using `**nano q3.conf**`, and uncomment all of the image files to look similar to the image shown below:  
 

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/37852612774a56e962d4d9fa8c1982d9d00b3f58fd6d6056dcddef1a56b9336e1812adb8b0412fe13d4c085e443f.png)

Once this has been edited, press CTRL+X then Y then ENTER to exit. We need to create an empty directory for Scalpel to output the carved file to, so we'll run `**mkdir outputq3**`, and run the following command to find any image files within the .img file:  
`**scalpel -c q3.conf carve1.img -o outputq3**`

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/0f70e7e06a8f7f14e0bcc698aebaf619615d5f33657dd351132d608838d2ec19c0fd61b313d01a0cb6f87c4f36cd.png)

The only file which has been carved out is a single jpg file, this is the file which we need to find the MD5 hash.  
 

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/1b1671aca1377387079d36c637cf6a564c6ab944f249fde6ff1748edc94ecd5f96df0f59ffd99d8e658506673251.png)

#### Great! You've made it to the end 💪

Domains List

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/91658288b1873ca144e161fe0085eb2b82e1b267cc6bc5d322297b5164838f623f49ff5bb9e844498cf9ec28509e.PNG)

---

**Question 1 - Using the command: echo -n texthere | md5sum, what is the md5 hash of the following sentence (without the quotes): "BTL1 rocks!"**

Echo will write the provided words (strings) back to the terminal. But by piping it (sending the output to) md5sum, it will take ‘BTL1 rocks!’ and hash it using the MD5 algorithm, giving us the answer.

---

**Question 2 - Using the same command as above, but with a slight change, generate the sha256 hash of the same sentence**

By changing the pipe to md5sum to sha256 sum instead, we're get our answer for this question.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/ac5d279c1675702170c4df0b1b949356155786151aec8f5ff8b934cec729e6128f4a86fabbdbc21349ae990a3179.PNG)

---

**Question 3 - In PowerShell, what command would you use to retrieve the SHA1 hash value of a file named "hashthis.jpg"?**

In this hypothetical question, we know from the associated lesson that we can use the Get-FileHash cmdlet, using the algorithm flag (-algorithm) to specifically state SHA1. The answer is `**Get-FileHash -algorithm SHA1 hashthis.jpg**`.

---

**Question 4 - Using a linux terminal, what command would we use to retrieve the MD5 hash of a file named "hashthis.jpg"?**

In a Linux-based terminal, we would use the ‘sum’ command, with the hashing algorithm in front of it. So for MD5, we would use `**md5sum**`.

---

**Question 5 - Generate the MD5, SHA1, and SHA256 hashes of the image "tastypancakes.jpg" and submit the first 5 characters of each. Answer this question in the format: MD5First5 SHA1First5 SHA256First5**

So we know for this question we'll be using md5sum, sha1sum, and sha256. We could run these commands individually, or we can use `**&&**` to chain them together.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/b0056a03e6995aecf5ab91f8178c198a81a85ec92f2eddb0d17026a0904160257dda28443dcd5a3971e16d2db58f.PNG)

---

**Question 6 - On your host machine, find a website that decodes MD5 hashes and enter the value "1f3870be274f6c49b3e31a0c6728957f". What is the plaintext string?**

After a quick Google search, we found the website [MD5 Online | Free MD5 Decryption, MD5 Hash Decoder](https://www.md5online.org/md5-decrypt.html). Entering the MD5 hash in and clicking Decrypt, we are told this hash is the same as the string ‘apple’.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/6f276497a3e13466679e51c2a3d13dc8ebac7d96e20113629dd8ef2cc9e03834ac17bb985da7ba88989be0955954.PNG)

# Lab) Windows Investigation 1 Solution

1. Digital Forensics
2. Windows Investigations
3. Lab) Windows Investigation 1 Solution

Complete

This lesson provides a step-by-step guide on how we would approach this situation and answer all the questions!

---

**Question 1 - Analyze the .LNK files in the Shortcuts folder using Windows File Analyzer - What is the full file name of the PlagueRat file?**

Open Windows File Analyzer by right-clicking it and selecting ‘Run as Administrator’ `**(C:\\Users\\BTLOTest\\Desktop\\Windows Investigation One\\WFA.exe)**`, then choose **File** > **Analyze Shortcuts...** and choose **C:\\Users\\BTLOTest\\Desktop\\Windows Investigation One\\Shortcuts** folder.

Next, look a the row (marked in ==**red**==) and look at the file name (marked in ==**yellow**==).

We can see that ‘Plaguerat' is found in the Filename column. Looking along the row we find lots of useful information.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/377d6c38d33e0e479f7b2d71d1cafd0be7efa102f38bb10f3c1e954455ae323a76bef22a338988b070514f32b767.png)

---

**Question 2 - Analyze the .LNK files in the Shortcuts folder using Windows File Analyzer - What is the name of the ZIP file that PlagueRat was found in?**

Keep WFA open and look a the row (marked in ==**red**==) and look at the file name (marked in ==**yellow**==). We can see that this file was previously stored in the following ZIP file.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/8db35051debddfbbade4cb0179daac350b18baddd2e453e8556eb8a2516c5cdf24959e556cbbe1843c6b6a6a82d1.png)

---

**Question 3 - Analyze the .LNK files in the Shortcuts folder using Windows File Analyzer - What other file or files were in the ZIP file?**

Keep WFA open and look a the row (marked in ==**red**==) and look at the file name (marked in ==**yellow**==). Looking at the Linked path column we can see another file that has the same file path, telling us it was in the same ZIP.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/5a4dc07db241e67895b063ba5d1f41d8278b6cce17ec746bb3fe02812e72f8048f9df1b5b1787e1215609f600cd9.png)

---

**Question 4 - Analyze the Prefetch files using PECmd.exe - What is the full file name of the PlagueRat file in CMD.EXE-89305D47.pf?**

Open a command prompt and move to the location of PECmd.exe using `**cd "C:\Users\BTLOTest\Desktop\Windows Investigation One\PECmd\"**` , then run the following command:

`**PECmd.exe -f "C:\Users\BTLOTest\Desktop\Windows Investigation One\Prefetch\CMD.EXE-89305D47.pf"**`  
 

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/d5382da18f1538f312576f73ff188044845b639a73b27eae71b269d177f3e5e8ca165550e63c1bf86684673fe6a9.png)

Look for PLAGUERAT in the output on Line 13, where the file is found with the extension ‘.bat’ - a batch script file.  
 

---

**Question 5 - Analyze the Prefetch files using PECmd.exe - What is the full file path of the PlagueRat file in CMD.EXE-89305D47.pf? (Starting with \USERS\)**

Using the above screenshot from Q4 we can see the full file path listed on Line 13.

---

**Question 6 - Analyze the Prefetch files using PECmd.exe - Open all .pf files by pointing PECmd at the /prefetch/ directory using the -d flag. Add the following to your command -k "plaguerat.ps1" to highlight rows that mention this string in red - What two applications were used to open PlagueRat.ps1?**

Open a command prompt and move to the location of PECmd.exe, then run the following command:

`**PECmd.exe -k “plaguerat.ps1” -d "C:\Users\BTLOTest\Desktop\Windows Investigation One\Prefetch\"**`

Because we've used the -k flag to highlight string matches (PECmd.exe will also match certain strings by default, so not every red-highlighted line will be relevant to us) we can look for red lines to see if they contain ‘plaguerat.ps1’ or not. Going from the bottom of the output upwards we can find our first match:

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/b800388979620efa5ee3acc27c22cd6486f513a07d7c8d4d54bf29848b0e5602602f3916dc7b0d364a7ea85716a6.png)

Scrolling up, we find what prefetch file, and therefore the executable name, that interacted with our suspicious file:

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/7f90241e4473ad042767f90cc7f080f79de324513808ee63891fb5eee113cc15401c1f64181379b578dc82219475.png)

Going up again, we find another result:

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/54129d4ce3792545467f462fccfbf2e49139fdd2d7b1517518ce57406d3d8aa51440669e3a77be425c844bb0e75c.png)

Finding the top of this section, we can find the executable that ran it:

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/d79af53fca0ed21865549d71ec2320ee1c00bf19a61f58d2196f2c25200f8fec82e158b5c4a306250b2ec0c14e32.png)

---

**Question 7 - Analyze the Jump List using JumpList Explorer.exe - Find the website that was accessed by the user. What is the domain they visited?**

Since we are looking for a website, the best thing to look for is a browser. There are two entries for Microsoft Edge. In the bottom left panel we can see that a visited website is listed.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/e1f647214ddc6af5e3c8328416f5c5ff837823e1d129a8b7c12805ef361c599f664e347e50ff99ebd2548eb82c35.png)

---

**Question 8 - Analyze the Jump List using JumpList Explorer.exe - What browser was used to access this site?**

Based on the previous question, we know this was Microsoft Edge, or Edge.

#### Great! You've made it to the end 💪

Domains List

# Lab) Windows Investigation 2 Solution

1. Digital Forensics
2. Windows Investigations
3. Lab) Windows Investigation 2 Solution

Complete

**Question 1 - What web browsers have been used by the employee, listed in alphabetical order? (Use simplified browser names)**

Firstly, we'll open Browser History Viewer (BHV) inside the Windows Investigation Two folder on the Desktop. Once it has loaded, we'll go to File > Load History.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/5a24e8413213154e2d55474455cdaee04eaa18dc1ffbb2bb37eed78f22740c986503faabaeba2196adcd8aef1f86.PNG)

When we're prompted to load history capture, we'll click on the “…” button, and find the Capture folder.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/30b4e9a667391b8e7214aa0a8ba7ac4b47d0ed05fb7848b9cbb5c19d2dfec75d46b38b4095eb05ff77bcc36c3bd5.PNG)

Once BHV has imported the data, we can begin answering the questions!

On the first screen we can see the column on the far-right is titled ‘Web Browser (Profile)’. Using this we can identify the web browsers that have been used on the system. We simply need to read through the list and take note of the browser names. It's very important to note that there are 4 pages, which can be navigated using the arrows on the left-hand side of BHV. As the question is asking for simplified names, instead of ‘Edge Legacy’ we would enter ‘Edge’. We're also asked to provide them in alphabetical order, so we'll make sure we enter them correctly.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/32310ba5b570b3e527c09b89991bd4656e6530b926f48efb35fd052deb079c212dc25ed72e3e8a5763b2b423ad06.PNG)

---

**Question 2 - The company has a policy against employees visiting social media on corporate devices. What sites has the employee visited, listed alphabetically?**

To answer this question we need to focus on the ‘URL’ column, where we can see exactly what web resources have been visited by the user. This is a case of going through them all to identify the names of social media websites.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/d1232cea6f1bb786622e46f29a0152fedf2a8c176c9cc185436ad2a54be3a920904bc64cf51f97c8ae59a8ae4b92.PNG)

If you're not sure whether a platform is considered social media or not, a quick Google search can help you understand. As an example:

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/1aa5fe99295a8878f2deca07b964ccf6db7a40c4301404bdf052628ef60cca62433d965f2d62b506c162d3c2a8be.PNG)

To help you answer this question, there are 5 sites that we deem to be classed as social media. Make sure to put them in alphabetical order! We accept multiple variations for this answer.

The correct answer is Discord, Facebook, Reddit, Twitter, YouTube.

---

**Question 3 - Looking at Cached Images at (UTC) 19/06/2020 12:12:10 with the filename "everything-in-one-place-scenario-base[1].png", what is the subject line of the third email?**

For this question we're provided a date to help us identify the file of interest. We have two ways to find this date, which is stored in the ‘Last Fetched’ column of the Cached Images tab of BHV.

- Option One - Click on the header for Last Fetched to change the results to show in time ascending or time descending order. If the timestamps are in order, it'll be easier for us to find the correct timestamp.
- Option Two - Use the ‘Filter by date’ section on the right-hand panel. For this lab all of the results are on the same day, however in a real-world scenario, there would most likely be days or weeks worth of data, so this feature would be useful to look at specific days of activity easily.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/9e13c17213d4b1643f104849d4b84914cd35ceda3e8c9c8dde0a6cd39d12100cbe9f301fa2d873361951e1b523df.PNG)

Using the Last Fetched column, we find the right time and file (based on the Filename column).

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/d5b1693f47819cb23ccff09c4511acb74479295bc3efb4e2a9cc1276806201db6c95bbac9406e73b55c6d82110a5.PNG)

Looking at the bottom panel of BHV, if we select a file in the table, it will highlight the associated image. We can double-click the image to show it full size in a new window. Here we can get the answer to this question.

---

**Question 4 - What is the full URL of the music video the employee is listening to on Youtube?**

For this question we're going to head back to the Website History tab in the top left. Instead of searching through all of the URLs to find YouTube ones, we can use the ‘Filter by keyword’ search box in the top-right. If we type in YouTube, we'll only see URLs or Titles that include the string ‘youtube’.

After searching for this, we can quickly find the answer to the question.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/d2b7999aa32870c459bb33f7c234151530801315bd8f5f1e5acb0965795b70a10d9c6fb64cbe83bf0c06b40d0ea3.PNG)

---

**Question 5 - What is the name of the malicious file that was downloaded by the employee?**

To approach this question, we have three primary methods:

- Option One - Manually review all URLs until we see URLs that end in a filename, highlighting a download URL (such as securityblue.team/downloads/file.exe). This method will be time-consuming depending on the volume of records, but you could also identify other activities of interest during the search.
- Option Two - We could utilize the ‘Filter by keyword’ search box to look for file extensions, searching for phrases such as ‘.zip’, ‘.exe’, and others. These searches will reduce noise from records that don't contain file names, but we would need to go through every file type until we find what we're looking for. If we forget to search for a file type, we might miss the related activity.
- Option Three - All downloaded files in BHV are prefixed with “file:///”. We can use this to see the name of the file, and where it was saved on the system. This is the quickest way, and once we have retrieved the filename, we can then use that in the search box to find where it was downloaded from!

Using option three and filtering by most recent Date Visited first, we find a ZIP file with an unusual name. This is definitely worth investigating further!

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/b1ea4ba61281d08b0e4e455cc575d2f7731dc73b35b7e74365927296923bbaacfda17448a99bf782b5d7ff1fb9d3.PNG)

---

**Question 6 - Based on the employee's browsing history around the time of the file download, what is the likely source of the malicious URL?**

Now that we've found the suspicious file, we can start to look deeper. While the URL that's hosting the file is interesting to us, looking back further in time we can understand exactly how they got there. Searching for the filename we can find the hosting URL.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/e8d60e60b558ee781435cd69abdc761b766e34241c56e2e62f4d674f02ebd9bb9575833fa5fa0f35069faf22b2f7.PNG)

So we know that the user visited that URL and downloaded the file to their Desktop at 12:14:09. Let's clear all our filters by clicking on ‘Reset’ on the right-hand side. Next we'll use the Date Visited column to find the timestamp 19/06/2022 12:14:09, allowing us to see the records that occurred before this download event.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/97c0fa62eb6529af895244109fa1e9d5ae4eb0691799e6541f75a3fb67e57bbba98467989202fd2e6f43a22e3fd3.PNG)

Based on the information above, we can infer that the following journey was taken by the user:

- 1) User goes to Outlook's login page.
- 2) User successfully logs in and goes to their email inbox.
- 3) User downloads the zip file, most likely from an email in their inbox. The file is downloaded to their Desktop.

It's worth mentioning that we cannot be 100% sure that this activity represents a URL within an email, without actually having access to their inbox to confirm this finding. It is completely possible that the user logs in to their email account and then manually types in the URL within a browser to visit it. However, based on the information available to us, and the timestamps that are all very close together, the most likely explanation is a link within an email.

Therefore, the answer to this question will be the domain shown in the highlighted section 2.

---

**Question 7 - What is the domain name where the malware was downloaded from?**

Utilizing the process above, look at the **third** box. We see a strangely worded zip file being downloaded from the hxxp[://]secretbeauty[.]ge website.

**Disclaimer:** The website above is defanged for illustrative purposes. When submitting in the lab, the format should be **domain.tld** (non-defanged).

#### Great! You've made it to the end 💪

Domains List

Prev

 # Lab) Memory Analysis Investigation Solution

1. Digital Forensics
2. Memory Analysis With Volatility
3. Lab) Memory Analysis Investigation Solution

Complete

The first thing we're going to do is turn our shell into a Bash shell by simply typing ‘bash’. This will allow us to use functionality such as [Tab] autocomplete, using the up arrow to go to our previous commands, and more.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/e9ca4a37050c1eeb90859484c9cc4cd608ec5126561a0be0ea57106b5b881fdc4e14130664389731a92eab6c999d.png)

Reading the Instructions tab of the lab provides us with the following information: ‘_vol.py is located in the root file system directory (/volatility/) - you should open a terminal in this location and call vol.py directly, providing the path to the memory dumps (/home/ubuntu/Desktop/Volatility Exercise/)_’

Using our open terminal session, we'll move to the volatility file using `**cd /volatility/**`.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/470466dffd4570b83979aaee87a31c1d823f758b336dd4d21e879f94c64a7f9ad1e10641a68f20b878d6c8c8603a.png)

---

**Question 1 - memdump1.mem - Image identification 1 - In order to start a memory analysis with Volatility, the identification of the type of memory image is a mandatory step. Identify the suggested profile that you should use with that image (use the first one suggested by Volatility)**

To identify the profile we'll use the command `**python vol.py -f /home/ubuntu/Desktop/Volatility\ Exercise/memdump1.mem image info**`.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/258f17b0924c3947b538c68e0dd4b3e4c9d41237ad26e6b37dbdc72936356bfc1d127b95740a43e53a20e46e2598.png)

---

**Question 2 - memdump1.mem - Image identification 2 - How many processors are identified by Volatility?**

In the highlighted section we can see that the host system had 1 processor.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/7133a3e73d0a4b81c2278e98f44f001ae6534070568603de4d162d9bbef3679f4395d4ef020e2eb083df6f8638ce.png)

---

**Question 3 - memdump1.mem - Image identification 3 - Identify the address value of the KDBG (short for _KDDEBUGGER_DATA64) structure that will be used by plugins, such as pslist and modules**

Looking at the line above the highlighted section in the screenshot from Question 2, we can see the KDBG address value.

---

**Question 4 - Generic Question - Process list 1 - What is the plugin command used within Volatility to list the processes of a system?**

This question is asking us what command-line argument we would use to list processes using Volatility. The answer is the ‘pslist' plugin.

---

**Question 5 - Generic Question - Process list 2 - What is the plugin command used within Volatility to view the process listing in tree form?**

This question is asking us what command-line argument we would use to list processes in a format that shows parent-child process relationships using Volatility. The answer is the ‘pstree’ plugin.

---

**Question 6 - memdump1.mem - Process list 3 - How many processes with the name "svchost.exe" are running in that system?**

To achieve this, we'll use the ‘pslist' plugin to list all processes that were running on the system at the time of the memory capture. As we're only interested in svchost.exe processes, we'll pipe our Volatility output into grep and search for lines containing svchost.exe, printing only these to the terminal. This command looks like this: `**python vol.py -f /home/ubuntu/Desktop/Volatility\ Exercise/memdump1.mem --profile=Win7SP1x64 pslist | grep “svchost.exe”**`

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/9743343f25e626c65646b47832be22573798d6fe9a5dc75c66a5f34fbd37320d2ceb912bd69fdca3c63a843e1672.png)

By counting the number of svchost.exe occurrences, we get the answer. Alternatively, we can pipe the grep output to wordcount using the lines flag (-l) to count the number of occurrences that grep has identified: `**python vol.py -f /home/ubuntu/Desktop/Volatility\ Exercise/memdump1.mem --profile=Win7SP1x64 pslist | grep “svchost.exe” | wc -l**`

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/cc40cbe50ade09c47f427be5e35f43123f4a1638df411a9da61eae23f3d8ac04b2547ad637e801f61f62882752c0.png)

---

**Question 7 - memdump1.mem - Process list 4 - One of the svchost processes is malicious. What is the PID of the strange svchost.exe process?**

To provide us with more context than simply listing processes, we'll use the ‘pstree’ plugin to show parent-child relationships between processes. We can see that the first svchost.exe process creates a cmd.exe child process, where the ping command is used, because we can see the ping.exe process being used. This is definitely unusual activity!

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/545be0170ad5167923528d8ed5c422f7bc8c1b88b6797d262fa225b4408e55dfa392e9ce795496b8426cdef15e03.png)

---

**Question 8 - memdump1.mem - Process list 5 - What is the command line of the process with PID 2352?**

Using the ‘cmdlist' plugin and pointing Volatility at the specific pid using the ‘-p’ flag, we can extract the command-line arguments this process was using. `**python vol.py -f /home/ubuntu/Desktop/Volatility\ Exercise/memdump1.mem --profile=Win7SP1x64 cmdline -p 2352**`

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/725a36255f0a0515bcc1d0aa7c9bcfdfb2b1d41d9d23114b3e2318aa258f630550a40c70e16717b7d1e3c9693a8e.png)

**For the next two questions, we'll be analyzing memdump2.mem instead.**

---

**Question 9 - memdump2.mem - Network connections - This memory dump correspond to a machine we suspect has been persistently infected by some type of malware. We need to identify the harmful IP related to the malware.**

For this question we're going to use the ‘netscan’ plugin and look for the presence of unusual Foreign Addresses (public IPs), especially those that are being connected to from unexpected processes. `**python vol.py -f /home/ubuntu/Desktop/Volatility\ Exercise/memdump2.mem --profile=Win7SP1x64 netscan**`

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/813314e08be09af2910ad3b54a29446722d7e695493fc79f5d001d09784c400062bdc0c2dac3cf16a91ac3084f54.png)

Looking at the bottom line of the output we can see that the process WINWORD.EXE (Microsoft Word) was communicating to the Foreign IP 65[.]111[.]166[.]58 on port 80 (HTTP). Based on knowledge of phishing attacks, this is very likely to be a malicious Word document macro that is downloading malicious software from the mentioned IP address over HTTP.

---

**Question 10 - memdump2.mem - Process dump - Dump the process with PID 2940 and calculate the MD5 hash. Submit the first 5 characters**

Using the ‘procdump’ plugin and providing the PID using -p, we can extract the file. We'll then use ‘md5sum’ to get the MD5 hash value. `**python vol.py -f /home/ubuntu/Desktop/Volatility\ Exercise/memdump2.mem --profile=Win7SP1x64 procdump -p 2940**`

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/eb4e8460c4b7155959d296b2bd195f71c82a726a3dfa1121e47f745a83fa474c76d90d752394511d807393480941.png)

#### Great! You've made it to the end 💪

Domains List

Prev

 / 66
 # Lab) Volatility 3 Workbench Solution

1. Digital Forensics
2. Memory Analysis With Volatility
3. Lab) Volatility 3 Workbench Solution

Complete

We'll start by opening the VolatilityWorkbench folder on the Desktop and double-clicking the VolatilityWorkbench application. 

When we click the Browse Image button at the top to import our memorydump, we'll navigate to Desktop > Malware3, but for the image to show up, we need to change the file types in the bottom right to “Any File”.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/8feba1e4d81da8587edf8e8cc1afca41efd8b86b3215af389b22df4dd9818db9c7adcd89bbfde53e1466c1dc1623.png)

Click on malware3.elf, then click Open in the bottom right.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/efe36745257910326794bd87f7ceb60b685243e1327ef20265b3c8f13f69aaf5b89f688bf13d6489b104d5522f64.png)

Before we can start, we need to click the “Refresh Process List” button in Workbench.

**Question 1) When refreshing the process list - what plugin is volatility actually using? (Format: Command.command)**

In the main window of Workbench we can see that after clicking the Refresh Process List button, Workbench is just running the windows.pslist command:

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/2448bb384aaa533963c59608781dbb00b3919a1c6a199851389be1c11f72c75eccc637eb11bf8c7193dd11cee65f.png)

**Question 2) Select the windows.info.info plugin from the drop down list. What version of the Windows Operating system is being used on the system the memorydump is taken from? (Format: Windows Version)**

 Selecting the command provided in the question within the output we can see the following lines of interest:

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/9cea979f55b974eb4b4688941e48b882b38dc6f0fa967494af926de3f7cd03869e0405750103bd0a5424222368e1.png)

Combining the SystemRoot and MajorOperatingSystemVersion, we can identify that the machine the memory image was taken from is running Windows 10.

**Question 3) Run the windows.pstree.PsTree command and use the process ID drop down menu to help filter out the noise. What is the parent process of Powershell.exe? (Format: PID, ProcessName)**

We'll select the windows.pstree command and click the Process ID checkbox which gives us a dropdown to select the process we want to focus on. Based on the question, we'll find and click on PowerShell.exe that has a PID of 4708. Now we can run the command.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/c264779edeeb60a31154f54dc6774e0ba12ed28602af2fa943117c19031dd5ef60c605a16b76afa918dfa9e9d9d9.png)

In the above output we can see that the parent process of PowerShell.exe is CompatTelRunne which has a process ID of 5264.

**Question 4) Use the windows.privileges command. The process 2416 has the ability to 'Add Workstations to the Domain. What is the attribute associated with this privilege? (Format: AttributeName)**

The question specifically mentions process 2416, so we'll click the Process ID checkbox and select this process from the dropdown menu, which is listed as HxTsr.exe (2416).

Looking through the output we can find a reference to “Add workstations to the domain” which has a Privilege Attribute value of “SeMachineAccountPrivilege”.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/fa16aafc13b6dd69a402fabacb77156c9d417be9756b56c9972cd2f3c77ac37cc8b98e03f00a4023389ddc49b7c0.png)

**Question 5) Pick a plugin to analyse the command-line arguments executed by process 2416. What is the server name the executable is parsing in its command? (Format: ServerName)**

Looking through the command dropdown menu for a relevant plugin, we find windows.cmdline.CmdLine, which seems like it'll do what we need. We'll click the Process ID checkbox and select HxTsr.exe (2416) and run it.

In the output we can see the ServerName value is HX.IPC.Server:

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/3dc04604640d8331dfadfd1b0ced1fa25e5780990753f16452e2061920c56e9ffd326092767b1adf5c9238f7337d.png)

#### Great! You've made it to the end 💪

Domains List

Prev

 / 66

Next

# Lab) Hard Drive Investigation Solution

1. Digital Forensics
2. Disk Analysis With Autopsy
3. Lab) Hard Drive Investigation Solution

Complete

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/c1ff2d282d803e4fca88280eeb0ce5901eb160526800a58653a7433edf87484afe1bba3db286f0d7a3e1ab559c23.PNG)

After opening Autopsy, found within the ‘Autopsy For Disk Analsis’ folder on the Desktop, we'll be asked if we want to open a case, or create a new one - click on Create New Case. You'll be asked to provide some information, you can name the case anything you want.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/13f9edd4c729e15c595cd2199e6b0703a01ea836299bca63ea0a331650403e02f938a0fa6a2451565acf51858b21.PNG)

We need to select a Base Directory for our investigation, which needs to be an empty folder. Click on Browse, go to the Desktop, then click the icon in the top-right to create a new folder.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/5d34bf297cfe83965d5c7a803acd1395d0646ab8227c9d40ee611cc9760be7c11302f9d2c54a4e8f82df4c7416c1.PNG)

After clicking Next we'll have our case created within Autopsy. We need to click ‘Add Data Source’ in the top-left corner. When asked to select a host, leave it as the default option (first option) and click Next. We are now asked to import an image, leave it as the first option and browser to the Autopsy For Disk Analysis folder, then Laptop Image, and select the below file.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/39492c9e84c80f0c0fe6176f75eb3e7d357244565e64db93668175ff7206677fb2027603b2b9b3d097236523e788.PNG)

For Step 4 we're asked what Ingest Modules we want to run on the disk image, to help us quickly retrieve interesting information. Click Deselect All, and tick the two modules shown below.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/fb2583fa8fe48aa217531565c9dae4f3ef077d811e0a8e573f5f72ea0a1b96387e1cd24152b913c9f6da00a6d9f6.PNG)

Autopsy will now begin importing and processing the disk image and ingest modules. Leave this to run for about 10 minutes, then you'll be ready to start answering the questions!

---

**Question 1 - What operating system (and version of OS) is the suspect laptop running?**

To find the Operating System of the device we can look under ‘Data Artifacts > Operating System Information’. Scrolling to the right within the table in the left panel, we can see the OS listed as ‘Program Name’.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/1be2a1be291a99f3c17fcd219bb8ea939f28492bfa453aae6dbcdb9ff706c20aded629a6fe86f2e3d2f364d3133b.PNG)

---

**Question 2 - What is the hostname of the system?**

On the same section as above, towards the left of the table, we can see the Hostname listed as ‘Name’.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/86b49231cdca4045fb384a813423cfd8824b554d1a13992ec9ef4a292b44ac387bffafd8db54fe04a85f89e3f8ef.PNG)

---

**Question 3 - Look at Web Downloads that have been retrieved from the disk image. What file was downloaded at 2013-12-18 20:05:57 GMT?**

Still looking at the ‘Data Artifacts’ heading on the left panel, we have been asked to investigate Web Downloads. In the table on the right we can see ‘Date Accessed’, so we need to find the row that has the date from the timestamp in the question!

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/98e263d93f3005b866b084c2d0ad0188c13ddb9bc854fdea5a3d6a321720039930ac5f82eb4a8489e13524c2b40f.PNG)

---

**Question 4 - What is the full URL of the file that was downloaded at 2013-12-18 03:02:50 GMT?**

Looking in the same location, we need to find the row in the table that matches the timestamp in the question. After finding it, we can see the full URL in the column titled ‘URL’.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/fbed000932dc3e33e95733c1e60cad9bfa0c81a1e299283bc0cbadbd3f45ce6cd6b3d28003751ee56e47746e5257.PNG)

---

**Question 5 - Looking at Recent Documents, what is the full path for the file Pier.jpg?**

Remember LNK files, that we covered earlier in this domain? Files that are used as shortcuts to the real file located on disk. We can use LNK to identify when files have been accessed, and where they are stored. The sample applies here! Looking at the ‘Recent Documents’ menu item, we can find the Pier.lnk file, which is used to represent Pier.jpg - we can get the file path from the ‘Path’ column.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/cf87f0f201455b719ab993a4ce4e35372f076228bd4e338591ef614607688e65ca8902f24608bcd1f26ce575def7.PNG)

---

**Question 6 - Double click on vol2 to enter the virtual filesystem. Navigate to Program Files > GIMP 2. What is the file size of the directory named "lib"?**

Let's view the virtual file system, as if we were on the computer itself! Double-click on vol2, the largest partition within the filesystem.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/e35f317e223a0c36ca9a7dc152987cf8843c0724b58442b5ccf542f0dac10faeba99d2625e349cc671ff9bd86e5b.PNG)

Moving to Program Files, GIMP 2, we can see the folder we're interested in. The file size is shown as a column at the end of the highlighted section!

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/83c0a4401f11a2cd594e7ec40d723250bbf3a598cccc90449430ce33d655fb78a99605e57df29b18c2f8a380aa74.PNG)

---

**Question 7 - Go to the OS Accounts tab. When was the local administrator account last accessed? (Format: YYYY-MM-DD HH:MM:SS)**

Looking under the ‘OS Accounts’ section, we can see every local user that is on this computer. At the bottom we can see the Administrator account, giving us the time it was last accessed.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/7c416bfdae41f2a64e72ec29580c5c90997afc79988bc143825a91e0556d2e30a0c9a85c5ebbd5187af93dd7d628.PNG)

#### Great! You've made it to the end 💪

Domains List

Prev

# Lab) Event Log Analysis Solution

1. Security Information and Event Monitoring
2. Logging and Aggregation
3. Lab) Event Log Analysis Solution

Complete

On the Desktop we can find a folder called ‘Event Log Analysis’ which contains a single file, ‘Security Investigation.evtx’.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/2c21e93795df4ac86ad0b992ff34bb8b0c89d5ae74a425dbbdfdfb6582e7b831a46d89e330cb1d695f10863d9aea.png)

After double-clicking this file, give Event Viewer a few minutes to load and show you the event logs.

---

**Question 1 - At what time is the first Special Logon event?**

One approach to this question is to filter the logs based on the date and time they occurred. By default Event Viewer will show the most recent events at the top, so if we left-click on the Date and Time column once, it'll show the oldest logs first. From here we can see that the first log recorded is a 4672 Special Login. We can take the date from the log, and make sure it fits the expected format.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/1b9aa3ce831327c778093eb51df3d41a2d88883b8e2940199cd8d86f3db44707595989aa7f346fbd67e76c1dceeb.png)

Alternatively, when looking at a much bigger export of event logs (as this capture only has 11 logs), we can use a filter to only look at specific event IDs, which in this case would be 4672. This can be achieved by clicking on ‘Filter Current Log…’ on the right-hand panel of Event Viewer. We have added 4672 to the input box half-way down the popup, and after clicking ‘OK’ we'll see our results.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/869946d746fc864a33dd76c7cdb7d78797ffb72709e82892e0b4d3328bfb01df9889ceabb1217e389639bc1600b4.png)

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/f190a847ee8084deb853c23f5f46356d94cd1786b434a6ab1d871ac17a8b22b9f70269b7f522241a9d50e1ee32d7.png)

---

**Question 2 - At what time does Jeff create another user account?**

Following the time-ordered chain of events, we can see a ‘User Account Management’ event (4720). Within the log details we can see the person that took the action (Jeff, the Subject), and the new account created, SteveE. We can take the date from the log, and make sure it fits the expected format.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/0019ef65603ddc2dd23ee0a34549685fe9d6abc805ccfc72a71f38e093124466a2a9770460c1415c0af3691391e4.png)

Alternatively, we could create a new filter to look for 4720 event IDs.

---

**Question 3 - What is the name of the new account?**

We have already recovered the new user's name in the previous question!

---

**Question 4 - What is the Windows event ID for the creation of the new user account?**

Based on the previous two questions, event ID 4720 is used for new user creation.

---

**Question 5 - What are the names of the three user groups that the new account is in, listed alphabetically?** 

When users are added to Windows Security Groups, 4732 event IDs are generated (Security Group Management). Looking through the log details we can see the group that the target account was added to. In the first event the account is added to the default group ‘Users’.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/a82f7614208ab66bf55c00ac7b716e4be46993a19e589d7fcf7997618ec2e90099c7d24ac625b52cf80607af667f.png)

In the second event the account is added to the ServiceAccount group.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/a40a03e975f937d019be485d252800d4ece7e360b61a97bdd89eb37b263e885757c71dca28a0bf2a2063a7e7c5bb.png)

And in the third event the account is added to the Administrators group.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/4a44256a0616224de807e43fc75ea29ecccbca6cb01abb4703122f5324ad2d99bfe6dbe57710a983f5ff130b30b6.png)

---

**Question 6 - At what time does the new user account log in?**

To find the answer for this question we can create a new filter for 4624 (normal logo) and 4672 (special logon) event IDs. Looking through these events we can find a special logon that involves the new account, SteveE. Remember, this is a special logon, not a standard logon, because this account is in the Administrators localgroup.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/05624d909432098bedec743601f6f9bd0d51e9ef9d19658300922df7c816dd115106aea38786255f93e66f238dbb.png)

# Lab) Splunk Investigation 2 Solution

1. Security Information and Event Monitoring
2. Using Splunk SIEM
3. Lab) Splunk Investigation 2 Solution

Complete

In the lab scenario on the Instructions page we're told to scope this investigation to fortigate_utm logs only. We are also told to search for two strings, our website name "imreallynotbatman.com", and “vulnerability” to help identify if our site is being scanned by an attacker.

To get Splunk ready, we'll open a Terminal using the icon on the bottom toolbar and enter in the following command: `**sudo systemctl start Splunkd**`. After a minute we'll open Firefox and visit `**127.0.0.1:8000**`. Next we'll click on the ‘Search & Reporting’ app on the left-hand side of the Splunk homepage.

We need to make sure we can see all of the logs as they were generated back in 2020. To do this we'll click on the timeframe selector on the far right and select OTHER > All time on the right.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/6bc46e36ea3fa18a10dec6ca24f08fa8f399c8e162d4d6070f40ff7c5988078c8d4fb2f380fdef711b3659470f4e.PNG)

Whenever we conduct a search we want to start the query with `**index="botsv1"**` to ensure we are loading the right data.

We're ready to get started with the lab questions!

---

**Question 1 - What is the name of the web vulnerability scanner that is being used?**

There is a wide range of ways we can approach this investigation, as we are not provided with the pre-written search queries in this lab. Let's assume we're not familiar with Splunk, so we can't just write a perfect search to find this information instantly. Let's go step-by-step and build up our query!

First, we want to find events with the sourcetype fortiguate_utm, so we'll turn Event Sampling to 1:100 (as we don't want to search through every single log just to retrieve the sourcetype) and run a search for `**index="botsv1"**`.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/340d87b072f17044988fd32aec362cc2b7157dd5c36d7e18b6fb2404b00b82251cf3bf853c7fc74735266b3e9a93.PNG)

On the left-hand panel, we'll see ‘sourcetype’ under the ‘SELECTED FIELDS’ heading. After clicking on sourcetype we can see fortigate_utm is listed. Clicking on this will add that filter to our search query.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/c7905ee5c4dad4a409c0f7e43ba80536e0f7520798a49ca10f994d4a3c82412079219d712f350a52eefc7ae4f9dc.PNG) 

Our search query is now `**index="botsv1" sourcetype=fortigate_utm**`. Let's turn Event Sampling off (No Event Sampling) and wait for the search to finish.

Next we're looking for a field that will hold the domain we're looking for, imreallynotbatman.com. Scrolling down the Interesting Fields we find ‘url_domain’, and clicking on it shows the domain we're interested in. We can click the value to add it to our search.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/321697d54e5b42e5cf6a4f94c00d9d7845f41a131ee4cd1156a3580c068f3bc8db1cb9fd6e0335874cf6062ded1b.PNG)

`**Our search query is now index="botsv1" sourcetype=fortigate_utm url_domain="imreallynotbatman.com"**`. The final part the scenario told us about is including the string ‘vulnerability’. We can add this by simply writing vulnerability at the end of our search query, giving us a final query of `**index="botsv1" sourcetype=fortigate_utm url_domain="imreallynotbatman.com" vulnerability**`.

Going back to the question now that our query is built, looking at the Event Details panel we can see that the text ‘vulnerability’ is highlighted, showing us that two fields in these logs, ‘attack’ and ‘msg’ inform us that the traffic is being generated by the Acunetix Web Vulnerability Scanner.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/610c55257227c79c3274bf374d7cf3c245b1d78a481218de858b3761ea70ec21c918bb698b5841ebec98acee8047.PNG)

---

**Question 2 - What is the source IP of the vulnerability scanner, and therefore the attacker?**

Looking at the events our search has found, we can see that the field ‘srcip’ is being used by this log to hold the source IP address value.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/30d547554bf5d25916153b39057012d50dd4524af49ecf9e3b8f441ecee72f5c67074661b3ba9c438922a987b1d7.PNG)

---

**Question 3 - What is the destination IP? (the internal address for our web server)**

Looking at the events our search has found, we can see that the field ‘dstip’ is being used by the log to hold the destination IP address value.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/8efac2c45391bfaf7ce5a7aef57487c7c4c6726450099065a30bc8d740f101a875559f64d42a4e884dfa66901e0a.PNG)

---

**Question 4 - Fortigate UTM provides enrichment, and can tell us the source IP country based on a lookup. What country is the scanning IP associated with?**

Looking at the events our search has found, we can see that the field ‘srccountry’ is being used by this log to hold the source IP address country value.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/30d547554bf5d25916153b39057012d50dd4524af49ecf9e3b8f441ecee72f5c67074661b3ba9c438922a987b1d7.PNG)

---

**Question 5 - What is the timestamp in the first Fortigate UTM log referencing the vulnerability scan, on 8/10/16, in the format HH:MM:SS? (Use the log timestamp, not the Time column next to the event)**

Keeping the same search query, we want to sort these events based on the ‘time’ field within the logs. To do this, we'll use the ‘sort’ functionality in our query. All we need to do is add `**| sort _time asc**` to the end of our search, which will sort all the events in time ascending order, putting the first events at the top.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/c66bc96c48234a69401c44081a785ad1f40e90aeca048bae157af921e6644501a466b4cd7f70427e203be83252ea.PNG)

#### Great! You've made it to the end 💪

Domains List

Prev
# Lab) Splunk Investigation 3 Solution

1. Security Information and Event Monitoring
2. Using Splunk SIEM
3. Lab) Splunk Investigation 3 Solution

Complete

To get Splunk ready, we'll open a Terminal using the icon on the bottom toolbar and enter in the following command: `**sudo systemctl start Splunkd**`. After a minute we'll open Firefox and visit `**127.0.0.1:8000**`. Next we'll click on the ‘Search & Reporting’ app on the left-hand side of the Splunk homepage.

We need to make sure we can see all of the logs as they were generated back in 2020. To do this we'll click on the timeframe selector on the far right and select OTHER > All time on the right.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/6bc46e36ea3fa18a10dec6ca24f08fa8f399c8e162d4d6070f40ff7c5988078c8d4fb2f380fdef711b3659470f4e.PNG)

Whenever we conduct a search we want to start the query with `**index="botsv1"**` to ensure we are loading the right data.

We're ready to get started with the lab questions!

---

**Question 1 - OSINT can be extremely useful in almost every investigation. Perform a Google search for osk.exe - what is the full name of the Windows feature associated with osk.exe?**

Searching for “what is osk.exe” on Google tells us that this is the file used to run the On-Screen Keyboard feature from Windows.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/c3a1dafc02451164b8584c22f06dca45115a0957ed7b9b758aeb889ac1e8612008c606475672df433ba8a890c1cd.PNG)

---

**Question 2 - Continue with your OSINT research. What is the expected file path for osk.exe? (Path to the folder, or full file paths are accepted)**

The screenshot from Q1 also tells us where the legitimate file is stored; in `**C:\Windows\System32\osk.exe**`.

---

**Question 3 - Filter on Sysmon events (sourcetype=xmlwineventlog) and search for the suspicious executable name. How many events are returned based on this query?**

Based on the sourcetype provided in the question, we know our full query will look like this: `**index="botsv1" sourcetype=xmlwineventlog osk.exe**`. When the search completes, we can see there are 49,608 events found.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/224fae72cb580bc8c36376602a253dc63cb3c121c8905163d75cb852b059ba21425953ae4801ea12d8d9d329b011.PNG)

---

**Question 4 - What is the full file path of the suspicious executable?**

Looking at these logs, we can see under the ‘Image’ field that osk.exe is NOT being stored in the C:\Windows\system32\ folder where it should be. What does this mean? This is not the real On-Screen Keyboard binary, but is trying to hide by looking legitimate!

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/c46993ad7ae3fb9560ffbaae6be35dc115de99323de0ab4c62c3917c6751463b7207355f210d96eda22a9e1bb7fe.PNG)

---

**Question 5 - What computer is the suspicious file running on, what is the internal IP address, and which user account is running it?**

Now that we've found something suspicious, let's gather information about the system this file is running on. In these logs we can find three useful pieces of information; the system name, the IP, and the user account:

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/3efe7a62ca870de13372ccb70369c77f68e8d95a76f7afa562a9c4e8cd1e4532e685052d45b5702964c0932fb475.PNG)

---

**Question 6 - To scope our next searches only on this executable, find an appropriate field + value pair to add to your search query. Next it's a good idea to see if there are any network connections - what destination ports is this file connecting to?**

Currently, as we're just using “osk.exe” in our search query, it will find events that have this string in any field of an event. To narrow this down within the Sysmon logs, we can include the Image field with the full file path value in our search query. We'll click on Image in the Interesting Fields panel and click on the path to the suspicious osk.exe.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/2f2f5f5ee480e1ee033295460583f073ee9c7c13754e3843fd3e3fed56a911c151381b25ec9106b240a22d709832.PNG)

Now that we've updated our search query, we see that the number of matched events has gone down from 49,608 to 49,594 - only 14 less, but this search is still neater!

Looking back to the Interesting Fields, we can see DestinationPort exists, with 2 values. Clicking on it will show us the destination ports observed.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/bbf661b083edee781d2f57d970dd6e926caccb9ddc7e19265669d577ed4f457846de7dabac6cd3a799e756561393.PNG)

---

**Question 7 - Adding the destination port with the highest activity to your query, use 'count' functionality to identify the number of unique destination IP addresses this file is connecting to**

First let's add the destination port 6892 to our search, because this is extremely suspicious. Why does an On-Screen Keyboard feature from Windows need to connect to ANYTHING over the network? And even if it did, why is it connecting to high-numbered port 6892, which is non-standard. This is more evidence helping us to confirm that this file is likely malicious. We'll click on the ‘6892’ port in the DestinationPort popup from Q6.

Our search query is now:`**index="botsv1" sourcetype=xmlwineventlog osk.exe Image="C:\\Users\\bob.smith.WAYNECORPINC\\AppData\\Roaming\\{35ACA89F-933F-6A5D-2776-A3589FB99832}\\osk.exe" DestinationPort=6892**`. If you want to get into the habit of keeping your searches neat, you can remove the ‘osk.exe’ after the sourcetype, as it's no longer needed because we are referencing that file using the Image field.

Looking at the Interesting Fields panel we can see that DestinationIP has 100+ results. As the number of unique values in this field is above 100, we can't easily get the count from just looking at it - we'll need to run our own search.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/da0f969d03010cf5a87bfc5b191b731a9f8692a63f1343a9a603b50efbf1eef48298eebd3457a0a51d0126f1f30b.PNG)

To look through all of the 'DestinationIp' values and only retrieve unique values, we can add the following to the end of our search query: `**| stats count by DestinationIp**`. We can now see that this file has connected outbound to 16,384 IP addresses… wow.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/b743f9a65332cb99fad5fe58147266b9aefee300b0e5dabe98b755115a5fbb54b1fa6a265d2d38f4e22b405627c1.PNG)

---

**Question 8 - Sysmon EventID 7 logs contain the hash values of files (ImageLoaded field) that are executed. Use this to find the SHA256 hash of the suspicious osk.exe and submit it**

Let's start with a new search query, as we're focusing on a specific type of Sysmon log. Based on the information present in the question, and the fact we're still looking at osk.exe, we'll run the following search to see if it works as intended: `**index="botsv1" sourcetype=xmlwineventlog EventID=7 ImageLoaded=*osk.exe**`.

For this specific question, we only need one relevant log to get the answer, so as soon as events are found we can stop the search using the square button underneath the search bar on the right-hand side.

In the below screenshot, in the highlighted section you can see that the ‘ImageLoaded’ field is using the full file path value for osk.exe. After this field we have the ‘Hashes’ field that holds multiple values, but the one we're interested in is the SHA256 hash string.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/831358b4b23159852499b65d9e8dd5d0b29806282ae8d15e583b0223ee1b518dd47c3b05fca3f263228ce03c8026.PNG)

---

**Question 9 - Outside of the lab, submit the SHA256 hash to VirusTotal. Based on the results on the Detection page, what is the potential name of this malware?**

Copying the SHA256 out of the log in Splunk, then copying it from the Clipboard tab of the lab client, we can easily paste it into VirusTotal. Looking at the results, we can see a lot of mentions of ‘Cerber’. This appears to be the only ‘name’ referenced on this page, as almost everything else is using generic or descriptive names.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/c173b827b967d944b01e79078b46c3e5ec88fa41013ecfa2107485c1f7d1ae722632eee4b6e510f40d936eb8a758.PNG)

---

**Question 10 - Sysmon was useful, but let's investigate the network traffic coming from the suspicious file out to thousands of IP addresses. To do this we'll look at the Fortigate Unified Threat Management logs. Find something all (but one) of the osk.exe sysmon logs have in common regarding network traffic and use this in your search query. What is the category of malware dedicated by Fortigate?**

From our previous searches, in Q6 we found that two destination ports were contacted, with 1 single request going to port 80, and all of the rest went to 6892. We'll use this as the indicator for this traffic, because 6892 is not a standard destination port, so we are very unlikely to get other non-related events included in our search (if we wanted to be extra safe, we could even include the source IP of the system making these connections, just in case another system was also making requests to destination port 6892). Our search query will be: `**index="botsv1" sourcetype=fortigate_utm dest_port=6892**`.

Looking at the results, we can clearly see lots of useful fields from Fortigate that tell us about this threat. According to the ‘appcat’ (threat category), ‘app’ (threat), and ‘msg’ (message) fields, the values tell us that Fortigate has flagged this for Cerber botnet activity. Therefore the category of malware reported here is a botnet.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/2bb305aa8f73fa4774c5d4d29816b63df7e33a3922cda96a8b13d244b4614f976dfd8065c7cee07d1d1df4050800.PNG)

---

**Question 11 - What is the name given to this specific malware by Fortigate?**

As mentioned above, the category for this malware is botnet, and the name given is Cerber, something we also saw on VirusTotal earlier.

---

**Question 12 - Conduct another OSINT search for the name of the malware. What is the primary function of this malware? (Submit the malware category, different from Q10)**

A simple Google search for ‘Cerber Malware’ shows us results from high-profile security companies, clearly stating that Cerber is a type of ransomware. The reason that Fortigate is flagging it as a botnet is that it also includes that functionality, and if you read some of these posts, you can learn about it in more detail!

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/eb9d98385b5f76aef67b244ee34d944784c77bbeb1442f3f7d6a2f1e53f206b2e26d401d302ac0f354d9cc540732.PNG)

---

**Question 13 - Finally, let's investigate the single connection from osk.exe to a remote IP address on destination port 80 HTTP. Find the IP from the Sysmon logs and use it to search in the suricata logs - these logs have different event types, and we're interested in 'alert'. If Suricata has alerted on this activity, what is the signature value?**

Based on the fact we're tasked with looking at suricata logs, we know that our search query is going to start with index="botsv1" sourcetype=suricata. Because these are just network intrusion detection/prevention system (NID/PS) logs, we most likely wont see any reference to the file generating this traffic, osk.exe, so we need something else to search on so we can find the relevant events.

We can use destination port 80, but this search is going to bring back a huge amount of events, because we aren't being specific enough. We could include the source IP of the system running osk.exe, but this search is also too wide, because we would get results related to any HTTP traffic over port 80.

To be as specific as possible, let's run one of our old searches again so we can find out the destination IP of the single event of osk.exe reaching out to port 80. We'll use the query `**index="botsv1" sourcetype=xmlwineventlog osk.exe**`. We will click on the DestinationPort field under the Interesting Fields header on the left and this time click on “80”.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/309d5ab1d24653fd6c3ddd4ae9d7fc9da334b5647cf7b37e0f30ac41318eeccf0a0149ef4ac82f8728f604cd337a.PNG)

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/8418a20b2061bb998b50b9bd5bd46e29f89a0cc7cec81078c7ca18a21b2b6e54d748eea75fcf7137723decb62667.PNG)

Looking at the single event, we can retrieve the source IP and Destination IP values from the log. We'll use these to narrow our final search to make sure we're looking at the right Suricata logs. We need to remember that while Sysmon logs use 'SourceIp' and' DestinationIp' field names, we cant be 100% sure that Suricata will use those same names, so to work out what those fields are called let's jump in with a wide search using `**index="botsv1" sourcetype=suricata**`.

After a few events show up we can cancel the search. Looking at the Event Details panel we can easily see the format used by Suricata for its logs:

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/0eadf6a20a9f51fc958c4c6842daa8d04c82764ec83d3d9e38467723b703202428d39464e5fd41eb2652013a376d.PNG)

Now that we understand the formatting, we can build our full search query to identify the suspicious port 80 HTTP traffic from osk.exe using Suricata logs: `**index="botsv1" sourcetype=suricata src_ip=192.168.250.100 dest_ip=54.148.194.58 dest_port=80**`. After a few seconds we can see that 4 logs match our search query! This question also tells us that we're interested in the event_type ‘alert’ - as there's a very small volume of logs, we can look through them to find the right one(s), however if there was a large number of events, we could add it to our search query using `**event_type=alert**`.

After finding the right event we can click on the “>” arrow in the top-left of the row to see all fields and values (some information may be hidden when looking at the Event Details panel, because this sometimes is used as a preview instead of the full raw log).

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/d6240ebc77588d773470a26edf49652fb0fd8c8e8ab90c8da8455f66f98510bd67082f3be99c1bd793b113b4c6d6.PNG)

Finally, in a field that is not configured to show on the Event Details panel, we can see the alert.signature value for this log is related to an external IP lookup, an action that is conducted by attackers or malware to identify the public IP of the machine or network, helping them to understand what company they have compromised (based on indicators such as the IP range owner, ASN owner, WHOis contact details, and more).

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/bdab04a9aa2b53ad41821e730ebf7f25c5fe9226ea33a217be18d848a8ee00c6d05aa8d75c07260acc371d148572.PNG)

#### Great! You've made it to the end 💪

Domains List

Prev

 # Lab) Splunk Investigation 4 Solution

1. Security Information and Event Monitoring
2. Using Splunk SIEM
3. Lab) Splunk Investigation 4 Solution

Complete

To get Splunk ready, we'll open a Terminal using the icon on the bottom toolbar and enter in the following command: `**sudo systemctl start Splunkd**`. After a minute we'll open Firefox and visit `**127.0.0.1:8000**`. Next we'll click on the ‘Search & Reporting’ app on the left-hand side of the Splunk homepage.

We need to make sure we can see all of the logs as they were generated back in 2020. To do this we'll click on the timeframe selector on the far right and select OTHER > All time on the right.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/6bc46e36ea3fa18a10dec6ca24f08fa8f399c8e162d4d6070f40ff7c5988078c8d4fb2f380fdef711b3659470f4e.PNG)

Whenever we conduct a search we want to start the query with `**index="botsv1"**` to ensure we are loading the right data.

We're ready to get started with the lab questions!

---

**Question 1 - Click on Dashboards and go to Splunk Investigation 4. How many Suricata alerts are there, and how many Fortigate alerts are there?**

First we'll click on Search & Reporting App, then Dashboards at the top of the page. At the top of the Splunk Investigation 4 dashboard we can see two panels being used as counters for both Fortigate alerts and Suricata alerts.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/2ec53a9a950276931a86f95a982f69b0bbd0317f9d41353b46c0587b66bc71adaec4f5c7859795f1ada5b157bcb7.PNG)

---

**Question 2 - Edit the dashboard and look at the search query for the Fortigate Alerts counter. What is the full query used to generate this number?**

To see the search queries that are powering dashboard panels we first need to Edit the dashboard in the top right corner. Then we can click on the magnifying glass icon of a panel, which is the ‘Edit Search’ option.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/4aee17e9e1a4c75d2a7f7b100f318cd2d31db719e7a76604b7137a55e93c7689276987c4370156bcfe3fa77482d0.PNG)

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/f82788d61c2bedf2c7372cb91dd3eff6d57d22e61f17b575921b0aae45532caefa3ce33e37af677d41c509cfab1a.PNG)

---

**Question 3 - What is the full query used to generate the Suricata Alerts counter?**

We'll take the same actions as we did for Q2, and click the magnifying glass icon on the Suricata Alerts counter panel to see the search query behind it.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/4c70cabe928e34ce8d1f85b1676c8e2aff4ad69b64eff718a0326dc661bf98bfbff68226434711982fd887323a20.PNG)

---

**Question 4 - Click on the Suricata alert titled 'Information Leak' to see the associated events. What is the source IP address, and what is the destination IP address?**

We can find this alert category on Line 6 of the Suricata Alerts (Categories) table.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/968dcc2c2c56f2b2dd84919cad0992114e2f11106f48731fd04efd76cf775891815592386c6b2846c3b7b35eeaf2.PNG)

Looking at the 2 events, we can see the dest_ip and src_ip are shown immediately, giving us our answer. The external IP 40.80.148.42 is connecting to our internal system which is hosted internally on 192.168.250.70 on port 80 (HTTP).

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/0fb64d8e7617254887ef535b8a84618d0dcb0a5fa7505a7d04563755f36adf3b23e430b77a0138ce0b0c63d1cfdd.PNG)

---

**Question 5 - What action did Suricata take after observing these events?**

Just looking at the events in the screenshot above, we cannot see any fields that would tell me what actions Suricata took, so we'll click on 'Show as raw text' at the bottom of each event to change the displayed format. We can now see a field called ‘action’!

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/16b94746706d6d209b2b0514d67d861891be0021a3517e9e19161f45ddb15401a783239d0c1ded286866026ea66a.PNG)

In this case, both events were allowed by Suricata. If this tool is deployed in Network Intrusion Prevention System mode (NIPS) as opposed to Network Intrusion Detection System (NIDS) then it could take actions to stop malicious connections, such as applying the ‘block’ action to end the connection!

---

**Question 6 - We know the alert category is 'Information Leak', however the specific signature can provide us with more information about this activity. What is the signature shared by both events?**

In the below screenshot, we have showed two different ways to view this field within the Suricata logs. This signature is a lot less generic than the category, and can provide context to what is actually happening.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/fe089f3c42376b7429de71778b6e875bd4ea9a0086efbfefa4b91d47f1f05504ba701f55113bf59c31e41b4dbd37.PNG)

---

**Question 7 - Based on the logs, combine two fields to understand the full website addresses being accessed by the attacker (Remember, in some logs a "/" character must be escaped by putting a "\" in front of it. You should not reference the "\")**

Looking at the logs we can see two fields that will help us answer this question: hostname and URL. Using these we can see the two targeted full URLs were:

- imreallynotbatman.com/phpinfo.php5
- imreallynotbatman.com/phpinfo.php

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/f16e045bd197b8054901509d24cf619d8ddacd0aad466fc547efe9a5b1a64951b8ae971956417c4fe86748960efb.PNG)

---

**Question 8 - What HTTP status code is returned to both of these requests, that tells us this attack was not successful?**

Looking at the logs we can see a field named ‘status’, where the value is 404 for both event. This tells us that the attacker tried to reach these URLs, but there is nothing there (Error 404, Not Found).

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/56390c14164aa9897275572d78be97d4bc7c536e97230c319b41d6a7b474f417ab604868503b74b5774feddc058a.PNG)

---

**Question 9 - Return to the Dashboard and click on the Suricata alert titled 'A Network Trojan was detected' to load this search. Modify the search query to show count of every signature field within this alert category. How many unique suricata signatures are present?**

Looking at the Suricata Security Alerts (Categories) table we can see the category we want on line 3.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/84a06dd1a9b7e33db435039e5f0a2162f6e96cc91c77a6ce2ce1812cef2f63508306893b48445a891d212d03b541.PNG)

We're being asked to identify how many signatures are found within this category of alerts. To do this we'll add the following to our search query to get the count of signature values: `**| stats count by signature**`. Looking at the Statistics title, we can see there are 12 unique signatures that have been observed within logs for this category.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/eae2e68841e948e14568d4a305438731598a77bfecb7889bdd445dd5ecccea9ee1cce3ce11d650cf671c67a87648.PNG)

---

**Question 10 - Search manually through Suricata logs where the HTTP status code is 200, then perform a count of each signature field to find two signatures that reference a vulnerability CVE identifier. Search this CVE on the National Vulnerability Database.- what is the CVSS Version 3 Score?**

Okay - there's a lot to do in this question, so let's go step by step. Firstly we'll build our brand new search query for Suricata logs, specifically alert logs, where the status code is 200. The query will look like this: index="botsv1" sourcetype=suricata event_type=alert status=200.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/ddfca9935016e5b6f46e897f16e0bba01e27bbd140fec5f34e86428131f5c99e3c8740c5d63ab8f01f428be3f962.PNG)

Great, next we need to get the count of values in the signature field. We'll add the following to our search: `**| stats count by signature**`.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/000bc37a079dc6690b7a2b2673aae1bd1ceb03348681e02e6c11901944aa2919b22e52c85317e5e867130bb51167.PNG)

Great, we've found the reference to a Common Vulnerability and Exposures identifier, used as an identification method for vulnerabilities. Next we're asked to find the score of this vulnerability, so we'll search for it on Google using the search “CVE-2014-6271 national vulnerability database”.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/847fea0ae2f511c8723bf5554894970666e7266a807c46049136029e6e4fc6c3382d2012972f4e977e4a0433bc94.PNG)

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/f7c28098c5da161780d7e8efa0089be643d4d903f658c5499f47f41350f3cc0ba0567c0c7058479f670e39d3cf24.PNG)

---

**Question 11 - On the Fortigate Security Alerts dashboard table click on 'MS.Windows.CMD.Reverse.Shell'. Identify the internal IP within this event, and use your SIEM skills to identify the name of this system.**

We can find the associated Fortigate alert category on the final row (13) of the dashboard table.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/2f7e0395fdbf0c507830365319abaf8d8e7281524ee7e22127f47f75b64e3ad9af8bb317ed2c1c203a0ece3058b2.PNG)

Clicking on the row will take us to a single Fortigate_UTM log. We can see that the internal IP address is in the ‘dstip’ field, and is 192.168.250.70. Because this log is from a Firewall, Fortigate has no idea what the hostname is for this system, so we'll need to use a different log source to find this.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/0dd824908848e21d5b7659b73517ac0fce1c547b83c421a7faee503d7935603d7f6b30c6d6d44928afb561ecfb51.PNG)

Let's be smart about this, this alert is about abuse of the Microsoft Windows Command Prompt. It is possible that the internal system is running Windows, and should have Sysmon logs enabled (xmlwineventlog). Let's change our search query to look at that sourcetype and free-search the IP (without declaring a field name, as we don't know what format it will be).

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/912bed2646a14c95c4774ed2d8bd405705cadf2dd3c6ea16512ac0a18ee143c2d7fc6fb85e10a64d66c840c9c1c7.PNG)

Here is another proposed method of solving it—which many students find easier:

Filtering by the IP 192.168.250.70 will indeed yield multiple hostnames.

![](https://i.imgur.com/ItPzB7O.png)

However, if the user includes the attacker's IP address in their search, they will obtain a single result and the answer to question 11.

Filter: index=* sourcetype=xmlwineventlog 23.22.63.114 192.168.250.70 | stats count by SourceHostname | sort - count  
 

![](https://i.imgur.com/tEykE5l.png)

---

**Question 12 - Go back to the Fortigate Security Events table and click on 'Apache.Roller.OGNL.Injection.Remote.Code.Execution'. Find the reference field in the log and open the URL on your host machine. What is the Affected Products text, and the CVE identifier?**

We can find the relevant Fortigate alert category on the 10th row of the dashboard table.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/22d85d66cb49ec1b3e029161df1d3fcff3517bb905419cd2a77f9a85036d94160acb45f7e8cf718297822243aa34.PNG)

Looking at the event we can see there is a field titled ‘ref’ which contains a URL.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/fbf8827e17af046ac436551946c0d770f334f4af98622c0a6ab5f7480968af431c3cb8a535f35f318d0d36f7dc4c.PNG)

Unfortunately, when trying to visit the URL, we get redirected to FortGuard's homepage. In the top right we can see there is a search bar, and clicking on it offers us the ability to change it to an ‘ID Lookup’ search. Let's try that with our VID number!

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/61d8980d755c1884bf6da210d6c7b67a4bc89115e35c885f165a48e53925e62503f75aec7ee13f7f48155cc0e55d.PNG)

Next we want to click on the right search result, based on the name of the category we saw in Splunk:

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/a81ca357af6e96b1ac2fbac40db15f601bc0a49d2bb08171155cff0f8031730c836ed4c0b76e3e375d75d70da502.PNG)

Here we can find all the information we need!

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/9399b3db39968e19297d8dd5aae6c5da50e6e2227868a4b380a406e6c4a49960d49f257011d81aa69347f0a7c362.PNG)

---

**Question 13 - On the dashboard consider the Fortigate category with the highest number of events. Try to find the version of the scanning tool being used, looking at Fortigate logs then Suricata logs.**

We can clearly see from the Fortigate alert table that ‘Acunetix.Web.Vulnerability.Scanner’ is the attack type with the most events generated. Let's see if we can identify what version of this tool is being used!

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/5d4c57d5bb544688f9587b828e4870bba3dc9f57a597548edb2b8aa1cb4f08002daae653a44f16d84df84fa07cf4.PNG)

Looking at the logs, there's nothing immediately obvious that tells us the version of this tool. There is a reference field so it's worth seeing if this will tell us the version.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/d9df113128a81412bbb5be132f608ce2a79843f3d84ec7d08289816a62c6f089ac1fd93aac5be501d6f8d620a88f.PNG)

However after searching it online, it doesn't give us any version information.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/e3c51d158139c1c4317d204d969d04358f8cddbfd5c97c97b66e74f7b64444591157eb7a10060a3a525cff7fce9d.PNG)

As we can't find anything helpful in the Fortigate logs, let's pivot to the Suricata logs instead. To do this we'll change our sourcetype to Suricata and free-search for ‘Acunetix’ as this is the name of the scanner.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/63f94326d0dde55aa91fef0b1fa9460db54b272b80abd1d48d84134b7f4cab659150b1ea5373b33ad903c5b34ef3.PNG)

---

**Question 14 - Investigate Suricata 'alert' logs to understand how they present the severity of the alert. Create a search query that gets the count of events based on each severity rating. When you having a working query click on 'Save As > Existing Dashboard' and select the Splunk Investigation 4 dashboard. Edit the dashboard and click on 'Select visualization' on the panel you just added to change it to a pie chart (feel free to add an appropriate title!). Hover your mouse over the 'High' section of the pie chart, what is the count%?.**

We're told we need to look at Suricata alert logs, so we'll perform our first search using: `**index="botsv1" sourcetype=suricata event_type=alert**`.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/66a06262a3657230cd3d97ff0f66c3bdda325bc301b9f15ca86fb9b648b352e7151b1ae994d5e4e92095015f3a1b.PNG)

Now that we know the severity field is called alert.severity, we could perform a stats count for each severity. Interestingly, there is another field called ‘severity’ that is using low, high, medium ratings, which is easier for us to understand than numbers, so we'll use this instead.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/3c6dc2ef74bd2e33889bf57c79928d844cdbccdd58cd4f212261cb77c9d5dd51bc48106a06cc613daa59f218443b.PNG)

Now that our search works, let's save it to our Splunk Investigation 4 dashboard using the ‘Save As’ button.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/79bb67cc368e2b5626554281f714b08c55cffb7dc167e2ab524cdc5ee309d0ef653af650ff9375ce6ce529cd938a.PNG)

We now see the search at the bottom of our dashboard, however by default it is in the Table visualisation, and we want to change this to a Pie Chart. We'll click ‘Edit’ in the top right of the dashboard then click on the ‘Select Visualization’ button of our new panel.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/326b4ab40560c3a01ac21e3e783703c68667c315d08f71ea8cedc55635dccd5804715f0de54a349c8b0934b3a688.PNG)

Next we'll select Pie Chart from the list.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/695e2425bb04fe93320ee3e7c7202fbf7758035e4b170fa73282538bdaa22344d30b146f53ef3f07b15552b7b4e7.PNG)

And we'll see that the graphic has been updated! We're going to set a sub-title (2nd title field) as “Suricata Alert Severity”. We can now click ‘Save’ in the top right of the dashboard.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/d55f15ae397e67d8e082cef0268c7a08b7fbd474258f04871a29cf2e9ab83d7fcc7eeb473487d584d1203591cbfd.PNG)

Hovering over the High section of the chart shows us the count% value we need to answer the question.

---

**Question 15 - Complete the same steps above but for Fortigate_UTM logs, creating a pie chart based on severity. If you want to keep things neat, you can drag your new pie chart next to your Suricata one! What is the count% of critical alerts?**

First we need to understand the field name that holds the severity rating for these logs. We'll perform a generic search for fortigate_utm alert logs, and quickly find a field called ‘severity' - perfect! Let's create a search to get the counts per severity value.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/7586d240fad8162bb3677f68fc85bcd13acb5498081e77f95bdc7c6d2f8d542118e582bcd27806008a1b34e9d1d2.PNG)

Now we'll save it to our dashboard and convert it to a Pie Chart, same as before.

While editing the dashboard, we can click on the ::::::::::::::: border of a panel to drag it around and resposition it. Let's drag our second Pie Chart (fortigate_utm severity) next to our first Pie Chart, and save the dashboard.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/a219ef0f104b3a472f3f1ef22020a7c59db2ddf74bc50ae399860fa767874e77125593eb7df34f75c36578ac7653.PNG)

Hovering over the Critical section of the chart (or the critical text itself, which is easier!) shows us the count% value we need to answer the question.

#### Great! You've made it to the end 💪

Domains List

Prev

 / 4
 
 
 # Lab) Network Traffic Analysis Investigations Solution

1. Incident Response
2. Detection and Analysis Phase
3. Lab) Network Traffic Analysis Investigations Solution

Complete

---

**Question 1 - PCAP 1 - Identify the first evidence of host discovery scanning on the network (prior to TCP). What is the IP address and what is the protocol used?**

Opening the first PCAP we can immediately see Address Resolution Protocol (ARP) traffic.  Based on the ‘Info’ column we can see that 192.168.56.1 is broadcasting on the network, asking every IP in the subnet (192.168.56.2 to 192.168.56.254) what their associated MAC address is. This is a form of network enumeration that allows an actor to identify online systems within the network when they reply to the ARP request with their MAC address.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/35f8d257952ebd1da76152c17eba253e95e235cc96a9b0d4481b55062c518f303effdef564dc1d833e2904b4a4c2.png)

---

**Question 2 - PCAP 1 - What IP address is being port-scanned by the malicious IP?**

In the question we're told that one system is being port-scanned. Based on this information it is highly likely that the attacker's system is attempting to connect to a target system on a large number of ports. Going to Statistics > Conversations we can see that the source IP 192.168.56.1 (column 1) is connecting to random destination ports (column 4) on destination IP 192.168.56.111 (column 3), where each of these conversations is two packets long (column 5). This is clear evidence of port scanning where the target is 192.168.56.111.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/564dc69f35b8ed82dcda2e3ab66c913b29da35777950f6f2b46f6ecdfe86d6642f4c504e45ba002615ab7c4a9d16.png)

---

**Question 3 - PCAP 1 - Take a closer look at some of the packets associated with FTP traffic. How many users are allowed to connect to the FTP server at once?**

Filtering on FTP traffic only using the filter “FTP” we can see a few response packets that provide informational text to the requesting client. Clicking on one we can see in the bottom pane there is text that mentions how many users can have active sessions at once.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/7f8bddb4388f5ab34c65ae0947f2c82b24f2aec8e0dd4365c257bc3ee37c6627d316b2829bde0f380453bc602027.png)

---

**Question 4 - PCAP 1 - The attacker tries to log into the FTP server using the username "anonymous". What incorrect password is supplied?**

Keeping our filter just looking at FTP traffic we can see a request is made by 192.168.56.1 to the FTP server running on 192.168.56.111 with the username anonymous. It's important to remember that FTP is an insecure protocol, meaning we can see usernames and passwords in plaintext. We're asked to find the password supplied during this authentication attempt - we can either keep scrolling down the packet list, or we can right-click the highlighted packet and Follow > TCP Stream.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/8273f75b4217fe6490a68a29f1983bd5e6e02c66d6bdc405c83e5d7754623999e228ee7180280bde02f1dfab315a.png)

In the below screenshot we can see that the client provided the server with the user ‘anonymous’ then the password ‘IEUser@’, which resulted in a failed authentication.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/51db7f0a079d7c98d1afad329d8aba9e7eedbf9f2b896013478de631fd8d3319aa7d033efd2d1046a62f5dcf4144.png)

---

**Question 5 - PCAP 1 - Export the robots.txt 404 page from packet 4612 as a HTTP Object and open the text file. What is the version number of Apache running on 192.168.56.111?**

We're provided with the packet number, and based on the question we know it's HTTP traffic, so we'll filter using ‘http’ then find packet 4612.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/c8b69597fd421ced2178ba345cd850974899db685b11a920f4aef427d6c6c9a6260a03f4d099fa3e07496f99a7b0.png)

In this packet the system running a web server (192.168.56.111) is sending a 404 page not found response back to the requesting client (192.168.56.1). Using Wireshark we can retrieve the HTML file used to generate the 404 webpage that the client will see. Going to File > Export Objects > HTTP we can see HTML pages captured in the PCAP and export them.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/3f95dbe09df43c390e368681d902acddab77c56f886f406331958119b34fd7b23a45a393ef8405a3f50930eb2ec7.png)

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/918b902b2e2d984f2c6cde747d56a2939ce6694de7135c4373b847743426b7f655b08798dd66a28f75180ecc76a6.png)

Looking at the Packet column we can find 4612 and select ‘Save’ then save it our Desktop. Opening the file we can see the web server framework, Apache, and version, 2.4.38.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/c6ecf61cff9e35e2460640254887adaf2bdae18b131bfd33c95512882abe2e75f8ca2f76e71eca0e7a8ab96bcfc1.png)

---

**Question 6 - PCAP 2 - What IP address downloaded the ZIP file?**

Moving to PCAP 2 we know that a ZIP file was downloaded, and the most likely protocol is going to be HTTPso we'll go to File > Export Objects > HTTP. Looking at the window we can see there is a ZIP file based on the Content Type column showing ‘application/zip’. If the ZIP didn't show up here, we would go to File > Export Objects, and look at the other options such as SMB, SFTP, etc.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/e0c6af3074256d20ae0d454b7d70bc89f1d05ad2264ea2c476004b71a43c3d7b1e7b7b3b1277f79865d75e2297ca.png)

Clicking on the row in the popup will take us to the correct packet within the capture, so we can now close this window and look at the main window. We're looking at the 200 response from the server (source = 192.168.56.1) back to the client that is requesting to download the file (destination = 192.168.56.111).

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/6d6fe137fca910d7c9713dd567649daae5769577a8c8730a8056841ce638bacae9a7811c356bbb43f0f2bba4c0f5.png)

To view the entire conversational better we will right-click the packet and select Follow > TCP Stream. We can now see the red section that shows the GET request from the client at 192.168.56.1, and the blue section that shows the OK 200 response from the server at 192.168.56.111, and then the file contents are transferred to the client.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/070d30a0225b306b2b02885ec6ffe95fe8cd05c74fcefc911791300f69809f935f818148263e00617c8fb414aec2.png)

---

**Question 7 - PCAP 2 - What is the source port (server) and destination port (client) for the file download?**

Continuing on from Q6 we'll select the packet where the server provides a 200 and sends the content of the ZIP to the client (if you've lost the packet go to File > Export > HTTP > click on the ZIP entry to select it, then close the popup window).

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/7d4ded8503a0a53e9a0d07bc89eff0a47c0d30c878bfffcb713cee9d4005e6f81bfa8b44f952fe1de539d0b1618e.png)

In the above screenshot we can see within the TCP layer the source (server) and destination port (client).

---

**Question 8 - What is the filename of the downloaded zip file?**

Based on the analysis we've done in the previous 2 questions, we know that filename is cr4ckx0r.zip.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/31763f84159f1047154c0d899e6c310da7eb7fcde7bb08200d06efa6057494d18ea4d14c3bc7336690510e0577d4.png)

---

**Question 9 - PCAP 2 - Export the ZIP file and save it to your system. What are the first 5 characters of the MD5 hash value of the ZIP file?**

Using File > Export > HTTP, then saving cr4ckx0r.zip to the Desktop we can open a terminal, use `**bash**` to get a bash shell, then run `**md5sum cr4ckx0r.zip**` to get the hash value.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/6da2bc317a861bc5cfbd52190365d7b1e52fe6103c0597c4136b81649af17a0c56782bf9f48921adfd8e6e4aee57.png)

---

**Question 10 - PCAP 2 - What is the name of the file inside the ZIP? (without file extension)**

We can view the files inside the ZIP by simply double-clicking the ZIP icon which will open it in xarchiver. We can see that the file inside is named ‘hashcat', a popular offensive/auditing tool used to crack hashes and passwords to reveal the plaintext versions.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/7befebb15793c9e4e281f4868f1ae8137d21837474bc01de524f4417df59658141676484a213fe34c72ddbee38f6.png)

---

**Question 11 - PCAP 2 - What are the first 5 characters of the MD5 hash value of the file inside the ZIP?**

We can extract the file by right-clicking the ZIP icon and selecting ‘Extract Here’ to save it to the Desktop. We'll then open a terminal, type `**bash**`, then use `**md5sum hashcat**` to get the answer we need.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/5db6f94771c325e876a933c39f8ad8d34997ab54c6f0053b8df9fd3c43cdace31e6332baaeabf6d459bde58e6178.png)

---

**Question 12 - PCAP 3 - What IP address is running an FTP server?**

Moving to PCAP3, to look only at FTP traffic we'll use the filter `**ftp**` to remove any unrelated noise. We're looking for the server's IP address, so we need to pay attention to the Info column to understand what's happening, and then use the Source and Destination columns to get the server IP.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/e5e8bb9a9565434961153e975ce0c0d2c2eb43b83e9016f16946c795eedb3e220bf001afd0aaad93c954a64ab462.png)

In the above screenshot we can see a number of FTP packets containing `**Response: 220**`. In the screenshot below we can expand the FTP section and get more information about what the 220 response code means.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/90675813dd3258b0b95c7eececc71a265fa04a184a55c6ae3bdadade9095c095a4d905e9306fedb7d5c2a4641b56.png)

So know we know that this packet represents the FTP server sending a response message to a client that is attempting to initiate a connection. From this information we know that the source IP must be the server, because it is sending responses to requests. The FTP server IP is 192.168.56.118.

---

**Question 13 - PCAP 3 - At what time does the attacker send the first password in a dictionary attack against the FTP server?**

Scrolling down the packets with our ftp filter still applied, we'll come across packets that contain ‘PASS’ followed by a value, which represents a password submitted to the server.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/be619ab510adedab2d1df03b856ebff58eaeef16cdebc5d1778f0c18c044e13b9c3e967fddf868d48e88ab9c2faf.png)

But, looking at the Time column, we can see the value is 0.46195… - this value is the time elapsed since the first packet was captured. As the question is asking for the time in the format YYYY-MM-DD HH:MM:SS we need to change how this column is formatted. We'll do this by going to `**View > Time Display Format > Date and Time of Day**` (first option at the top).

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/f31020402eca912ab1dd731688953d9fe4b5d994861e379fb1109dc68c7ff2e93c5a655dd3c4f86947844843e990.png)

Following the requested format, the answer is 2020-05-26 14:51:19.

---

**Question 14 - PCAP 3 - At what time does the attacker successfully log into the FTP server?**

Looking through the Info column, we can see a Response from the server, `**230 Login Successful**`. We can get the answer by looking at the Time column and matching the requested format of YYYY-MM-DD HH:MM:SS.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/ff089ec39451053fefa64d061ba9e513ffe29a4e68b69d94eaed821ea2404ec52cd3e2145e3b46c243ea12b9010e.png)

---

**Question 15 - PCAP 3 - What credentials allowed the attacker to log into the FTP server?**

We can get the USER and PASS by looking at the packets previous to the 230 Login Successful, reading the Info column, or we can right-click the 230 Login Successful response and go to Follow > TCP Stream.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/28a3f831fade2897bb41fd7ec672ba7f989e8ebe0f35e6ad18c8fe9bb243749d918d6176a8632aaad2cecdea4489.png)

---

**Question 16 - PCAP 3 - What is the name of the file downloaded from the FTP server?**

The easiest way to see what actions were taken in an FTP session is to right-click a 230 Login Successful response and follow the TCP stream. Completing the same actions as we did for Q15, when we can see everything in the TCP stream window. In the below screenshot you can see the RETR command, an abbreviation for Retrieve, which tells the server to send the requested file to the client. We can see that the user Chris logged in to the server and downloaded password.backup.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/5be072f499818f9e1a61d132b5c58c9ddc293ccd0fddaac039534ed092cc8005ec483287a1af8f7546439bdb1f58.png)

---

**Question 17 - PCAP 3 - At what time does the attacker send the request to download this file from the FTP server?**

Looking at the TCP Stream for the 230 Login Successful from the previous questions, we can actually click on the line that references ‘RETR’ which will take us to that packet in the PCAP. We can now close the Stream window and grab the Time value.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/5dce016ee6086c51e2d2ceaeecabf23b907ff88c735dea4b1d0ffdabda5996b07adecc4b9981634cb4444a7fcf40.png)

#### Great! You've made it to the end 💪

Domains List

Prev

# Lab) CMD and PowerShell Solution

1. Incident Response
2. Detection and Analysis Phase
3. Lab) CMD and PowerShell Solution

Complete

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/eaf953b9ce9c1a3ad5eadc56cd89e2c3ddd8faa28e3c8ebef8f0dcddc5a6a4705f5d0bf9162da6a4ef76356f2835.PNG)

**Question 1 - Processes) To export a list of running processes from a Command Prompt into a text file, open a cmd session on the Desktop (or move into the desktop using "cd Desktop") and run "tasklist > tasklist.txt". Open this in Sublime Text and use the Find feature on the top menu to look for instances of cmd.exe. How many are there in total?**

After moving the CMD session to our Desktop (cd Desktop) and running the stated command (tasklist > tasklist.txt) we will right-click the created text file, Open With, and select Sublime Text.

Using CTRL+F and searching for “cmd.exe” shows 4 results (technically one of these is ours, which we used to get a list of running processes, so either 3 or 4 is a correct answer).

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/6ac46a64bd96972f91c4f3d9d69939f53e7ba6eac095bf1b81a106820feb6895ef1f57f0774fc8f453625513c44f.PNG)

**Question 2 - Users) How many accounts in total are present on the system?**

Using the command `**net users**` we can get a list of all local users on the system.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/aedf6563509ea465aeaca00b32d501b6954eac2424325cab2ab5ec51d0b5479760d313a3b356267a8d37c5027fd5.PNG)

**Question 3 - Users) How many of these accounts are in the administrators localgroup?**

Using the `**net localgroup administrators**` command we can list all local accounts that have administrative privileges.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/0a3d8ac3a769926a8717f06e179aa1efc2bc09ea5500b82854ee92e935333f56b945c9f492777cf110c1755faf93.PNG)

**Question 4 - Users) What is the name of the suspicious administrator account?**

Looking at the above screenshot, we can see there is an account with the name ‘ServiceeAccount’, which appears to be trying to imitate an account that could exist on the system for legitimate purposes.

**Question 5 - Users) What are the names of the local accounts that are able to connect to the system using RDP? (List them in alphabetical order)**

Using the net localgroup “Remote Desktop Users” command we can see that only one account is able to RDP, the suspicious account from the previous question.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/161c5b92c2a84c60b6dc16cfc8f65f670509bd0011a82ca72b564f5bb34dc8569d30965e2459db484f697d495a84.PNG)

**Question 6 - PowerShell Users) Run the command to get detailed information about the suspicious account identified earlier. When was it last logged in?** 

Using the command `**Get-LocalUser -Name ServiceeAccount | Select ***` we can retrieve all properties relating to this local account. Highlighted we can see the last login timestamp.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/86257b82d51145b40ef82499a6ffc6b88665dc3bcb6e832dda6dd2966d557c2b2f2373952e85664329dc570d0240.PNG)

**Question 7 - PowerShell Services) Run the command to list services on the system. What is the display name of the service starting with "Amazon"?**

Running the command Get-Service | Where Status -eq "Running" | Out-GridView will open a new window. From here, we can see that the service we've been asked to find is at the top of the alphabetical list.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/b03b663971c5dbc2eb64f3f4ada3302dd0c88260e679cc14c0d50280ff59849a0c096c6a0cf91bd9d55d4047f2be.PNG)

**Question 8 - PowerShell Scheduled Tasks) Get a list of all Scheduled Tasks. What is the TaskName of the entry beginning with 'P' that is in a Ready state?**

Using the command `**Get-ScheduledTask | Where State -eq "Ready"**` we can see only Scheduled Tasks that are in the state we're looking for. The first item shown is the task we're looking for.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/39ea31b38b6bdfd59caf37dad59cd8b0f1f660433f8a0f781d71075a2cfaf1572abb5d7266ababc1a9d22fe51bd4.PNG)

**Question 9 - PowerShell Scheduled Tasks)  Run the command "Get-ScheduledTask -TaskName 'TaskNameFromLastQuestionHere' | Select *". Look at the Triggers property, what is it?**

Running the provided command we can see that the Trigger property is set to when a user logs into the system.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/4a9bb802f2b078938f66b54e0d4d8166970812008769d69c15f3a1fc73c943bb55df959259d2ea8d1e30be12dddf.PNG)

#### Great! You've made it to the end 💪

Domains List

Prev

# Lab) DeepBlueCLI Solution

1. Incident Response
2. Detection and Analysis Phase
3. Lab) DeepBlueCLI Solution

Complete

**Question 1 - Run DeepBlueCLI from a PowerShell window, and set the target evtx file as .\evtx\password-spray.evtx. How many accounts were targeted in a password spray attack, and what is the MITRE ATT&CK Technique ID for password spraying?**

Running the provided command we can see that 41 accounts were targeted in this password spray.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/362b8bd9c926fd67ded3ef0dba512bc1288264b58cff43b86097ab0ce528f63af45aaf3142b40d413ff168820409.png)

Searching Google (or the MITRE ATT&CK website directly) for “password spray”, we find the following sub-technique page:

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/1c2f0ed4bbce1774cf770cdd2a062f8d9ca7f4dc214406c26ae817d35d19a7db1518d6dc8b753ca6b884e1c890da.png)

---

**Question 2 - Still looking at password-spray.evtx, what is the responsible user and hostname of the system?**

Looking at the output of the command, we can also find the username and hostname.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/8c95a2110f9a2e054b8f1f214bb1f71405e2cf4f493e1089a4b22a0527e9a5012d6b0abddafb7ace91f8f8ab0227.png)

---

**Question 3 - Investigate new-user-security.evtx. What is the username of the created account, and what group was it added to?**

Looking at this new evtx file, we can easily find the username and the group they were added to.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/50d2c90a722c4e79377b2d10e57ff2402429e9039efa386222e9cd61de394f55a91b5c8d905662d9ab5327f6448a.png)

---

**Question 4 - Investigate powersploit-system.evtx. What is the MOST RECENT file that is being downloaded using PowerShell's 'Net.WebClient' functionality? Provide the full URL**

Running DeepBlue against this .evtx file shows two detections for downloads, however, based on the question we've been asked to find the most recent one.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/c37bd519e1dafb2d74aee0ec99150c9e9cf454a3b9b44ba5d9a421908710aacbd74387e97aab98ce984012495001.png)

---

**Question 5 - To look at all of the event logs at once and export it to a text file, we can use the following argument "./DeepBlue.ps1 .\evtx\* > output.txt". Lots of open-source offensive tools are stored on GitHub, which means attackers can download them using PowerShell. Open the created text file and use CTRL+F to search for "githubusercontent". What is the .ps1 script that is downloaded?** 

Following the steps, we run the command which will create ‘output.txt’ in the DeepBlue folder on our Desktop.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/c68a81f3e752dcf3629448b7d3e944c496d0e94f267bcf719246b4396b22603b4d8672412d21b37a5dcbe88bcfa2.png)

Searching for “githubusercontent” there are 3 matches, all of which are for the same file download, but at different times. This gives us the answer to the question.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/fc0bf61ae96e9e893775829a74ca771ce660bf1fdde6d00569951fd4409008888427a64400789c7a4eb285d2a808.png)

---

**Question 6 - Search for the name of the tool on MITRE ATT&CK. What is the Software ID given to this tool?**

Searching on Google for “Mimikatz MITRE ATT&CK" we can find the Software page for this tool.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/e2dbe906b1345253ca15154ed0df854ea0eeacea7ac801878c0138837e44aff593bcb4807e2eb0a0e4ad6f96d5da.png)

#### Great! You've made it to the end 💪

Domains List

# Lab) TheHive Solution

1. Incident Response
2. Case Management
3. Lab) TheHive Solution

Complete

**Launching TheHive**

We are provided with steps to follow on the ‘Instructions’ tab of the lab client.

We'll open a terminal from the bottom taskbar and enter the command `**sudo docker run -p 9000:9000 btl1-thehive5**`.

We can see from the header of our terminal window (or using the ifconfig command in a new terminal, and looking for the ens5 adapter's IP address) that the private IP of our machine is 10.0.2.26, so we'll open Firefox and visit HTTP://10.0.2.26:9000. We can now see TheHive login screen! The instructions tell us that we need to login using BTL1@securityblue.team and password.

---

**Question 1) How many cases have been recorded within TheHive?**

From the Cases page, we can see that there are 6 cases present in the platform.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/9e4d2830f596e003190d2557b579962bd5c24cc95ce72965028f44301978b4a5e545b551b7a2a0dd1f9d310dd008.png)

---

**Question 2) How many cases are open, and how many are closed?**

There are a few ways we can get this answer, one of them involves clicking on Quick Filters, which gives us the open and closed count.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/cf531d557269ba0c908d8ea66721f8fc79f0ed84d6b88353a4b5d094f9f6298325dc583c8abdad6a8af4afe81715.png)

---

**Question 3) Investigate the #5 case. What tags have been assigned to this case?**

From the list of all cases, we can see the second column has a heading of “#NUMBER”, so we'll click on the title of the #5 case.

From the General tab, we can see there are two tags applied, “phishing” and “email”.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/194185c4df5edc6e648b3f63adc8668b2b1602bd6ce2c7c5a6c286c4c27008592e2336f0aa5c24b99b539a603f02.png)

---

**Question 4) Look at the task related to taking defensive measures. How many blocks have been requested/conducted?**

Navigating to the Tasks tab and clicking on the ‘Take Defensive Measures’ task, we cab see that the analyst has requested/conducted 2 blocks, one email block and one web block.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/55aea566d10d8015f77cdc51d5e018f2fee7c8d2cde9490a3103ca91be9aa3ea194a7e0be339862542173d734d7a.png)

---

**Question 5) How many Observables have been created for this case?**

From the Observables tab name, we can already see there is (8). If we click into the tab we can also count them ourselves.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/15b92fb27692ae843dd548345bdc00d2260b1386071b0e816a36907bc95236bb00cdb91b9711641db9630979cde3.png)

---

**Question 6) There is an Observable with the data type 'ip' that begins with 54. What is this IP related to?**

Clicking on the IP data-type observable for 54.240.48.89, we can read the description and see this is related to a “sending server ip”.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/85f0c27217f56e8e8affcf7559d1b12868f49be7bb55f2fb4b5cb89080a320c5b2ebf53742040d1d6e2e9cc131f9.png)

---

**Question 7) What is the size of the attachment within the case?**

Heading over to the Attachments tab, we can see in the SIZE column there's a value of 24.66 KB.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/c5793f03c710acc0e458e09bce480bfc4a2bccb248fa63dfb2dcfb17407f5c10f4d6fb0902c6451311acf56de338.png)

---

**Question 8) This case was closed. What was the Status, and was there any Impact?**

Looking at the left column with the case properties, we can see the Status is TruePositive, and the Impact is No.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/0e44149d67f2c10ddcae0bbddb3aa933078f95f1799a387ee02f6208ccf83cf400be2d0153f61ba74a7368a1f811.png)

---

**Question 9) Case #4 is missing something important to the case. What tab is missing this important information?**

After looking through the tabs that we've been trained to use (case properties left column, General, Tasks, Observables, Attachments, Comments) we can see that this case is referring to a file, but there are no attachments! It's important to make sure files are attached.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/eb60b1fd201deac5a63acce505cde03b0aa45f86190a03b14f0beaceae44f4c022ca1811cc23377a1cbe19c128c5.png)

---

**Question 10) What is the name of the Security Incident Response Team member that assisted with this case?**

To understand the case, we want to read the tasks to see what is happening. From this, we can gather that Jason Smith from SIRT has been asked to assist.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/60a4e563744af871cb84d3611dffb7f5ac0a34cf13d3deb408cdbd69027c4f63d04a2afd817046c2fab32f0ea7a0.png)

---

**Question 11) How many tasks have been marked as complete?**

There's a few ways to get this value, but we'll click on Quick Filters and then Complete tasks, where we can see there are 14 results.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/5f1dcfdd7cbc78024a30cf02e1e2aeb5af648aa631c151d87d24ca34ae1c83155157f4d1660793df9fab9547b1fc.png)

---

**Question 12) How many tasks have a status of Waiting?**

We'll complete the same actions we did for Q11, but select ‘Waiting’ from Quick Filters instead. There are 9 waiting tasks.

---

**Question 13) Looking at the Operations Dashboard, how many cases have a severity of Low, Medium, and Critical?**

Moving to the Dashboards page we'll click on Operational Dashboard. In the donut graph on the right (Case Severity) we can see there are 2, 3, 1 low medium and critical severity cases.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/be2339f78e35c3c7a18a781606258fd0b8a43db2fb44179323828a6a3b1ae5f47601e50075b6361f5c7751ad74c9.png)

---

**Question 14) How many case templates are available for use by the team?**

Looking at the middle dashboard graph we can see there are currently 5 different case templates ready for use by analysts.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/06f374606933d729df52db2175420ffd4ecaa537e89173a55e02731ae755c059be999da7330fa63c2150279424a9.png)

---

**Question 15) Go back to Cases and open #4. Look at the left-hand column of the case, and notice the red "1" icon in the bottom left, called "Related Cases". Click this. What is the title of the related case?**

Going to the Cases page then select case #4, on the bottom of the left column we can see the following:

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/6cd63cd8bbbd8732794414402e9df7c95fbed8f7714098f20d6b8c3cdf2911d040b04a5cac130f68bc7ca4f2a6f8.png)

Clicking on this icon will change the middle panel to show the related case, and how it's related.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/93e54b776704c74761031569e5c600be3f179d41079533547d5d67557eee54a5a37efd8be1e843df606e2cd7d0e4.png)

---

**Question 16) What is one of the two linked observables that are shared by both of these cases?**

We can see the two linked observables in the right-hand column. Submit either of these.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/93e54b776704c74761031569e5c600be3f179d41079533547d5d67557eee54a5a37efd8be1e843df606e2cd7d0e4.png)

---

**Question 17) Don't forget to play around with TheHive! Once you're done, you can type "complete" below to finish this last question.**

When you're done with the lab, type the text “complete” into the answer box.

#### Great! You've made it to the end 💪

Domains List

Prev

*These notes will come handy in exam.*

## SOC Fundamentals

List of common ports.

|Port|Service|Description|
|:---:|:---:|:---:|
|20,21|FTP|File Transfer Protocol used to transfer files b/w systems.|
|22|SSH|Secure Shell Protocol allows users to securely connect to a remote host.|
|23|Telnet|Used before SSH, allows users to connect to a remote host, doesn't offer encryption.|
|25|SMTP|Simple Mail Transfer Protocol used to send emails between servers within the network, or over the internet.|
|53|DNS|Domain Name System converts human-readable domain names to machine-readable IP address.|
|67,68|DHCP|Dynamic Host Configuration Protocol assign IP address-related information to any hosts on the network automatically.|
|80|HTTP|Hypertext Transfer Protocol allows browsers (Chrome, Firefox, etc) to connect to web servers and request contents.|
|443|HTTPS|Hypertext Transfer Protocol Secure is a secure version of HTTP Protocol which allows browsers to securely connect to web servers and request contents.|
|514|Syslog|Syslog server listens for incoming Syslog notifications, transported by UDP packets.|

## Phishing Analysis

### Gathering IOCs

1. **Email Artifacts** :

- [ ] Sending Email Address
- [ ] Subject Line
- [ ] Recipient Email Addresses
- [ ] Sending Server IP & Reverse DNS
- [ ] Reply-To Address
- [ ] Date & Time

2. **Web Artifacts** :

- [ ] Full URLs
- [ ] Domain Names

1. **File Artifacts** :

- [ ] Attachment Name
- [ ] MD5, SHA1, SHA256 Hash Value

### Analyzing Artifacts

2. **Visualization Tools** - [URL2PNG](https://www.url2png.com/), [URLScan](https://urlscan.io/), [AbuseIPDB](https://www.abuseipdb.com/)
3. **URL Reputation Tools** - [VirusTotal](https://www.virustotal.com/gui/), [URLScan](https://urlscan.io/), [URLhaus](https://urlhaus.abuse.ch/), [WannaBrowser](https://www.wannabrowser.net/)
4. **File Reputation Tools** - [VirusTotal](https://www.virustotal.com/gui/), [Talos File Reputation](https://www.talosintelligence.com/talos_file_reputation)
5. **Malware Sandboxing** - [Hybrid Analysis](https://www.hybrid-analysis.com/), [Any.run](https://any.run/), [VirusTotal](https://www.virustotal.com), [Joe Sandbox](https://www.joesandbox.com/)

## Digital Forensics

6. Data Representation can be done in following ways,

- Base64
- Hexadecimal
- Octal
- ASCII
- Binary

7. File Carving :

```bash
scalpel -b -o <output> <disk image file>
```

8. Hashes :

- **Windows** -

By default, `get-filehash` command will generate SHA256 sum of a file,

```powershell
get-filehash <file>
```

To generate MD5 hash of a file,

```powershell
get-filehash -algorithm MD5 <file>
```

To generate SHA1 hash of a file,

```powershell
get-filehash -algorithm SHA1 <file>
```

- **Linux** - 

```bash
md5sum <file>
sha1sum <file>
sha256sum <file>
```

9. Find digital evidence with 
	- **FTK Imager** - Import .img file in FTK imager
	- **KAPE** - Can be used for fast acquisition of data.

10. **Windows Investigations** :

- **LNK Files** - These files can be found at 

```md
C:\Users\$USER$\AppData\Roaming\Microsoft\Windows\Recent
```

- **Prefetch Files** - 
	- **PECmd** - This tool can be used to view the prefetch files. `PECmd.exe -f <path/to/file.pf>`

These files can be found at 
```md
C:\Windows\Prefetch
```

- **Jumplist Files** - These files can be found at

```md
C:\Users\% USERNAME%\AppData\ Roaming\Microsoft\Windows\Recent\AutomaticDestinations
C:\Users\%USERNAME%\AppData\ Roaming\Microsoft\Windows\Recent\CustomDestinations
```

- **Logon Events**
	- **ID 4624** - successful logons to the system.
	- **ID 4672** - Special Logon events where administrators logs in.
	- **ID 4625** - Failed Logon events.
	- **ID 4634** - Logoffs from the current session.

These event logs can be found at
```md
C:\Windows\System32\winevt\Logs
```

- Capture and view the browser history with 
	- **Browser History Viewer** 
	- **Browser History Capturer**

11. **Linux Investigations** :
	- **/etc/passwd** - contains all information about users in the system. 
	- **/etc/shadow** - contains encrypted passwords
	- **Unshadow** - used to combine the passwd and shadow files.
	- **/var/lib** - In `/var/lib/dpkg/status` location, this file includes a list of all installed software packages.
	- **.bash_history** - contains all the issued commands by the users.
	- **Hidden Files** - isuch files whose name begins with **.**
	- **Clear Files** - files that are accessible through standard means.
	- **Steganography** - practice of concealing messages or information within other non-secret text or data.

12. **Volatility** - 

Find the imageinfo of the file, 

```bash
volatility -f /path/to/file.mem imageinfo
```

List the processes of a system,

```bash
volatility -f /path/to/file.mem --profile=PROFILE pslist
```

View the process listing in tree form,

```bash
volatility -f /path/to/file.mem --profile=PROFILE pstree
```

View command line of the specific process with PID XXXX,

```bash
volatility -f /path/to/file.mem --profile=PROFILE dlllist -p XXXX
```

View Network Connections,

```bash
volatility -f /path/to/file.mem --profile=PROFILE netscan
```

Dumping the process with a specific PID XXXX,

```bash
volatility -f /path/to/file.mem --profile=PROFILE procdump -p XXXX -D /home/ubuntu/Desktop
```

Print all available processes,

```bash
volatility -f memdump.mem --profile=PROFILE psscan
```

Print expected and hidden processes,

```bash
volatility -f memdump.mem --profile=PROFILE psxview
```

Create a timeline of events from the memory image,

```bash
volatility -f memdump.mem --profile=PROFILE timeliner
```

Pull internet browsing history,

```bash
volatility -f memdump.mem --profile=PROFILE iehistory
```

Identify any files on the system from the memory image,

```bash
volatility -f memdump.mem --profile=PROFILE filescan
```

13. **Metadata** - Data about data
	
- **Exiftool** 

```bash
exiftool <file>
```

## Security Information and Event Management

### SPLUNK

Queries must start by referencing the dataset,

```md
index="botsv1"
```

To search for a source IP (src) address with a value of 127.0.0.1,

```md
index="botsv1" src="127.0.0.1"
```

To search for a destination IP (dst) address that this source IP address made a connection with a value of X.X.X.X,

```md
index="botsv1" src="127.0.0.1" dst="X.X.X.X"
```

## Incident Response

14. **Network Analysis** - use Wireshark to import .pcap, .pcapng files.

15. **CMD** : Command prompt can be used to view the valuable information,

To view the network configuration of the system,

```cmd
ipconfig /all
```

To check running processes and programs,

```cmd
tasklist
```

Display running processes and the associated binary file that was executed to create the process,

```cmd
wmic process get description, executablepath
```

To view all number of users in the command prompt

```cmd
net users
```

List all users that are in the administrators user group,

```cmd
net localgroup administrators
```

List all users in RDP group,

```cmd
net localgroup "Remote Desktop Users"
```

List all services and detailed information about each one,

```cmd
sc query | more
```

List open ports on a system, which could show the presence of a backdoor,

```cmd
netstat -ab
```

16. **Powershell** - Can also be used often retrieve much more information.

These commands will get network-related information from the system,

```powershell
Get-NetIPConfiguration
Get-NetIPAddress
```

List all local users on the system,

```powershell
Get-LocalUser
```

Provide a specific user to the command to only get information about them,

```powershell
Get-LocalUser -Name BTLO | select *
```

Quickly identify running services on the system in a nice separate window,

```powershell
Get-Service | Where Status -eq "Running" | Out-GridView
```

Group running processes by their priority value,

```powershell
Get-Process | Format-Table -View priority
```

Collect specific information from a service by including the name in the command (-Name ‘namehere’) or the Id, as shown above and below,

```powershell
Get-Process -Id 'idhere' | Select *
```

Scheduled Tasks are often abused and utilized a common persistence technique,

```powershell
Get-ScheduledTask
```

Specify the task, and retrieving all properties for it,

```powershell
Get-ScheduledTask -TaskName 'PutANameHere' | Select *
```

Changing the Execution Policy applied to our user,

```powershell
Set-ExecutionPolicy Bypass -Scope CurrentUser
```

17. **DeepBlueCLI** - PowerShell script that was created by SANS to aid with the investigation and triage of Windows Event logs.

To process log.evtx,

```powershell
./DeepBlue.ps1 log.evtx
```

DeepBlue will point at the local system's Security or System event logs directly,

```powershell
# Start the Powershell as Administrator and navigate into the DeepBlueCli tool directory, and run the script

./DeepBlue.ps1 -log security
./DeepBlue.ps1 -log system

# if the script is not running, then we need to bypass the execution policy
Set-ExecutionPolicy Bypass -Scope CurrentUser
```


# Lab) Manual Artifact Extraction Solution

1. Phishing Analysis
2. Investigating a Phishing Email
3. Lab) Manual Artifact Extraction Solution

Complete

**Lab Overview**

  
In this activity, you will be manually collecting artifacts from safe phishing emails. The Mozilla Thunderbird email client can be used for viewing, as well as the Sublime Text 2 text editor for looking at the .eml files directly Manually collecting artifacts using a client and text editor, is a core skill for phishing analysis, as not all organizations will have access to tools that can automatically retrieve email, web, and file-based artifacts.

The only tools you need to use for this lab are the Mozilla Thunderbird email client and Sublime Text 2. Launch it and drag the emails in (or right-click an email and select 'Open With'), then select either of these two tools.

**If you are prompted to log into Thunderbird, close this prompt and you'll be able to use it without an account.**

---

**Question 1 - Email One - What is the sending address?**

Opening the email in Sublime Text we can use the Find feature (CTRL+F) to search for “From”.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/c29d138b22bd83eb3dbc058078d6909d16ea478a4778abc8e96b5d35bd4e683f90f565e67274f69c3618bca1f1af.PNG)

---

**Question 2 - Email One - What is the recipient address?**

For this question we'll look for the “To” field and its value.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/a2e6cabef06eb995e8d0afdc865286e36f918160e83a5658a1d719008b5ace0adc0e7838d8f5189d00b63768ec8c.PNG)

---

**Question 3 - Email One - What is the subject line?**

For this question we'll look for the “Subject” field and its value.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/67550c8ca23ee77f3836587dfaf220b04bdd3e132fbdda6ecaafcf389f5bcc9cea47e5cb4750dcf2531be556df86.PNG)

---

**Question 4 - Email One - What is the date and time the email was received? (Retrieve this via text editor. Format: DD MonthName YYYY XX:XX:XX)**

For this question we'll look for the “Date” field and its value.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/2d2da11fd2589431d692777f821cf72814489822cd9ea0ca8eb98917d27b5367fd5a5f60d7b87e7770791d41e29e.PNG)

---

**Question 5 - Email One - What is the sending server IP address?**

For this question we'll search for the “X-Sender-IP” field and its value.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/5bad9ccf9a122c71977a476f33f8a6e64b4f9b7116acd51a6e60b5cfe40fd0f80c25e6b95059a4c8f3f913e7c9eb.PNG)

---

**Question 6 - Email One - What is the hostname of this IP address? (Reverse DNS Lookup)**

Taking the IP from the previous question we'll open the site [https://whois.domaintools.com](https://whois.domaintools.com/) and perform a search. We can see the resolved hostname below.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/6450e251ebd6b77937fb4a39aa4079608e679c0b825d8d892b0731846d8cce68ef1a0d79a1386e66c051f9693646.PNG)

---

**Question 7 - Email One - What is the full URL hyperlinked within this email?**

The easiest way to retrieve this artifact is to (carefully) right-click the hyperlink when viewing the file in an email client, and select ‘Copy Hyperlink’ (or a similar option).

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/c62789480d6b9624cf464b1c9fac1db8b4734ae95d822ed700858f3636457cc3b8a9caafbef5ae3e2eb0fc7bdd46.PNG)

---

**Question 8 - Email One - What is the root domain of the URL?**

To find this we can either right-click the link in the email and select ‘copy link location’ and paste it into a program such as Notepad to see the URL text, or search for ‘http’ or ‘https’ in the email file until we find the right link. The ‘root domain’ essentially means the domain name of the URL, not including the specific resource. For this email, the URL is hxxps://www.thiswouldbeamalicioussite.com/index/2020/j411/NetflixLogin.php? (we're replaced https with hxxps to stop it from becoming hyperlinked), so the root domain is ‘thiswouldbeamalicioussite.com’.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/65a63d5262e78a5af01c7137ad5d696ad363396ceaea5cafde17b2a89c4f01a2ff6970a13d3c396df523e14fa6fb.png)

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/ebac7eb38943825eeca0e238f8b3498d041a5581d7ca0c9ec133f5bb86bba09731d4d71ad73ce16037e736396af8.png)

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/c961a3248ef6d5005c6bcc171823403a1a99367de5cee337aa441c7ff09cc04f0781234649d659b032d618163fc8.png)

---

**Question 9 - Email Two - What is the sending address?**

Same as before, we'll use Find and search for “From”.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/54bd12eeb34fed06c44b7b52c5d191ccab8e3996764152afc988d4d68930d8aa6985c11328d284715856f398ab13.PNG)

---

**Question 10 - Email Two - What is the recipient address?**

Searching for the “To” field and value.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/24f700c0102a36ab7a536d1b9a8d93a6cc8390c75db389a61afdf08fd70aa115952b890481d9a0ef88b1081be071.PNG)

---

**Question 11 - Email Two - What is the subject line?**

Searching for the “Subject” field and value.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/c9332658e7328bf2d322fd2660ef2355da7281e81036f8deb558742d3f2709e96aaa4bb382806f2bbcfebfda29b1.PNG)

---

**Question 12 - Email Two - What is the date and time the email was received? (Retrieve this via text editor. Format: DD MonthName YYYY XX:XX:XX)**

Searching for the “Date” field and value.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/814ce34a8446b41ba7e8a650703f5379f83ff006c43738cbe998c91d9323d3d2e9bf7c466a74564bbe0bf5cf8b30.PNG)

---

**Question 13 - Email Two - What is the sending server IP address?**

Searching for the “X-Sender-IP” field and value.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/b8f46e23c75b02d06356ba61d8e768e342ac4b0d2ee5e245266535185f566c4fa6441a5d0e9374aa5c769244e464.PNG)

---

**Question 14 - Email Two - What is the hostname of the sending server IP? (Reverse DNS Lookup)**

Using the IP from the previous question, we'll submit it to https://whois.domaintools.com.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/7c9026b6b7448e650ce2269c4b3f68bb06180260941ddde12bfadf29f0d1c3a943f5325302b74597e6a2dea7572d.PNG)

---

**Question 15 - Email Two - What is the full file name? (name + extension)**

There are two ways we can get the file name. From within the text editor we can search for “filename”.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/1ad38a2bbed8db1c349a97f3114cbf9b1488af6b04afaa089d64292d21ccd3a4639693daf7f0d42793997ee15eca.PNG)

And within an email client we can see the attachment name somewhere in the interface. The location and style will vary depending on the client, but Outlook for example will show the attachment details at the top of the email. In Thunderbird, we see this at the bottom.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/82d00b520d7dfb4f8553c96185e737e971ba785bdfa1bfe7e756397d307b2da9e4f64ff81d3cfcaefdd7c0b73709.PNG)

---

**Question 16 - Email Two - What are the MD5 and SHA256 hashes of the attached file? (Format: MD5 SHA256)**

In Thunderbird we can right-click the attachment and click Save-As, then save it to the Desktop. We'll then open a PowerShell window and use the Get-FileHash cmdlet to retrieve the MD5 and SHA256 hashes. As SHA256 is the default hashing algorithm we don't need to state it, however we must do this for MD5.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/4c72a1863ca9b7e1e32e642b48cfdc7c24a16d28e682be280f6f1797aba61e11c3a5b25ae59e8d1f8b7e8d6752fe.PNG)

# Lab) Investigating an Attachment Solution

1. Phishing Analysis
2. Analyzing Artifacts
3. Lab) Investigating an Attachment Solution

Complete

**Question 1 - What is the name of the file that was attached to a phishing email?**

Looking in folder for Lab 3 on the Desktop we can find the file. Right-clicking it we can go to Properties and copy the filename. We also need the file extension, which we can see on this panel is ‘.html’.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/edc718e32d68c04c7c1e03452bd65ea587b21d1ee058ac0f5b11ddc659e022daf100a2b17444b7ae62a4a4d0173a.png)

---

**Question 2 - What is the SHA256 hash value of this file?**  
We can hold shift and right-click in the folder that contains the file to select ‘Open PowerShell Window Here’. Then we'll use the command Get-FileHash MICRO (then pressing the Tab key to auto-complete the filename).

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/ebaa234416efbc896ef220a143721bb1854ab479cfe3688f99597721f7713ca68b7b8043c2aeff1747fe5d56b279.png)

---

**Question 3 - What is the file size in KB?**

We can get this value by right-clicking the file, clicking Properties, then looking at the Size property.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/8aba5e2905ca4ad086b9f1593d768bef90f86da2b0350528b51b9909855c6dfc1dd83a671a64bebdd94910a798d3.png)

---

**Question 4 - Open the file - What company is the presented web page trying to impersonate?**

Based on the Website Title property and the design, this web page is imitating Microsoft's Outlook / Office365 login portal (even though the logo image isn't loading, because the lab has no internet connection).

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/a16eb29db784da99024568f50a7b59e3eb5c2dc22877a7e134808951705d191ceba2e6f9ce55f6cf00d5d623fe15.png)

---

**Question 5 - Based on the email address that has been auto filled, what recipient was this phishing email targeting?**

We can see that the email is already set in the web page as contact@securityblue.team.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/101c907e70eee18d6e0bc2d6a5502702db0bd36db3b63ca6c8a699b7d20e66fd7bb0f9045eda61fc9ee7e2f16a12.png)

---

**Question 6 - Right-click the web page within Chrome and select View Source. Press CTRL+A to select all of the text, then CTRL+C to copy it. Open up CyberChef from the folder on the Desktop and paste the text into the 'Input' box in the top right. Drag 'URL Decode' from the left-hand panel into the 'Recipe' tab to decode it. Search for "logo" - what is the filename of the Microsoft logo used?**

Putting the source code in CyberChef with the URL Decode operation, we can see the contents of the web page clearly.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/d3fc53e98f17fa780c059713beb26987f0ae003b2adf083c310fb979adbc92386afee777024a00bacf88379e6653.png)

Using CTRL+F we can search for ‘logo’ and find the URL and filename we need to answer this question.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/6aa78c1f8ee39f50fb0635ff44e6d7ef1542e2c44f6a79c27cb2d88d197376f5814a698aedffbdd1542e7d394049.png)

---

**Question 7 - Open Developer Tools (see instructions if you're unsure) and go to the Network tab. Enter in the password 'test' and click Sign in. Click on the off.php entry - what is the request URL being used to send the email and password to the web server?**

Opening Developer Tools then going to the Network tab, we can see any network activity on a website. Submitting the password ‘test’ will result in the following URL being visited on a malicious domain, which is how the attacker receives the credentials. Copying this value will give us the answer for the question. Notice how the email and password are in this URL!

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/a6c9593d2a579aff29564e66a7eea7edd12a7216687a75658e048207e017ccfc5848fdfcfb136c09934a8e6b4f9f.png)
# Lab) Phishing Response Challenge Solution

1. Phishing Analysis
2. Phishing Response Challenge
3. Lab) Phishing Response Challenge Solution

Complete

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/0d2d21b3c40fb10e2508d5a41df13718fe4a8bb4e19683c26f7e59d742a30158df0c7c758dae465487a419809029.PNG)

This lesson will be replaced with a video in the very near future, however, we wanted to provide a walkthrough as quickly as possible, so we're using a text lesson for now.

**Question 1 - Which of the 5 emails have you identified as being malicious?**

This is arguably the longest question to answer because it requires us to investigate all of the five provided emails and apply our analysis skills to identify which two are malicious.

**Email One**

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/5cb8417d54e79194392f474121e1e07feab414b1de9d3aa600240cf327ba725d346d1536ae6e12c43a16dfae9571.PNG)

It is immediately clear that this email is highly suspicious:

- The sending address is set as ‘auto-confirm.info-amazon.co.uk (where info-amazon.co.uk is the domain, not amazon.co.uk), but we can see it’s actually coming from [QPE77756@mun.ca](mailto:QPE77756@mun.ca) - this definitely isn't Amazon
- Formating/styling is inconsistent - emails from huge brands such as Amazon are styled well, and do not use varying fonts
- The email is not addressed to a specific person which is often seen in legitimate emails, instead it is addressed to a generic recipient ‘Amazon user’
- The email features poor and incorrect grammar such as ‘Your ID’ (should be your account), and ‘From Amazon Store’
- Has an obvious call-to-action button, enticing the user to click on the link for the ‘Help Page - Refund Form’ (emails do use legitimate call-to-actions, but this is also a part of phishing with URLs)

We've found our first malicious phishing email!

**Email Two**

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/b9319fd06f75f7fdf6405d20bf08efd2937d52c658ea7db35aaf492bfb46e72da74b67b821d00df0793ae13fa463.PNG)

If you thought this email was malicious, you may be rushing your analysis. Let's consider a few points:

- Email is spam-themed, trying to convince non-technical users that they are going to get a portion of someone's lottery winnings
- The email is not addressed directly to the recipient, suggesting it is being mass-mailed to a large list of people
- There is a URL in the body, however it is not hyperlinked. A quick Google search tells us that ‘thescottishsun[.]co[.]uk’ is a legitimate news site, and is not malicious
- The email provides an email address to contact that is different from the sender

Based on this information, this email is not malicious. It should be classed as spam/scam as it is trying to convince recipients to send personal details to a Gmail address, using the story behind a legitimate news article regarding lottery winners in Scotland.

**Email Three**

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/b84844779cdc76783986f513835bcb9197473bd5ba9132bf976d6e2fadbd8477b8bab720505755d8b28242344766.PNG)

Let's start by noting down some key parts of this email:

- The sender is a Gmail address, despite the email claiming to be from the UK's National Health Service
- The image used in the email is a generic stock image and doesn't show any NHS or UK Government branding to match the theme of the email
- The email is addressed to a generic recipient ‘Sir/Madam’
- The email is telling the recipient to open the attached file (call-to-action)
- A sense of urgency is created to generate an emotional response using the sentence ‘If you do not act soon, we will give your slot to someone else’ - this is trying to make people act quicker than they can think
- The attachment is named ‘MALICIOUS ATTACHMENT REMOVED - SBT.txt’. This is extremely unlikely to be the name of the real attachment - some Email Gateways have the ability to strip out and replace attachments to let recipients know it was malicious.

As the attachment is just a text file, we can open it without fear of malicious code execution.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/1ccc38b28b364a6b5a484fde960e81ac8f0437c1a8d584b863866e277a23ac9b74bd80d88937f4ac706f9ee75538.PNG)

This informs us that the attachment was indeed malicious, and was actually an executable disguised as a PDF using the double extension ‘.pdf.exe’.

Here's our second malicious email, giving us the answer of ‘1, 3’. Let's look at the final two emails anyway for practice!

**Email Four**

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/35e4cedda338d5a309a4939bd79cb8104300ee0e1a23dc25cb2fa81a4c6348e87c5e189ba5ee14f87689b2c77308.PNG)

Based on the sender, styling, theme, and purpose of this email, we can classify this as spam/newsletter. The email is not using a real call-to-action despite a number of hyperlinks. Further analysis of the links could be conducted using tools such as URL2PNG or WHOis and reputation checks on the domain, however over time you'll learn to understand what is suspicious, and what is just spam.

**Email Five**

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/9141d85f99567b8d4232dcea98291b204cf87b8e6e936e4ea15be50deb77694d1d4d716bba598003d6b78fec1487.PNG)

As with email four, we are seeing the same techniques being used. While parts of this email seem suspicious, such as the Reply-to address having the name set as ‘dfsdf’ and the subject line is misleading to individuals that aren't familiar with cryptocurrencies or investing, this is another spam email trying to convince people to sign up to begin trading cryptocurrencies, and is not inherently malicious - although it should be avoided!

---

**Question 2 - First Malicious Email: What is the sending address?**

Opening Email One in Sublime Text and searching for (CTRL+F) ‘From’ we can find the sending email address, which is contained within the <> symbols at the end of the line (everything before this is just a friendly name that can be set as anything, only the final part matters!)

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/25dd77632c48891c888d02f7ef0b7a48e13963257c2ab366985d1a05bb6046280e07870a2a6c3bcafe94d31aae01.PNG)

---

**Question 3 - First Malicious Email: What is the subject line?**

A few lines below, or by searching for ‘Subject’ we can find the subject line.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/afca1cbf49afe2b0abfa21f9e4da31562f3af9b2248c0087bc21ac5359131d816c2da1781f1fbed85a4ac5ae2f4a.PNG)

---

**Question 4 - First Malicious Email: Who are the recipients?**

Looking at line 42 we can see the email is being sent to jack.tractive@abcindustries.co.uk.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/0e790697804cb7953086a0414a80111d4a3eeeebefae20ec5ccfe2cbefc1b92d4a6c603ec420864529e798ee8a9b.PNG)

---

**Question 5 - First Malicious Email: What is the Reply-to address? (If not present, write "none")**

Searching for ‘reply’ or ‘reply-to’ gives us no results, so we will enter the answer as ‘none’.

---

**Question 6 - First Malicious Email: What is the date and time the email was sent? (Retrieve this via text editor!)**

Searching for ‘Date’ in our text editor will show us the timestamp of the email.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/d7b6629db846d1c5a6472ab23b3bf730090c250979349a39dbd7ecc78411f4986aa1f2717f619d5ce374bd15f50b.PNG)

---

**Question 7 - First Malicious Email: What is the sending server IP?**

Searching for the string ‘Sender’ we can see a number of references to the same IP address, including a mention of SPF checks that came back positive for this IP.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/718e4eba21d2cf2abda4a862ac858d61a1110bc183e4597661b54c02d8ddd5066aea6c2f61757d4c9d681f73768f.PNG)

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/cc66a8c5a28b0ce2f0e42f83d0278a2ec23d92e433ea018903bfbf5c45d79e29ea22efe1c0fe80f6ab7cf1a0c49b.PNG)

---

**Question 8 - First Malicious Email: What is the reverse DNS hostname of the sending server IP? (check email headers and/or a WHOis lookup)**

Searching for the sender IP 68.114.190.29 on [https://whois.domaintools.com](https://whois.domaintools.com/) doesn't show us a hostname, and states that the IP is owned by ‘United States Ashburn Charter Communications’. It seems that this IP is no longer owned by an individual company, so we won't be able to get the hostname from here. While IP ownership can change, we'll always have the original information preserved within the email file.

Searching for the IP in the text editor we find the following information, giving us the hostname of the sending server:

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/1657d5f76bc19ea420b46677f56e24fd8ac4ab9ae4ee488e7e025a0573a203c688ff5498368613ba818225144b5f.PNG)

---

**Question 9 - First Malicious Email: What is the full URL?**

The easiest way to do this is by right-clicking the URL in the email when viewed through an email client, because email files can contain a lot of http/https links, making it time-consuming to go through them to find the right one.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/ed7704bec2f81bb35f63a1e882bc614a8c075265c3bc71e752db9e4966b3c8dc68fef9ae3a20ae9c078c2983e4d1.PNG)

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/00ac2c0303da4239d91c4d1e57fe4c6661875ec2380880bf797a530750bcf832bb84df496ee8ed833543835a79c0.PNG)

Based on the formatting of the URL and the theme/intent of the email, this is very likely to be a credential harvester, where the email address on the fake Amazon login screen is being auto-filled (to make it seem more legitimate) by the email argument provided in the URL. This is speculation until we investigate further, but over time you will learn to understand attacks based on themes and techniques used.

---

**Question 10 - Second Malicious Email: What is the sending address?**

Opening the email in a text editor, we'll use CTRL+F to search for the ‘From’ property.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/3117e611026b04b26d419231f9db0e4cf902bafebb7ec5d5c6a1b3b3baebb42147c6d9fc8dd4ddd47ce71aae569f.PNG)

---

**Question 11 - Second Malicious Email: What is the subject line?**

Looking down a few lines or searching for ‘Subject’ will give us the value.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/fd3b4a23f1403c6f871f03a5a419cfbedb38bf8042008c592efb20bd415329c020c6f280d0346faad071b46d969d.PNG)

---

**Question 12 - Second Malicious Email: Who are the recipients?**

Searching for the ‘To’ property we can find one recipient listed.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/adfd097e87536c87820e83a418e578f3851b04b873fb0231b9a09e07c052778b849af8cf21babf71fa794f3277a7.PNG)

---

**Question 13 - Second Malicious Email: What is the Reply-to address? (If not present, write "none")**

Searching for ‘Reply’ or ‘Reply-to’ shows no results, so this email is not using a reply-to address to receive replies.

---

**Question 14 - Second Malicious Email: What is the date and time the email was sent? (Retrieve this via text editor!)**

Searching for ‘Date’ will give us the timestamp of the email.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/a87d53023e21951e49200d8e165f100b0afb620a5320b00c3d2c396e9b134ce7c5261cb6acf6d2a0b827cda862df.PNG)

---

**Question 15 - Second Malicious Email: What is the sending server IP?**

Searching for ‘Sender’ we can find the sending server's IP address.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/3a9ca66725855bf0e7822d62160eb1d64cd76b1d4af67c67911db65e8c2429c46cf91fb0e8bbdea6d722432422f0.PNG)

---

**Question 16 - Second Malicious Email:  What is the reverse DNS hostname of the sending IP? (check email headers and/or a WHOis lookup)**

Searching for the IP address on Domain Tools WHOis lookup, we can see the resolved host is a Gmail sending server, owned by Google.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/457a05adc27ddc55d3c90e6e0e1c3eb20a54e3e5b2cfb7914bee2bc95b5314a00018a3daa028274a97a7d35f9c1d.PNG)

---

**Question 17 - Second Malicious Email: What is the file name, including extension?**

Typically we will retrieve the filename and extension that is shown in the email client (but can also be found in a text editor by looking through the body content at the end of the file). In this scenario we have ‘removed’ the malicious file, which some email gateways can do. In the below screenshot you can see our dummy attachment can be found within the eml file itself.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/fb62874dd5491dc35445b738d60844ab9b583067ecc0f5e149b071b39648b67e5a7d3c23b48267b9bfa75aaf7f18.PNG)

Looking in the Thunderbird client we can see the attachment shown at the bottom of the windows (however most email clients like Outlook and Gmail will display attachments at the top of an email).

In this scenario, we need to submit the ‘real’ name of the attachment that was removed by our email gateway, which can be found within the text file attachment.

![](https://d2y9h8w1ydnujs.cloudfront.net/uploads/content/images/10d2476d5fdf85559b59d52056bccbd062660d93adb7ae0731757fba9e4d6696a3fd9d4d766f92770748b486edf7.PNG)

---

**Question 18 - Second Malicious Email: What is the SHA256 hash value of the file?**

If we were dealing with a real malicious attachment then we would want to download it within a virtual machine (that is only used for analysis and doesn't hold corporate data) and hash the file using PowerShell or Linux CLI (Get-FileHash vs sha256sum).

However in this fictional scenario, we're provided with the SHA256 hash, as we no longer have access to the real attachment (shown in the screenshot above).