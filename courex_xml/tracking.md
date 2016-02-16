---
layout: default
title: Courex XML - Tracking
section: courex_xml/tracking
---

## Tracking

Returns the list of all events pertaining to the specified tracking number and its current status. Newer events are returned first.

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
  - ```In Transit```, ```On the way to deliver```, ```On the way to pickup```
  - ```Transferred to International Shipping```
  - ```Undelivered - No One Home```, ```Undelivered - Wrong Address```, ```Undelivered - Moved```, ```Undelivered - Not Willing To Accept```, ```Undelivered - Other```
  - ```Returned connote and COD```
  - ```Returned to Sender```

#### Example

Request:

```xml
<RequestCall>
  <AppType>Tracking</AppType>
  <UserName>[Username]</UserName>
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
