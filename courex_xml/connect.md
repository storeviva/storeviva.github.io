---
layout: default
title: Courex XML - Connect
section: courex_xml/connect
---

## Connecting to the XML Server

A new user of the Courex XML application will need to complete the following steps before attempting to send an XML document directly to the Courex server.

- Each customer is required to have his account XML enabled as this is required for the server to grant your XML submission. This access has to be requested from a Courex representative.
- Customers are required to use their own username and password to authenticate with the server for each XML submission.
- Please read section 2.2 on the implementation considerations.

## Connection HTTP Request

Send the following lines, data between quotes. N.B. 1 blank line should be sent after Content-length line.

```http
POST index.php HTTP/1.0
Accept: */*
User-Agent: CourexGateway_socket/1.0
Content-Type: application/x-www-form-urlencoded
Content-Length: X (replace X with the length of data plus 19 for “HTTP_RAW_POST_DATA=”)
HTTP_RAW_POST_DATA=XML document (this is the content of message)
```

XML document is the XML corresponding to the format needed by the requested service.

Once the above data has been sent, read from the socket until further data is available. The data returned will consist of the requested information as documented in the service's documentation.
