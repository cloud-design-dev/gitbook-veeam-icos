---
description: >-
  This will guide you through what needs to be done within the Veeam Backup and Replication console to add a new backup repository tied to our newly format drive.
---

From the Veeam Backup and Replication console click **Backup Infrastructure** and then right click on **Backup Repositories** and select **Add backup repository** to launch the Repository creation wizard.

![Add backup repository wizard]https://dsc.cloud/quickshare/add-backup-repository.png

Select *Direct Attached Storage* in the first dialog box and *Microsoft Windows* in the second. Give the backup repository a name and click **Next**  
![](https://dsc.cloud/quickshare/Shared-Image-2020-07-24-09-50-40.png)

Select your local server and click Populate to list locally attached available drives. In my case I select `F` and select **Next**  
![Select Repository Drive](https://dsc.cloud/quickshare/select-repo-drive.png)

For both the *Repository* and *Mount Server* dialog boxes you can accept the defaults and just click **Next**  

On the review dialog box make sure to leave *Import existing backups automatically* unchecked since we're starting off with a fresh set of backup job. Once you're satisfied everything looks correct click **Apply**.  
![Create repository](https://dsc.cloud/quickshare/Shared-Image-2020-07-24-09-55-55.png)

{% hint style="info" %}
 When you see a dialog box asking *Change the configuration backup location to the newly created repository?* select **No**. If you select **Yes** the backup repository becomes un-usable for Scale out ICOS storage.
{% endhint %}

