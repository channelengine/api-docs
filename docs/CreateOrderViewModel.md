
# CreateOrderViewModel

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**channelReference** | **String** | The unique order number used by the Channel | 
**channelId** | **Integer** | The id of the Channel to create the order for. | 
**channelCustomerReference** | **String** | The unique customer number used by the Channel |  [optional]
**phone** | **String** | The customer&#39;s phone number |  [optional]
**email** | **String** | The customer&#39;s email address | 
**companyRegistrationNo** | **String** | The customer&#39;s company registration number (chamber of commerce) |  [optional]
**vatNo** | **String** | The customer&#39;s company VAT registration number |  [optional]
**paymentMethod** | **String** | The payment method used by the customer |  [optional]
**shippingCostsInclVat** | **Double** | The shipping fee including VAT |  [optional]
**currencyCode** | **String** | The ISO 4217 currency code of the currency in which the order was placed. | 
**orderDate** | [**Date**](Date.md) | The moment the order was placed at the Channel |  [optional]
**billingAddress** | [**Address**](Address.md) | The customer&#39;s invoice/billing address |  [optional]
**shippingAddress** | [**Address**](Address.md) | The customer&#39;s shipping address | 
**lines** | [**List&lt;CreateOrderLineViewModel&gt;**](CreateOrderLineViewModel.md) | The order lines | 
**extraData** | **Map&lt;String, String&gt;** | Any extra key/value pairs with information about the order |  [optional]



