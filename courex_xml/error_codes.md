---
layout: default
title: Courex XML - Error Codes
section: courex_xml/error_codes
---

## Error Codes

Application errors are included in your returned XML as they occur and take the following format:

```xml
<?xml version="1.0" ?>
<RequestResponse>
  <Data>
    <faultCode>error code</faultCode>
    <faultString>error description</faultString>
  </Data>
</RequestResponse>
```

| faultCode     | faultString  | Resolution  |
| ------------- | ------------------ | ----------- |
| 1 | Your account is not enabled for access into this API, please contact a Courex representative for more information. | Your account has not been enabled to use the API or you’ve entered the information wrongly. Please contact a Courex representative to enable the API if you have not done so. |
| 2 | The method you requested, xxx, was not found. | You have specified an invalid AppType in your XML. Please check that you have entered the correct Application Type. |
| 3 | Result Error! Invalid tracking number provided. Please check and try again. | This error is caused by an incorrect Tracking Number provided under the Tracking Application. Make sure a valid Tracking Number is entered and try again.
| 3 | Result Error! Invalid XML Syntax | This error occurs as no AppType is provided under AppType Request Call. Make sure you have entered a proper AppType and try again.
| 3 | Result Error! Invalid Order Type, Please check and try again. |  This error is caused by an incorrect OrderType entered under the Order Application. Make sure a correct OrderType is entered and try again.
| 3 | Order Creation Error! Please check your input and try again. | This error is caused by incorrect data provisioned in the Parameters element under the Order Application. Make sure you have double checked the information in the Parameters element and try again. |
| 3 | Quote Query Error! Please check your input and try again. | This error is caused by incorrect data provisioned in the Parameters element under the Quote Application. Make sure you have double checked the information in the Parameters element and try again. |
