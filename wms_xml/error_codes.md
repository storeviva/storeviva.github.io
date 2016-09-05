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
| 3 | Result Error! Invalid XML Syntax | This error occurs as no AppType is provided under AppType Request Call. Make sure you have entered a proper AppType and try again.
| 3 | Result Error! Invalid parameters or missing compulsory values. | This error occurs as the compulsory values are not entered correctly. Please check either parameter or values and try again.
