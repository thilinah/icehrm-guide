---
description: How to use AWS S3 for IceHrm file system
---

# AWS S3 File Storage

With IceHrm you can use Amazon S3 as your file system. In order to do that you need to first create an S3 bucket for icehrm. For this example, let's assume the name you are selecting for your s3 bucket is **icehrmpro-test.**

### **Configuration**

1. Goto AWS S3 console and create the bucket

![Create S3 Bucket](../.gitbook/assets/screenshot-2021-06-06-at-11.46.13.png)

2\. Make sure the bucket access is public. This doesn't mean the file stored here by IceHrm is public. A secure has is needed every time a file is accessed.

![](../.gitbook/assets/screenshot-2021-06-06-at-12.08.05.png)

3\. Create an IAM user with access to S3. (You may use restrict permission for this user only to a selected bucket if needed)

![](../.gitbook/assets/screenshot-2021-06-06-at-11.49.30.png)

![](../.gitbook/assets/screenshot-2021-06-06-at-11.52.36.png)

4\. Update IceHrm Settings Accordingly Under System->Settings

![](../.gitbook/assets/screenshot-2021-06-06-at-12.53.04.png)

5\. Set "**System: AWS Region**" setting under **System->Settings correctly**.

### Testing

* Update a file for an employee via the documents module
* Check if you can download the file and make sure it's being downloaded via S3 URL
* If successful upload all the files in icehrm/app/data to s3 bucket and make sure file permissions are not set to public
* Try downloading an old file

{% hint style="warning" %}
Test and make sure your S3 files can not be accessed publicly.
{% endhint %}
