
# OrderViewModel

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**merchantReference** | **String** |  | 
**channelReference** | **String** |  |  [optional]
**phone** | **String** |  |  [optional]
**email** | **String** |  | 
**companyRegistrationNo** | **String** |  |  [optional]
**vatNo** | **String** |  |  [optional]
**paymentMethod** | **String** |  |  [optional]
**shippingCostsInclVat** | **Double** | The shipping fee including VAT              (in the tenant&#39;s base currency calculated using the exchange rate at the time of ordering). |  [optional]
**shippingCostsVat** | **Double** | The total amount of VAT charged over the shipping fee              (in the tenant&#39;s base currency calculated using the exchange rate at the time of ordering). |  [optional]
**totalInclVat** | **Double** | The total value of the order including VAT              (in the tenant&#39;s base currency calculated using the exchange rate at the time of ordering). |  [optional]
**totalVat** | **Double** | The total amount of VAT charged over the total value of te order              (in the tenant&#39;s base currency calculated using the exchange rate at the time of ordering). |  [optional]
**originalShippingCostsInclVat** | **Double** | The shipping fee including VAT              (in the currency in which the order was paid for). |  [optional]
**originalShippingCostsVat** | **Double** | The total amount of VAT charged over the shipping fee              (in the currency in which the order was paid for). |  [optional]
**originalTotalInclVat** | **Double** | The total value of the order including VAT              (in the currency in which the order was paid for). |  [optional]
**originalTotalVat** | **Double** | The total amount of VAT charged over the total value of te order              (in the currency in which the order was paid for). |  [optional]
**currencyCode** | **String** |  | 
**orderDate** | [**Date**](Date.md) |  |  [optional]
**status** | [**StatusEnum**](#StatusEnum) |  |  [optional]
**acknowledgedDate** | [**Date**](Date.md) |  |  [optional]
**channelName** | **String** | Name of channel party (ie bol/vergelijk/amazon etc), used to make it easier to identify channels when using the api. |  [optional]
**canShipPartialOrderLines** | **Boolean** | Indicates if the merchant can ship partial orderlines. |  [optional]
**channelCustomerReference** | **String** |  |  [optional]
**billingAddress** | [**Address**](Address.md) |  | 
**maxVatRate** | **Double** |  |  [optional]
**extraData** | **Map&lt;String, String&gt;** |  |  [optional]
**shippingAddress** | [**Address**](Address.md) |  | 
**lines** | [**List&lt;OrderLineViewModel&gt;**](OrderLineViewModel.md) |  | 


<a name="StatusEnum"></a>
## Enum: StatusEnum
Name | Value
---- | -----
IN_PROGRESS | &quot;IN_PROGRESS&quot;
SHIPPED | &quot;SHIPPED&quot;
IN_BACKORDER | &quot;IN_BACKORDER&quot;
CANCELED | &quot;CANCELED&quot;
MANCO | &quot;MANCO&quot;
IN_COMBI | &quot;IN_COMBI&quot;
CLOSED | &quot;CLOSED&quot;
NEW | &quot;NEW&quot;
RETURNED | &quot;RETURNED&quot;
REQUIRES_CORRECTION | &quot;REQUIRES_CORRECTION&quot;



