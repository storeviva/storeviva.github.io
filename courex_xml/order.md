---
layout: default
title: Courex XML - Order
section: courex_xml/order
---

## Order

Place new delivery orders.

#### Parameters
- **AppType**: ```Order```
- **OrderType**: The order type of the shipment. ```Local``` or ```Export```.
- **SenderName**: The name of the Sender.
- **SenderCompany**: The company name of the Sender.
- **SenderContact**: The contact of the Sender.
- **SenderAddress**: The address of the Sender.
- **SenderAddress2**: The optional extra address line of the Sender.
- **SenderUnit**: The unit number of the Sender.
- **SenderCity**: The city of the Sender.
- **SenderState**: The state of the Sender.
- **SenderPostalCode**: The postal code of the Sender.
- **SenderCountry**: The country of the Sender.
- **RecipientName**: The name of the Receiver.
- **RecipientCompany**: The company name of the Receiver.
- **RecipientContact**: The contact of the Receiver.
- **RecipientAddress**: The address of the Receiver.
- **RecipientAddress2**: The optional extra address line of the Receiver.
- **RecipientUnit**: The unit number of the Receiver.
- **RecipientCity**: The city of the Receiver.
- **RecipientState**: The state of the Receiver.
- **RecipientPostalCode**: The postal code of the Receiver.
- **RecipientCountry**: The country of the Receiver.
- **NotificationEmail**: The email address of the Receiver for notification on shipment progress (local delivery only).
- **ContentDesc**: The content description of the shipment.
- **DeclaredValue**: The declared value of the shipment.
- **Weight**: The weight of the shipment.
- **ShipMethod**: The shipping method of the shipment.
- **ShipType**: The shipping type of the shipment. Each shipping type corresponds to different dimensions. Please ask Courex for the applicable shipping types.
- **PickupDate**: The pickup date of the shipment. OPTIONAL: Only required if Sender & Recipient’s Country is Singapore
- **PickupTime**: The pickup time of the shipment. OPTIONAL: Only required if Sender & Recipient’s Country is Singapore
- **DeliverDate**: The delivery date of the shipment. OPTIONAL: Only required if Sender & Recipient’s Country is Singapore
- **DeliverTime**: The delivery time of the shipment. OPTIONAL: Only required if Sender & Recipient’s Country is Singapore
- **VolL**: The length size of the shipment.
- **VolW**: The width size of the shipment.
- **VolH**: The height size of the shipment.
- **Instruction**: The additional instructions of the shipment. OPTIONAL: You may input any additional instructions pertaining to the order
- **PaymentMethod**: The payment method of the shipment. Available Options: 1 = Credit, 2 = Cash, 3 = Prepaid, 4 = Cheque
- **PaymentParty**: The payment party of the shipment. Available Options: 1 = Sender, 2 = Receiver
- **CustomTracking**: (Optional) Your own custom tracking number
- **CashCollection**: (Optional) Amount of Cash to be collected on delivery (COD). Enter the number only (without $ sign)

#### Response
- **AppType**: ```Order```
- **OrderType**: The order type of the shipment. ```Local``` or ```Export```.
- **TrackNo**: The tracking number assigned to the new order. Ex: ```ML213742```.
- **Status**: ```Successful```.
- **TotalCost**: Cost of the delivery in SGD.

## Example

Request:

```xml
<RequestCall>
  <AppType>Order</AppType>
  <UserName>[Username]</UserName>
  <Password>[pass]</Password>
  <Parameters>
	  <OrderType>Local</OrderType>
	  <SenderName>Test Sender Name</SenderName>
	  <SenderCompany>Courex Pte Ltd</SenderCompany>
	  <SenderContact>612345678</SenderContact>
	  <SenderAddress>Test Sender Address</SenderAddress>
	  <SenderUnit>0000</SenderUnit>
	  <SenderCity>NA</SenderCity>
	  <SenderState>NA</SenderState>
	  <SenderPostalCode>499637</SenderPostalCode>
	  <SenderCountry>Singapore</SenderCountry>
	  <RecipientName>test</RecipientName>
	  <RecipientCompany>test</RecipientCompany>
	  <RecipientContact>90110000</RecipientContact>
	  <RecipientAddress>Test Recipient Address</RecipientAddress>
	  <RecipientUnit>1111</RecipientUnit>
	  <RecipientCity>NA</RecipientCity>
	  <RecipientState>NA</RecipientState>
	  <RecipientPostalCode>486127</RecipientPostalCode>
	  <RecipientCountry>Singapore</RecipientCountry>
	  <NotificationEmail>recipient@test.com</NotificationEmail>
	  <ContentDesc>test content</ContentDesc>
	  <DeclaredValue>5</DeclaredValue>
	  <Weight>1</Weight>
	  <ShipMethod>Local</ShipMethod>
	  <ShipType>SmallParcel</ShipType>
	  <PickupDate>15062015</PickupDate>
	  <PickupTime>1400</PickupTime>
	  <DeliverDate>17062015</DeliverDate>
	  <DeliverTime>1400</DeliverTime>
	  <VolL>5</VolL>
	  <VolW>5</VolW>
	  <VolH>5</VolH>
	  <Instruction>Test Instruction</Instruction>
	  <PaymentMethod>1</PaymentMethod>
	  <PaymentParty>1</PaymentParty>
	  <CustomTracking>T-20160127-1</CustomTracking>
	  <CashCollection>199.90</CashCollection>
  </Parameters>
</RequestCall>
```

Response:

```xml
<RequestResponse>
  <Data>
   	<AppType>Order</AppType>
   	<OrderType>Local</OrderType>
   	<TrackNo>OL389899</TrackNo>
   	<Status>Successful</Status>
   	<TotalCost>6.00</TotalCost>
  </Data>
</RequestResponse>
```
