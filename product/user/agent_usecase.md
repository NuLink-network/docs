# DApp example

Welcome to the NuLink Agent SDK's third-party demonstration case, showcasing a private file-sharing platform known as [File Transfer](https://agent-integration-demo.nulink.org). This platform ensures privacy and security by encrypting all files uploaded and shared among users.

The workflow of File Transfer is simple and efficient:
* Users can freely upload and encrypt their files on the platform. 
* Other users can apply for files they are interested in. 
* Once the author approves the application, the applicant can download and view the encrypted files. 

To maintain the utmost privacy and security of files, all operations within this platform are executed through on-chain contracts.

In the following sections, we will dive deeper into the detailed usage of this application and its seamless integration with the NuLink Agent.

This application requires authorization to log into the Agent account for normal access and operation.

![File Transfer Demo](../../miscellaneous/img/agent/connect.png)

Click `Agent` in the top right corner to call up the Agent authorization page.

## Agent Authorization Login

Before official authorization, enter your account password and click `confirm` to start the authorization.

![Enter Password](../../miscellaneous/img/agent/enter_password.png)

As shown in the authorization page below, it displays the request source's address and my Agent account address.

![Connect NuLink Agent](../../miscellaneous/img/agent/confirm.png)

Click `Confirm` and the page will automatically return to the third-party application page.

The image below shows the third-party application 'File Transfer' page in the logged-in state, with the account being the currently logged-in Agent account. 

![File Transfer](../../miscellaneous/img/agent/filetransfer.png)

If you have not uploaded any files, please click `Upload File` first.

## File Upload -> Single File Upload

After selecting the local file to upload, you will be redirected to the Agent page to encrypt the file first, as shown below.

**Notice: the file size can not exceed 5M bytes.**

![File Upload](../../miscellaneous/img/agent/upload.png)

Click `NEXT` to start encryption.

After encryption, you will enter the file upload page, as shown below. 

![File Upload Confirm](../../miscellaneous/img/agent/upload_confirm.png)

Click `CONFIRM` to start the file upload.

After successful file upload, the following interface will be displayed:

![File Upload Success](../../miscellaneous/img/agent/uploaded.png)

## File Upload -> Multiple File Batch Upload

After selecting the local files to upload, you will be redirected to the Agent page to encrypt the files first, as shown below.

![Multiple Files Upload](../../miscellaneous/img/agent/upload_batch.png)

Click the `Left Arrow` or `Right Arrow` buttons on the progress bar to switch and view each file's details. 
And click `NEXT` to start encryption.

After encryption, you will enter the file upload page, as shown below.

![Multiple Files Upload Confirm](../../miscellaneous/img/agent/upload_batch_confirm.png)

Click `CONFIRM` to start the file upload.

After successful file upload, the following interface will be displayed:

![Multiple Files Upload Success](../../miscellaneous/img/agent/upload_list.png)

## File Application

The figure below shows the file details page, and clicking "Request the file" can apply for the file. Enter the number of days you want to apply for and click "Submit."

The image below is the file detail page. 
Click `Request the file` to apply for the file.

![Request File](../../miscellaneous/img/agent/request_file.png)

Enter the desired number of days and click `Submit`.

![Request Submit](../../miscellaneous/img/agent/request_submit.png)

Next, Agent will be called up for file application authorization, and the request details are shown below.

![Request Confirm](../../miscellaneous/img/agent/request.png)

Click `CONFIRM` to apply.

After completing the authorization application, you will return to the third-party application page, 
and the file status will change to `pending`.

![Rquest Pending](../../miscellaneous/img/agent/request_pending.png)

## File Approval

The image below is the author's list page of received applications.

![Request Review](../../miscellaneous/img/agent/request_review.png)

* Single File Approval

Click `Review request` button next to the file list to view the application details, and click `Submit` if everything is fine.

![Request Review Submit](../../miscellaneous/img/agent/request_reviewed.png)

* Multiple File Batch Approval
Select multiple files you wish to apply for, then click `Review request` button.
View the application details of the files, click the `Previous` and `Next` buttons to view different file application details, and click `Submit` if everything is fine.

![Request Review Submit](../../miscellaneous/img/agent/request_reviewed_batch.png)

Then the Agent authorization page will be called up, and the details of the approval request are shown below. 
Click `APPROVE` to proceed with the approval.

![Request Approve](../../miscellaneous/img/agent/request_confirm.png)

After completing the approval, you will return to the third-party application page, and the file status will change to `Approved`.

![Request Approved](../../miscellaneous/img/agent/request_approved.png)

## File Download

When the applicant re-enters the file details page, they will see that their request has been approved and they can now download the file.

![Approved File Info](../../miscellaneous/img/agent/request_details.png)

Click `Download now`.
Since it is an encrypted file, the encrypted file will be downloaded first, click `NEXT`,
as shown in the image below, 

![Authorization Request](../../miscellaneous/img/agent/request_auth.png)

further decrypt the file by clicking `Confirm`.

![File Decryption Confirm](../../miscellaneous/img/agent/request_download.png)

A message indicating successful decryption will appear, and after 1 second, you will automatically return to the third-party application page.

![File Decrypted](../../miscellaneous/img/agent/request_decryption.png)

The image below shows the returned third-party page, and as shown in the lower left corner, the file has been downloaded to the local machine through the browser.

![The Main](../../miscellaneous/img/agent/request_mainpage.png)

Click on the file to view its content, as shown below.

![File Image](../../miscellaneous/img/agent/request_img.png)

## Storage Capacity
To meet users' needs for encrypted file storage capacity, 
Agent offers a storage capacity recharge plan for users, as shown in the image below.

![Storage Upgrade](../../miscellaneous/img/agent/storage_status.png)

![Storage Plan Chose](../../miscellaneous/img/agent/storage_plan.png)


