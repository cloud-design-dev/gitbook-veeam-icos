---
description: >-
  This will guide you through what needs to be done in the Veeam Backup and Replication console to configure ICOS as scale out storage.
---

## Add Scale out storage
Need *Add scale out* image here 
Scale out repo name 
https://dsc.cloud/quickshare/Shared-Image-2020-07-24-10-03-55.png

Performance Tier > Add > Select newly created repo 
https://dsc.cloud/quickshare/Shared-Image-2020-07-24-10-04-47.png

Select **Extend scale-out with object storage** and click the **Add** button  
https://dsc.cloud/quickshare/Shared-Image-2020-07-24-10-06-01.png

Select IBM COS 
https://dsc.cloud/quickshare/Shared-Image-2020-07-24-10-07-19.png

 - Add endpoint and credentials 
![Add endpoint](https://dsc.cloud/quickshare/Shared-Image-2020-07-24-10-09-49.png)
The bucket that I am going to be offloading backups to was created as a us-south regional bucket. As such I am adding the private us-south endpoint `s3.private.us-south.cloud-object-storage.appdomain.cloud`. To see all available endpoints see [Object Storage Endpoints](https://cloud.ibm.com/docs/cloud-object-storage?topic=cloud-object-storage-endpoints).

Next to credentials click Add. This is where you will add the HMAC keys that we generated previously. With those credentials added click Next. You will now select the COS bucket to use. Under Folder selection click **Browse** and click **Add Folder** to create a new directory within the bucket. Click **Next** to get to the Review page. If everything looks good click **Finish**. 

You are now dropped back in to the Scale out repository wizard. You can now set the **age out** policy for backups in this backup repository. Make sure the *Move backups to object storage* checkbox is checked and set your policy. The default is 30 days.  

![](https://dsc.cloud/quickshare/Shared-Image-2020-07-24-10-26-45.png)

Click **Apply** and review the creation details. Click **Finish**.

Make sure to select your newly created backup repository when creating new backup jobs to ensure that your backup roll-off operations run as expected. 

![Targeting new backup repository](https://dsc.cloud/quickshare/Shared-Image-2020-07-24-10-34-11.png)
