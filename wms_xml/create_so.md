---
layout: default
title: WMS XML - Sales Order
section: wms_xml/create_so
---

## Sales Order

Create new Sales Order.

#### Order Parameters
- **AppType**: ```SOCreate```
- **Terms**: The payment terms of the order, eg ```NET 7```, ```NET 30```, ```COD```.
- **BillContactPerson**: The person to contact for billing.
- **BillContactPhone**: Phone number to contact for billing.
- **BillCompany**: Billing company name.
- **BillAdd**: Billing address line 1.
- **BillAdd2**: (Optional) Billing address line 2.
- **BillUnit**:  (Optional) Billing address unit number.
- **BillPostalCode**: Billing address postal code.
- **BillCountry**: Billing country.
- **ShipContactPerson**: The person to contact for shipping.
- **ShipContactPhone**: Phone number to contact for shipping.
- **ShipCompany**:  (Optional) Shipping company name.
- **ShipAdd**: Shipping address line 1.
- **ShipAdd2**: (Optional) Shipping address line 2.
- **ShipUnit**:  (Optional) Shipping address unit number.
- **ShipPostalCode**: Shipping address postal code.
- **ShipCountry**: Shipping country.
- **Currency**: Currency of the order. Accepted value: ```SGD```.
- **ShipCharge**: (Optional) Shipping charge of the order. Enter numeric only without the $.
- **Tax**: (Optional) Taxes for the order. Enter numeric only without the $.
- **TotalCost**: Total Cost of the order. Enter numeric only without the $.
- **PaymentMethod**: Payment Method of the order.
- **SOReference**: (Optional) Your reference for the order.
- **ShipDate**: (Optional) Shipping Date for the order. Format ```DDMMYYYY```, eg, ```25092015```.
- **ShipTime**: (Optional) Shipping Time for the order.
- **SORemarks**: (Optional) Any remarks for the order. If Courex delivery order is created after fulfilling the Sales Order, this remarks will appear in delivery instruction.
- **CreateItem**: (Optional) Flag to indicate that if there is new item in ```Item``` tag, it can be created on the fly. Accepted value: ```1```.
- **SONumber**: (Optional) Custom Order number. It will override the default order number. Do this if you would like to use your own format.

#### Item Parameters

These parameters has to be enclosed in ```Item```, 1 item element per SKU.

- **ItemSKU**: SKU of item as in StoreViva inventory. *If ```CreateItem``` is set to 1, the SKU will be created if it doesn't exist. Otherwise, do ensure the SKU exists before order creation.*
- **ItemQty**: Qty of this item in the order.
- **ItemPrice**: Price of this item in the order.
- **ItemName**: (Conditional) Name of this item.
- **ItemBarcode**: (Conditional) Barcode of this item.
- **ItemCategory**: (Conditional) Category of this item, eg PRODUCTS, BOOKS, ELECTRONICS.
- **UnitsofMeasurement**: (Conditional) The Units of Measurement, eg PIECE, BOX, BOTTLE.

*Conditional* parameters: Compulsory if ```CreateItem``` is set to 1

#### Response
- **AppType**: ```SOCreate```
- **SOCreate**: Order Number issued on successful order creation. If you set your own SONumber, this will be the value returned.
- **Status**: ```Successful```.

## Example

Request:

```xml
<RequestCall>
  <AppType>SOCreate</AppType>
  <UserName>[Username]</UserName>
  <Password>[pass]</Password>
  <Parameters>
	  <Terms>NET 7</Terms>
    <BillContactPerson>Mr Joe</BillContactPerson>
    <BillContactPhone>90111111</BillContactPhone>
    <BillCompany>ABC</BillCompany>
    <BillAdd>4 Changi South Lane</BillAdd>
    <BillAdd2></BillAdd2>
    <BillUnit>#07-02</BillUnit>
    <BillPostalCode>486127</BillPostalCode>
    <BillCountry>Singapore</BillCountry>
    <ShipContactPerson>Ms Jane</ShipContactPerson>
    <ShipContactPhone>90111116</ShipContactPhone>
    <ShipCompany>ABC</ShipCompany>
    <ShipAdd>4 Changi South Lane</ShipAdd>
    <ShipAdd2>Nan Wah Building</ShipAdd2>
    <ShipUnit>#07-04</ShipUnit>
    <ShipPostalCode>486127</ShipPostalCode>
    <ShipCountry>Singapore</ShipCountry>
    <Currency>SGD</Currency>
    <ShipCharge>25</ShipCharge>
    <Tax>10</Tax>
    <TotalCost>500</TotalCost>
    <PaymentMethod>credit</PaymentMethod>
    <SOReference>TSO20160901_1</SOReference>
    <ShipDate>16092016</ShipDate>
    <SORemarks>Please handle with care</SORemarks>
    <Item>
      <ItemSKU>SKU-1978</ItemSKU>
      <ItemQty>2</ItemQty>
      <ItemPrice>100</ItemPrice>
    </Item>
    <Item>
      <ItemSKU>SKU-1979</ItemSKU>
      <ItemQty>3</ItemQty>
      <ItemPrice>100</ItemPrice>
    </Item>
  </Parameters>
</RequestCall>
```

Response:

```xml
<RequestResponse>
  <Data>
   	<AppType>SOCreate</AppType>
   	<SONumber>SO2016-000001</SONumber>
   	<Status>Successful</Status>
  </Data>
</RequestResponse>
```
