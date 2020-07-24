---
description: >-
  This will guide you through what needs to be done on the IBM Cloud side to
  allow Veeam to offload backups in to our Object Storage Bucket.
---

# IBM Cloud Pre-Work

## Launch IBM Cloud Shell

Launch [Cloud Shell](https://cloud.ibm.com/docs/cloud-shell?topic=cloud-shell-getting-started) to run through the following steps. The icon can be found in the upper right navigation bar in the cloud portal.

![Launch Cloud Shell](https://dsc.cloud/quickshare/Shared-Image-2020-07-24-11-02-05.png)

## Finding Your Cloud Object Storage Instance ID

We will use the `resource service-instance` operator to get our Cloud Object Storage instance id \(GUID\). Use the handy [jq](https://stedolan.github.io/jq/) utility to only return the GUID. 

```bash
$ ibmcloud resource service-instance <name-of-icos-instance> --output json | jq -r '.[].guid'
```

{% hint style="info" %}
 You will use the value returned by the above command in another command. Please note it. 
{% endhint %}

### Create a Service ID

We will create a service ID to interact with our ICOS bucket. A service ID identifies a service or application similar to how a user ID identifies a user. We can assign specific access policies to the service ID that restrict permissions for using specific services. 

```bash
ibmcloud iam service-id-create <name-of-your-service-id> --description "Service ID for Veeam Scale out repository"
```



