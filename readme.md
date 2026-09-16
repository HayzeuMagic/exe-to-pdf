<div align="center">
  <img src="https://github.com/user-attachments/assets/e4d90e60-ee23-4e28-b9c1-ab35e68fed13" alt="Rivan Cyber Training Institute Logo" width="200">

  <h1>RIVAN CYBER TRAINING INSTITUTE</h1>
  <h2>D3 Pentest Lab</h2>
</div>

<hr>

## 📌 Lab Resources

**Demo Video:**
https://drive.google.com/file/d/1hBlqFhoAzBjNp-m3VZchQ6XjZZgXFXi0/view?usp=sharing

**Downloadable Files:**
https://drive.google.com/drive/folders/1TeWFy63-GBd0ItOfedSpzVJcegvqyxQN?usp=sharing

---


# **BEFORE WE START MAKE SURE TO EXTRACT THE DOWNLOADED ZIP FILE TO (C:) DRIVE**

1.Go to Local Disk (C:) and create a folder named `exe-to-pdf` 

2.Extract the zipped file and to the fold we just created

<img width="607" height="441" alt="image" src="https://github.com/user-attachments/assets/339a1d18-4bc5-4cb6-9dab-200f6367bafe" />

3. Double check that the folder should be in Local Disk (C:)/exe-to-pdf
   
<img width="843" height="520" alt="image" src="https://github.com/user-attachments/assets/76f90840-ecaa-46ea-92cd-76c4fa7780b9" />

# Step 1: Open VMware

This laboratory uses VMware to run the provided Kali Linux virtual machine.

1. On your Windows PC, press the **Windows key** on your keyboard.

2. Type:

   ```text
   VMware
   ```

3. Open **VMware Workstation** from the search results.
<img width="820" height="287" alt="image" src="https://github.com/user-attachments/assets/aef36bf2-6420-459b-bb5a-ef2af34896fb" />

---

# Step 2: Open the `_D3PentestVM` Virtual Machine

1. In VMware, click **File** in the top-left corner.

2. Select **Open**.
<img width="279" height="270" alt="image" src="https://github.com/user-attachments/assets/382c42d0-3acb-4a00-98de-94a83b5993c9" />

3. Navigate to the `_RivanVMs` folder.

4. The folder may be located on either your **C:** or **D:** drive, depending on where the virtual machines were stored.

5. Locate the following virtual machine:

   ```text
   _D3PentestVM
   ```

6. Open the `.vmx` file associated with the virtual machine.

   Example:

   ```text
   _D3PentestVM.vmx
   ```
<img width="951" height="555" alt="image" src="https://github.com/user-attachments/assets/0ba9829e-f4d7-4371-b7e6-aa0aff717b76" />

7. VMware should now display `_D3PentestVM` in the virtual machine list.

---

# Step 3: Configure the Virtual Machine Network

# **WARNING: Make sure that the Virtual Machine is powered off!**
Before starting the virtual machine, verify that its network adapter is configured correctly.

1. Select `_D3PentestVM` in VMware.

2. Click **Edit virtual machine settings**.
   
<img width="837" height="580" alt="image" src="https://github.com/user-attachments/assets/0b3becc6-b6a9-4f7e-a927-313319bbd519" />

3. In the **Hardware** tab, select **Network Adapter**.
   
4. Make sure the network connection is set to:

   ```text
   NAT
   ```

<img width="746" height="724" alt="image" src="https://github.com/user-attachments/assets/aa1c2673-b203-4405-9e14-0c3f3755e226" />

### Why NAT?

NAT allows the Kali Linux virtual machine to access the network through the host computer while keeping the virtual machine separated from the physical network.

---

# Step 4: Enable VMware Shared Folders

Shared Folders allow you to access files stored on your Windows computer from inside the Kali Linux virtual machine.

### On VMware:

1. Click the **Options** tab.

2. Select **Shared Folders** from the left-side menu.

<img width="756" height="723" alt="image" src="https://github.com/user-attachments/assets/b5c16636-bca7-4e06-9cb2-583680ab282f" />

3. Select:

   ```text
   Always enabled
   ```
 <img width="747" height="689" alt="image" src="https://github.com/user-attachments/assets/a5919461-4852-49cb-9665-380e694bde9c" />


4. Click **Add...**.
<img width="747" height="689" alt="image" src="https://github.com/user-attachments/assets/0e1a0196-c7c6-49a2-90c3-6f58fb2e05f9" />


5. The **Add Shared Folder Wizard** will appear.

6. Click **Next**.
<img width="747" height="720" alt="image" src="https://github.com/user-attachments/assets/84a7d479-0cd8-4540-806e-461d190fb822" />


7. Click **Browse...**.
<img width="417" height="373" alt="image" src="https://github.com/user-attachments/assets/c86d6f68-095a-4381-a709-78cbfbbf331b" />

8. Select This PC > Local Disk (C:) > exe to pdf

<img width="315" height="365" alt="image" src="https://github.com/user-attachments/assets/1b27df87-5f84-4bb6-8dfd-342c24a2335e" />


9. Click **Next**.

<img width="426" height="377" alt="image" src="https://github.com/user-attachments/assets/239871ff-6eec-421b-9e5d-22fba96ff4d0" />

10. Confirm the shared-folder settings.
    
<img width="419" height="370" alt="image" src="https://github.com/user-attachments/assets/40290bc0-3930-41cb-91a7-fc96a38b32df" />

11. Click **Finish**.

12. Double Check, make sure your shared files looks like this
<img width="743" height="720" alt="image" src="https://github.com/user-attachments/assets/c820235b-38e8-4602-a151-b4c6b82402d1" />


### Example

If your files are located in:

```text
C:\exe-to-pdf
```

you can select `C:\exe-to-pdf` as the shared folder.

The folder name used by VMware will be needed in the Kali Linux mounting command later.

---

# Step 5: Power On the Virtual Machine

1. Select `_D3PentestVM`.

2. Click **Power on this virtual machine**.

<img width="1322" height="774" alt="image" src="https://github.com/user-attachments/assets/12279401-b0ac-427d-a2f1-5cc64e201ddd" />


3. Wait for the virtual machine to boot.

4. If VMware displays a message asking whether the virtual machine was **moved or copied**, select:

   ```text
   I copied it
   ```

6. If the virtual machine displays a blue boot screen requiring keyboard input, click inside the VMware window and press **Enter** when prompted.
   If you miss the prompt, the VM may continue to a different screen or appear to remain black. If this happens, wait briefly or restart the VM if necessary.

<img width="1327" height="789" alt="image" src="https://github.com/user-attachments/assets/3be5b56d-74b8-4dc4-963d-52ca211eafad" />


> **Important:** Do not close VMware while the virtual machine is running.

---

# Step 6: Log In to Kali Linux

Once the Kali Linux login screen appears:

1. Click inside the virtual machine window so that your keyboard and mouse are captured by VMware.

2. Select the Kali Linux login screen.

3. Enter the following credentials:

<img width="1270" height="782" alt="image" src="https://github.com/user-attachments/assets/cbd75247-d15a-4f50-87be-e46d14f6a502" />

   **Username:**

   ```text
   kali
   ```

   **Password:**

   ```text
   kali
   ```

4. Press **Enter**.

5. Wait for the Kali Linux desktop to load.

---

# Step 7: Mount the Shared Folder in Kali Linux

After logging into Kali Linux, open the **Terminal**.
<img width="1278" height="819" alt="image" src="https://github.com/user-attachments/assets/f00ff5c6-4bca-4b73-b244-4a1575b237a3" />

The shared folder created in VMware must be mounted before you can access the Windows files from Kali.

### 7.1 Create the Mount Point

Run:

```bash
sudo mkdir -p /mnt/hgfs/
```

When prompted for the password, enter:

```text
kali
```
<img width="641" height="507" alt="image" src="https://github.com/user-attachments/assets/232c94b3-cad7-4d7a-9b3b-4e7116fb6667" />


> **Note:** When entering a Linux password in the terminal, the characters may not appear on screen. This is normal. Type the password and press **Enter**.

---

### 7.2 Mount the VMware Shared Folder

Use the following command:

```bash
sudo vmhgfs-fuse .host:/exe-to-pdf /mnt/hgfs -o allow_other
```
<img width="635" height="515" alt="image" src="https://github.com/user-attachments/assets/a6f7b555-553c-4826-a1cb-3283d7b94336" />

### 7.3 Check the Mounted Folder

After mounting the folder, run:

```bash
ls /mnt/hgfs/
```
<img width="635" height="503" alt="image" src="https://github.com/user-attachments/assets/b6b9835b-5aa9-438e-a0ef-bb7d5f3ce0b4" />

You should see the shared folder and its contents.

---

# Step 8: Extract a PDF Icon Using Resource Hacker

This step is performed on the **Windows host computer**, not inside Kali Linux.

The purpose of this step is to extract an icon resource from Microsoft Edge and save it as an `.ico` file for use in the laboratory.

### 8.1 Open Resource Hacker

1. On your Windows PC, open **Resource Hacker**.
2. Click **File**.
3. Select **Open**.
<img width="778" height="425" alt="image" src="https://github.com/user-attachments/assets/13cad68e-c3d8-4749-8d49-4ad8075466fb" />

5. Navigate to the location of the Microsoft Edge executable. It should be in your downloaded folder in C:/exe-to-pdf
7. Select:
```text
msedge.exe
```
6. Click **Open**.
<img width="1013" height="525" alt="image" src="https://github.com/user-attachments/assets/bb1317e2-5db6-4d67-8dc5-18a344c14445" />

---

### 8.2 Locate the PDF Icon Resource

After opening `msedge.exe`, Resource Hacker will display the executable's resources in the left-side panel.

1. Look for:

   ```text
   Icon Group
   ```

2. Expand **Icon Group** if necessary.

3. Locate:

   ```text
   IDR_X007_PDF_DOC
   ```

4. Right-click:

   ```text
   IDR_X007_PDF_DOC
   ```
<img width="774" height="421" alt="image" src="https://github.com/user-attachments/assets/72cacee5-5709-438a-a11d-da1b89cd09d2" />

5. Select the option to **Save [Icon Group] resource** / save the icon resource.
<img width="491" height="150" alt="image" src="https://github.com/user-attachments/assets/ef5909b6-0352-46aa-9dcb-ae72057e64b6" />

6. Save the resource as an `.ico` file.

For example:

```text
IDR_X007_PDF_DOC.ico
```

---

# Step 9: Change the `1mb.exe` Icon

This step is also performed on the **Windows host computer** using Resource Hacker.

The objective is to replace the existing icon of the provided laboratory executable with the extracted PDF icon.

### 9.1 Open `1mb.exe`

1. Open **Resource Hacker**.
2. Click **File**.
3. Select **Open**.
4. Locate:

```text
1mb.exe
```

5. Click **Open**.
<img width="870" height="482" alt="image" src="https://github.com/user-attachments/assets/60a19081-4a35-4041-bc1d-c8ef72a43d58" />

---

### 9.2 Add the PDF Icon Resource

1. In Resource Hacker, click  **Add binary or image resource**:
<img width="777" height="392" alt="image" src="https://github.com/user-attachments/assets/222fa94a-0c41-442c-a606-49d25dd9918d" />

2. Select:
<img width="244" height="256" alt="image" src="https://github.com/user-attachments/assets/c381c0d9-bd7d-4bd3-8797-046a23c174bf" />

3. Browse to the previously extracted:

   ```text
   IDR_X007_PDF_DOC.ico
   ```
4. Select the `.ico` file.
<img width="1010" height="522" alt="image" src="https://github.com/user-attachments/assets/8a6bd5a0-f5b7-44fa-8b78-8c78275f2ae0" />

5. Click Add Resource
<img width="246" height="268" alt="image" src="https://github.com/user-attachments/assets/9dcee90c-4e91-4de9-b6b7-2cef2754ed50" />

6. Click file and save as.
7. Save it in the same folder C:/exe-to-pdf
8. It will prompt that the file already exists, just click replace.
<img width="772" height="393" alt="image" src="https://github.com/user-attachments/assets/7a26d8e8-aeec-4e63-a9fe-5efd35f1e50c" />

9. Verify that the icon of 1mb.exe should show up as a pdf icon in your file explorer.
<img width="366" height="135" alt="image" src="https://github.com/user-attachments/assets/67a0a8a4-13b4-4b9d-860c-fd27a79ecd06" />

# Step 10: Reverse the Right-to-Left Override

This step demonstrates how a filename can contain a **Right-to-Left Override (RLO)** Unicode control character.

The RLO character can affect how characters in a filename are visually displayed. This is relevant to cybersecurity because filenames can sometimes be made visually misleading.

### 10.1 Open the Instructions in Kali Linux

1. Return to your **Kali Linux virtual machine**.
2. Locate:

```text
how-to-reverse.txt
```

It should be under File System > mnt > hgfs 
<img width="1276" height="791" alt="image" src="https://github.com/user-attachments/assets/320b9d5b-241e-417b-9acf-17a33ff71d74" />
<img width="643" height="680" alt="image" src="https://github.com/user-attachments/assets/e897781b-f571-402f-a579-b003f2a7cb75" />
<img width="639" height="635" alt="image" src="https://github.com/user-attachments/assets/586c7eef-dde2-4d37-8567-fe4094ad764c" />


3. Open the file using a text editor.

For example:

```bash
cat how-to-reverse.txt
```
<img width="660" height="568" alt="image" src="https://github.com/user-attachments/assets/b645f5c5-7332-4b1e-bfdd-e2d0f533aaab" />
<img width="766" height="413" alt="image" src="https://github.com/user-attachments/assets/a5f19c59-7565-4e69-9de2-4b3b63798684" />

If you get confused at this point, please watch the video demo at the top of this documentation and follow the steps there.

---

### 10.2 Rename the Laboratory File

The intended laboratory filename is:

```text
high-level-complexe.pdf
```

1. Go back to the hgfs folder and right click 1mb.exe
<img width="684" height="419" alt="image" src="https://github.com/user-attachments/assets/f4f39c5f-e5b1-4503-8a2b-9e8cd9581700" />

2. Select properties and rename it from there
3. Erase all text and type
   'high-level-compl -> ctrl + shift -> U202E -> fdp.exe'
<img width="529" height="511" alt="image" src="https://github.com/user-attachments/assets/04fded9e-873f-48ca-81ad-0e9d57699877" />
4. Make sure it you're not changing the actual file into a .pdf file. We're just using Right to Left Override
 **Important:** A file's displayed extension and icon do not change what the file actually is. An executable remains an executable even if its filename or icon is made to appear like a PDF.

<img width="529" height="516" alt="image" src="https://github.com/user-attachments/assets/2bdc2a2c-2544-4da2-af73-73cb7c17a767" />

5. Double check in your Windows File Explorer, it should look like a .pdf file with the pdf icon
<img width="536" height="305" alt="image" src="https://github.com/user-attachments/assets/8dddd037-7e0a-4694-8a6a-90455bbe7363" />

---



<div align="center">

### RIVAN CYBER TRAINING INSTITUTE

**Cybersecurity Laboratory — D3 Pentest**

</div>
