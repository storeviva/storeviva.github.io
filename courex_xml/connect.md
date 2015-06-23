---
layout: default
title: Courex XML - Connect
section: courex_xml/connect
---

## Connecting to the XML Server

A new user of the Courex XML application will need to complete the following steps before attempting to send an XML document directly to the Courex server.

- Each customer is required to have his account XML enabled as this is required for the server to grant your XML submission. This access has to be requested from a Courex representative.
- Customers are required to use their own username and password to authenticate with the server for each XML submission.

## Service URL

All XML services is accessed througth the URL: ```https://www.courex.com.sg/xml/```

## HTTP Request format

```http
POST index.php HTTP/1.0
Accept: */*
User-Agent: CourexGateway_socket/1.0
Content-Type: application/x-www-form-urlencoded
Content-Length: X (length of data plus 19 for “HTTP_RAW_POST_DATA=”)

HTTP_RAW_POST_DATA=<RequestCall><!-- Service specific data --></RequestCall>
```

XML document is the XML corresponding to the format needed by the requested service.

Once the above data has been sent, read from the socket until further data is available. The data returned will consist of the requested information as documented in the service's documentation.

## Input Format

The parameters are passed as XML elements. The parameter names are case-sensitive.

```xml
<RequestCall>
 <AppType>Service Name</AppType>
 <UserName>YOUR USERNAME</UserName>
 <Password>YOUR PASSWORD</Password>
 <Parameters>
  <!-- AppType dependent parameters -->
 </Parameters>
</RequestCall>
```

## Output Format

The HTTP response in the following format:

```xml
<?xml version=”1.0” ?>
<RequestResponse>
  <Data>
    <AppType>Tracking</AppType>
    <TrackNo>1234</TrackNo>
    <Date>1280738116</Date>
    <Location>Singapore</Location>
    <Activity>New Order</Activity>
  </Data>
  ... etc ...
  <Data>
    <AppType>Tracking</AppType>
    <TrackNo>1234</TrackNo>
    <Date>1280739010</Date>
    <Location>Singapore</Location>
    <Activity>Delivered</Activity>
  </Data>
</RequestResponse>
```
