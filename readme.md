<div align="center">
  <img src="https://github.com/user-attachments/assets/e4d90e60-ee23-4e28-b9c1-ab35e68fed13" alt="Rivan Cyber Training Institute Logo" width="200">
  <h1>RIVAN CYBER TRAINING INSTITUTE</h1>
</div>

<hr>

demo video: https://drive.google.com/file/d/1hBlqFhoAzBjNp-m3VZchQ6XjZZgXFXi0/view?usp=sharing

downloadables: https://drive.google.com/drive/folders/1TeWFy63-GBd0ItOfedSpzVJcegvqyxQN?usp=sharing

# Step 1: Opening VMware
* Open the VMware app on your PC, press ⊞ Windows key and type "VMware"

# Step 2: Opening the _D3Pentest VMware File
* Under the File button, click Open
* Under the _RivanVMs folder on the D: Drive or C: Drive, find _D3PentestVM and open the .vmx file

<hr>

# Step 3: Editing Virtual Machine Settings
* Click "Edit virtual machine settings"
* Make sure the Network Adapter is set to NAT

<hr>

# Step 4: Enabling Shared Folders
* Right-click _D3PentestVM, then click Settings at the top
* Go to the Options tab > Shared Folders
* Select "Always enabled"
* Click Add > Next > Browse > locate the shared folder on your host machine > Next > Finish > OK

<hr>

# Step 5: Powering On the Virtual Machine
* Click "Power on this virtual machine"
* If prompted, click "I copied it"

<hr>

# Step 6: Accessing Kali Linux
* Click inside the virtual machine and press Enter once you see the blue screen — do this quickly or you will get a black screen
* Both username and password are "kali"

<hr>

# Step 7: Mounting the Shared Folder in Kali Linux
* Open the terminal and create the mount point
```bash
sudo mkdir -p /mnt/hgfs/
```
* When prompted for a password, enter "kali"
* Mount the shared folder from Windows into Kali Linux
```bash
sudo vmhgfs-fuse .host:/<shared-folder-name> /mnt/hgfs -o allow_other
```


# Step 8: Resource Hacker
* Open Resource Hacker on your Windows PC
* Click File and Open 1mb.exe
* Click Add binary or image resource
* Select IDR_X007_PDF_DOC.ico
* Then File and Save

# Step 9: How to Reverse Right to Left Override

 * Go back to kali linux open how-to-reverse.txt
 * Rename 1mb.exe to: high-level-complexe.pdf





