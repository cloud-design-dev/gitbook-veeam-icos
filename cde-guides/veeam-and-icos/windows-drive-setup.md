---
description: >-
  This will guide you through what needs to be done on the Veeam Windows Servers in order to use our secondary drive for Veeam.
---

# Windows Server Manager
Upon initial login to Windows server you should see Server Manager. If not then launch Server Manager and from the left hand navigation select:
 - *File and Storage Services* 
 - *Disks*
 - *the drive we want to use as our new Veeam Backup Repository*

![Select second drive](https://dsc.cloud/quickshare/select-second-drive.png)

In the Volumes view click on **Tasks** and select *New Volume*.

![New Volume](https://dsc.cloud/quickshare/volume-tasks-new-volume.png)

This will start the new Volume Wizard. Under *Server and Disk* select your local server and the drive where this volume will be created. Click **Next**

![Select server and drive](https://dsc.cloud/quickshare/server-and-disks.png)

For both the **Size** and **Drive Letter** selections you can simply click Next as we are leaving these as default. 

When it comes the filesystem we will want to select *ReFS* for the *File System* and *64K* for the *Allocation unit size* and then click **Next**. After you have reviewed the volume creation details click **Create** to provision the volume.

![File System Settings](https://dsc.cloud/quickshare/file-system-settings.png)

The drive is now ready to be used with Veeam. Go to [Adding New Veeam Backup Repository](./add-veeam-backup-repo.md)
