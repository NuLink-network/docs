# NuLink Agent Use Case
We provide a third-party demo example, a private file-sharing platform called [File Transfer](https://agent-integration-demo.nulink.org). 
The business process is as follows: users can freely upload and encrypt their own files on the platform, and other users can apply for the files they are interested in. Once the author approves the application, the applicant can download and view the encrypted file. Due to the privacy and security considerations of the files, all operations of this platform must be conducted through on-chain contracts. Next, we will focus on introducing the business scenario of the application and Agent integration.

![File Transfer Demo](../miscellaneous/img/agent/connect.png)

This application must be authorized to log in to the Agent account to access and operate normally. Click "Agent" in the upper right corner to call up the Agnet authorization page.

## Agent Authorization Login

Before formal authorization, you need to enter the account password and then click "confirm" to start the authorization.

![Enter Password](../miscellaneous/img/agent/enter_password.png)

As shown in the figure below, the authorization page will display the address of the request source and my Agent account address. 
Click "Confirm," and the page will automatically jump back to the third-party application page.

![Connect NuLink Agent](../miscellaneous/img/agent/confirm.png)

The figure below shows the File Transfer page of the third-party application, and it is logged in with the Agent's current account. If you have not uploaded any files, please click "Upload file" to upload files first.

![File Transfer](../miscellaneous/img/agent/filetransfer.png)

## File Upload
Click "Upload file" to upload. You can drag and drop the file into the box to upload. Also click button "UPLOAD FILE" and select files through dialog is supported.
NuLink Agent supports all file formats, e.g. JPG, PNG, GIF, MP4, DOC, XLS, PDF, etc.

**Notice: the file size can not exceed 5M bytes.**

![File Upload](../miscellaneous/img/agent/upload.png)

After selected file, here show the file list to be uploaded, confirm and upload these files.

![List of Uploaded Files](../miscellaneous/img/agent/upload_list.png)

## File Application

The figure below shows the file details page, and clicking "Request the file" can apply for the file. Enter the number of days you want to apply for and click "Submit."

![Request File](../miscellaneous/img/agent/request_file.png)

![Request Submit](../miscellaneous/img/agent/request_submit.png)

Next, the Agent will be called up for file application authorization, which includes the relevant information of the file: file name, owner address, requester address, source URL, and requested days. Click "Confirm" to authorize.

![Request Confirm](../miscellaneous/img/agent/request.png)

After the authorization is completed, the page will jump back to the third-party application page, and the file status will change to "pending."

![Rquest Pending](../miscellaneous/img/agent/request_pending.png)

## File Approval

The figure below shows the list of applications received by the author.

![Request Review](../miscellaneous/img/agent/request_review.png)

* Single File Approval
  Click on the "Review request" button next to the file in the list page to view the application details. 
If everything looks fine, click "Submit."


![Request Review Submit](../miscellaneous/img/agent/request_reviewed.png)

* Batch File Approval
Select multiple files that you want to approve, then click the "Review request" button. 
You can view the application details for different files by clicking the "Previous" and "Next" buttons. 
If everything looks fine, click "Submit."

![Request Review Submit](../miscellaneous/img/agent/request_reviewed_batch.png)

Then the Agent authorization page will be displayed, showing relevant information about the application, including the addresses of the parties involved, the source URL, the method being called, gas fees, and service fees. 
Click "Confirm" to complete the approval process after making the payment.


After reviewing the application details, click "Submit."

![Request Approve](../miscellaneous/img/agent/request_confirm.png)

After the approval is completed, the page will jump back to the third-party application page, and the file status will change to "Approved."

![Request Approved](../miscellaneous/img/agent/request_approved.png)

## File Download

Applicants revisiting the file details page of their application will see that the application has been approved and they can now download the file.

![Approved File Info](../miscellaneous/img/agent/request_details.png)

By clicking "Download now", as it is an encrypted file, the Agent authorization decryption page will be prompted first. The relevant information of the request can be seen, including File name, Owner's address, Applicant's address, and Source URL. 
Clicking "Confirm" will initiate the decryption authorization.

![Authorization Request](../miscellaneous/img/agent/request_auth.png)


Once decryption is complete, a prompt will appear asking whether to proceed with the download. Clicking "Confirm" will redirect to a third-party page for downloading.

![File Download Confirm](../miscellaneous/img/agent/request_download.png)

The image below shows the redirected third-party page, as indicated in the bottom left corner, where the file has been successfully downloaded to the local machine via the browser.

![The Main](../miscellaneous/img/agent/request_mainpage.png)


Clicking on the file will display its contents, as shown in the image below.

![File Image](../miscellaneous/img/agent/request_img.png)

## Multi-Network Switching

Currently, Agent supports two networks: Horus (BSC Testnet) and Conflux eSpace Testnet. 
In the future, it will also support more networks.

![File Image](../miscellaneous/img/agent/network_switching.png)

When switching to another network, a pop-up window will provide a prompt.

![File Image](../miscellaneous/img/agent/network_switch_info.png)

After switching the network, if any operation requiring Agent authorization is needed, the Agent's network will be checked to ensure it matches the network of the third-party application. 
If they don't match, a pop-up window will prompt the user to switch Agent's network. Otherwise, the authorization for the related operation cannot proceed.

![File Image](../miscellaneous/img/agent/network_switch_confirm.png)