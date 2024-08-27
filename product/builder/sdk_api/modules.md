[NuLink SDK - v0.5.31](README.md) / Modules

# NuLink SDK - v0.5.31

## Table of contents

### Enumerations

- [DataType](enums/DataType.md)
- [DataCategory](enums/DataCategory.md)

### Classes

- [Strategy](classes/Strategy.md)
- [Account](classes/Account.md)
- [AccountManager](classes/AccountManager.md)
- [NuLinkHDWallet](classes/NuLinkHDWallet.md)

### Type Aliases

- [DataInfo](types/DataInfo.md)
- [GasInfo](types/GasInfo.md)

### Data Apply Details Functions

- [getApplyDetails](functions/getApplyDetails.md)
- [getMultiApplyDetails](functions/getMultiApplyDetails.md)

### Data Publisher(Alice) Approval Functions

- [getPolicyServerFee](functions/getPolicyServerFee.md)
- [getPolicyGasFee](functions/getPolicyGasFee.md)
- [ApprovalUseData](functions/ApprovalUseData.md)
- [getPolicyTokenCost](functions/getPolicyTokenCost.md)
- [estimatePolicyGas](functions/estimatePolicyGas.md)
- [approvalApplicationForUseData](functions/approvalApplicationForUseData.md)
- [refusalApplicationForUseData](functions/refusalApplicationForUseData.md)

### Data Publisher(Alice) Approval (Multi) Functions

- [getPolicysServerFee](functions/getPolicysServerFee.md)
- [getPolicysGasFee](functions/getPolicysGasFee.md)
- [ApprovalMultiUseData](functions/ApprovalMultiUseData.md)
- [getPolicysTokenCost](functions/getPolicysTokenCost.md)
- [estimatePolicysGas](functions/estimatePolicysGas.md)
- [approvalApplicationsForUseData](functions/approvalApplicationsForUseData.md)
- [refusalApplicationsForUseData](functions/refusalApplicationsForUseData.md)

### Data Publisher(Alice) Approval Details Functions

- [getDataForApprovedAsPublisher](functions/getDataForApprovedAsPublisher.md)
- [getDataForAllStatusAsPublisher](functions/getDataForAllStatusAsPublisher.md)
- [getDataByStatusForAllApplyAsPublisher](functions/getDataByStatusForAllApplyAsPublisher.md)
- [getDataAllStatusAsPublisher](functions/getDataAllStatusAsPublisher.md)
- [getDataByApplyStatusAsPublisher](functions/getDataByApplyStatusAsPublisher.md)
- [getDataPendingApprovalAsPublisher](functions/getDataPendingApprovalAsPublisher.md)
- [getApprovedDataAsPublisher](functions/getApprovedDataAsPublisher.md)
- [getDataForRefusedAsPublisher](functions/getDataForRefusedAsPublisher.md)
- [getDataByStatus](functions/getDataByStatus.md)

### Data Publisher(Alice) Data Details Functions

- [checkDataApprovalStatusIsUnderReviewOrApproved](functions/checkDataApprovalStatusIsUnderReviewOrApproved.md)
- [getDataInfoByStatus](functions/getDataInfoByStatus.md)
- [getUploadedData](functions/getUploadedData.md)
- [getDataInfosByAccount](functions/getDataInfosByAccount.md)
- [deleteUploadedData](functions/deleteUploadedData.md)
- [checkDataApprovalStatusIsApprovedOrApproving](functions/checkDataApprovalStatusIsApprovedOrApproving.md)
- [checkMultiDataApprovalStatusIsApprovedOrApproving](functions/checkMultiDataApprovalStatusIsApprovedOrApproving.md)
- [getDataInfosByPolicyId](functions/getDataInfosByPolicyId.md)
- [getDataDetails](functions/getDataDetails.md)

### Data Publisher(Alice) Download Data Functions

- [getDataContentAsPublisher](functions/getDataContentAsPublisher.md)
- [getDataContentByDataIdAsPublisher](functions/getDataContentByDataIdAsPublisher.md)

### Data Publisher(Alice) Policys Functions

- [getPublishedPolicyInfos](functions/getPublishedPolicyInfos.md)
- [getDataInfoOfPolicy](functions/getDataInfoOfPolicy.md)
- [getAllDataInfoOfPolicy](functions/getAllDataInfoOfPolicy.md)
- [getPublishedPoliciesInfo](functions/getPublishedPoliciesInfo.md)
- [getPoliciesInfo](functions/getPoliciesInfo.md)

### Data Publisher(Alice) Upload Data Functions

- [uploadDataByCreatePolicy](functions/uploadDataByCreatePolicy.md)
- [uploadDataBySelectPolicy](functions/uploadDataBySelectPolicy.md)

### Data User(Bob) Approval Details Functions

- [getDataAllStatusAsUser](functions/getDataAllStatusAsUser.md)
- [getDataByApplyStatusAsUser](functions/getDataByApplyStatusAsUser.md)
- [getDataPendingApprovalAsUser](functions/getDataPendingApprovalAsUser.md)
- [getApprovedDataAsUser](functions/getApprovedDataAsUser.md)
- [getUnapprovedDataAsUser](functions/getUnapprovedDataAsUser.md)
- [getDataByStatus](functions/getDataByStatus.md)

### Data User(Bob) Data Details Functions

- [checkDataApprovalStatusIsUnderReviewOrApproved](functions/checkDataApprovalStatusIsUnderReviewOrApproved.md)
- [getDataApprovedForApplicantAsUser](functions/getDataApprovedForApplicantAsUser.md)
- [getDataByStatusForAllApplyAsUser](functions/getDataByStatusForAllApplyAsUser.md)
- [getDataInfoByStatus](functions/getDataInfoByStatus.md)
- [getOtherShareData](functions/getOtherShareData.md)
- [checkDataApprovalStatusIsApprovedOrApproving](functions/checkDataApprovalStatusIsApprovedOrApproving.md)
- [checkMultiDataApprovalStatusIsApprovedOrApproving](functions/checkMultiDataApprovalStatusIsApprovedOrApproving.md)
- [getDataDetails](functions/getDataDetails.md)

### Data User(Bob) Download Data Functions

- [getDataForApprovedAsUser](functions/getDataForApprovedAsUser.md)
- [getApprovedFileContentUrl](functions/getApprovedFileContentUrl.md)
- [getApprovedDataContent](functions/getApprovedDataContent.md)
- [getDataContentAsUser](functions/getDataContentAsUser.md)
- [getDataContentByDataIdAsUser](functions/getDataContentByDataIdAsUser.md)

### Data User(Bob) Policys Functions

- [getPolicyInfosAsUser](functions/getPolicyInfosAsUser.md)
- [getDataInfoOfPolicy](functions/getDataInfoOfPolicy.md)
- [getAllDataInfoOfPolicy](functions/getAllDataInfoOfPolicy.md)
- [getInUsePoliciesInfo](functions/getInUsePoliciesInfo.md)
- [getPoliciesInfo](functions/getPoliciesInfo.md)

### Data User(Bob) Request Data Functions

- [applyForDataUsagesPermission](functions/applyForDataUsagesPermission.md)
- [applyForDataUsagePermission](functions/applyForDataUsagePermission.md)
- [revokePermissionApplicationOfData](functions/revokePermissionApplicationOfData.md)

### Send Raw Transaction Functions

- [sendCustomTransaction](functions/sendCustomTransaction.md)
- [estimateCustomTransactionGas](functions/estimateCustomTransactionGas.md)

### Wallet Account Functions

- [getLoginedUserInfo](functions/getLoginedUserInfo.md)
- [isUserLogined](functions/isUserLogined.md)
- [getUserDetails](functions/getUserDetails.md)
- [getUserByAccountId](functions/getUserByAccountId.md)
- [updateUserInfo](functions/updateUserInfo.md)
- [restoreWalletDataByRootExtendedPrivateKey](functions/restoreWalletDataByRootExtendedPrivateKey.md)
- [restoreWalletDataByMnemonic](functions/restoreWalletDataByMnemonic.md)
- [restoreWalletData](functions/restoreWalletData.md)
- [exportWalletData](functions/exportWalletData.md)
- [createWallet](functions/createWallet.md)
- [loadWallet](functions/loadWallet.md)
- [verifyPassword](functions/verifyPassword.md)
- [existDefaultAccount](functions/existDefaultAccount.md)
- [logoutWallet](functions/logoutWallet.md)
- [getWalletDefaultAccount](functions/getWalletDefaultAccount.md)
- [unlockWallet](functions/unlockWallet.md)
- [getMnemonic](functions/getMnemonic.md)
- [getDefaultAccountPrivateKey](functions/getDefaultAccountPrivateKey.md)
- [createAccountIfNotExist](functions/createAccountIfNotExist.md)
- [IsExistAccount](functions/IsExistAccount.md)
- [createAccount](functions/createAccount.md)
- [getAccountInfo](functions/getAccountInfo.md)
- [getAccountInfos](functions/getAccountInfos.md)
- [updateAccountInfo](functions/updateAccountInfo.md)
