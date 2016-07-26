# CreateOrderViewModel

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**channel_reference** | **string** | The unique order number used by the Channel | 
**channel_id** | **int** | The id of the Channel to create the order for. | 
**channel_customer_reference** | **string** | The unique customer number used by the Channel | [optional] 
**phone** | **string** | The customer&#39;s phone number | [optional] 
**email** | **string** | The customer&#39;s email address | 
**company_registration_no** | **string** | The customer&#39;s company registration number (chamber of commerce) | [optional] 
**vat_no** | **string** | The customer&#39;s company VAT registration number | [optional] 
**payment_method** | **string** | The payment method used by the customer | [optional] 
**shipping_costs_incl_vat** | **double** | The shipping fee including VAT | [optional] 
**currency_code** | **string** | The ISO 4217 currency code of the currency in which the order was placed. | 
**order_date** | [**\DateTime**](\DateTime.md) | The moment the order was placed at the Channel | [optional] 
**billing_address** | [**\Swagger\Client\Model\Address**](Address.md) | The customer&#39;s invoice/billing address | [optional] 
**shipping_address** | [**\Swagger\Client\Model\Address**](Address.md) | The customer&#39;s shipping address | 
**lines** | [**\Swagger\Client\Model\CreateOrderLineViewModel[]**](CreateOrderLineViewModel.md) | The order lines | 
**extra_data** | **map[string,string]** | Any extra key/value pairs with information about the order | [optional] 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)


