
# OrderLineViewModel

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**merchantReference** | **String** |  | 
**channelReference** | **String** |  |  [optional]
**quantity** | **Integer** |  | 
**vatRate** | **Double** |  | 
**unitPriceInclVat** | **Double** | The value of a single unit of the ordered product including VAT              (in the tenant&#39;s base currency calculated using the exchange rate at the time of ordering). | 
**unitVat** | **Double** | The total amount of VAT charged over the value of a single unit of the ordered product              (in the tenant&#39;s base currency calculated using the exchange rate at the time of ordering). | 
**originalUnitPriceInclVat** | **Double** | The value of a single unit of the ordered product including VAT              (in the currency in which the order was paid for). | 
**originalUnitVat** | **Double** | The total amount of VAT charged over the value of a single unit of the ordered product              (in the currency in which the order was paid for). | 
**feeFixed** | **Double** |  |  [optional]
**feeRate** | **Double** |  |  [optional]
**deliveryTimeIndication** | **String** |  |  [optional]



