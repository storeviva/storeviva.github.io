---
layout: default
title: Courex XML - Tracking
section: courex_xml/tracking
---

## Tracking

Returns the status of the specified tracking number. The returns the list of all events pertaining to the specified tracking number.

#### Parameters
- **AppType**: ```Tracking```
- **TrackNo**: The tracking number of the order to check. Ex: ```OL01234```.

#### Response
- **AppType**: ```Tracking```
- **TrackNo**: The tracking number checked. Ex: ```ML213742```.
- **Date**: Date & time of the event occurence as a unix timestamp.
- **Location**: ```Singapore```.
- **Activity**:
  - ```New Order```
  - ```Delivered```
  - ```Picked Up```, ```Collected```
  - ```In Warehouse```
  - ```In Transit```, ```In Transit to Destination```
  - ```Transferred to International Shipping```
  - ```Undelivered - No One Home```, ```Undelivered - Wrong Address```, ```Undelivered - Moved```, ```Undelivered - Not Willing To Accept```, ```Undelivered - Other```

#### Example

Request:

```xml
<RequestCall>
  <AppType>Tracking</AppType>
  <UserName>dolita</UserName>
  <Password>[pass]</Password>
  <Parameters>
	<TrackNo>ML213742</TrackNo>
  </Parameters>
</RequestCall>
```

Response:

```xml
<RequestResponse>
  <Data>
   	<AppType>Tracking</AppType>
   	<TrackNo>ML213742</TrackNo>
   	<Date>1387160796</Date>
   	<Location>Singapore</Location>
   	<Activity>Delivered</Activity>
  </Data>
  <Data>
   	<AppType>Tracking</AppType>
   	<TrackNo>ML213742</TrackNo>
   	<Date>1379675139</Date>
   	<Location>Singapore</Location>
   	<Activity>New Order</Activity>
  </Data>
</RequestResponse>
```
