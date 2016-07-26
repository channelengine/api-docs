# Swagger\Client\OrderApi

All URIs are relative to *https://demo.channelengine.net/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**orderCreate**](OrderApi.md#orderCreate) | **POST** /v2/orders | Create a new order in ChannelEngine.
[**orderCreate_0**](OrderApi.md#orderCreate_0) | **POST** /v2/orders/acknowledge | Acknowledge an order. By acknowledging the order the merchant can confirm that              the order has been imported. When acknowledging an order the merchant has to supply              references that uniquely identify the order and the order lines. These references              will be used in the other API calls.
[**orderGet**](OrderApi.md#orderGet) | **GET** /v2/orders/{merchantReference} | 
[**orderGetNew**](OrderApi.md#orderGetNew) | **GET** /v2/orders/new | Fetch newly placed orders (order with status NEW).


# **orderCreate**
> \Swagger\Client\Model\OrderViewModel orderCreate($model)

Create a new order in ChannelEngine.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$api_instance = new Swagger\Client\Api\OrderApi();
$model = new \Swagger\Client\Model\CreateOrderViewModel(); // \Swagger\Client\Model\CreateOrderViewModel | 

try {
    $result = $api_instance->orderCreate($model);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrderApi->orderCreate: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **model** | [**\Swagger\Client\Model\CreateOrderViewModel**](../Model/\Swagger\Client\Model\CreateOrderViewModel.md)|  |

### Return type

[**\Swagger\Client\Model\OrderViewModel**](../Model/OrderViewModel.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, text/json, text/xml, application/x-www-form-urlencoded
 - **Accept**: application/json, text/json, text/xml

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **orderCreate_0**
> \Swagger\Client\Model\OrderViewModel orderCreate_0($model)

Acknowledge an order. By acknowledging the order the merchant can confirm that              the order has been imported. When acknowledging an order the merchant has to supply              references that uniquely identify the order and the order lines. These references              will be used in the other API calls.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$api_instance = new Swagger\Client\Api\OrderApi();
$model = new \Swagger\Client\Model\OrderAcknowledgementViewModel(); // \Swagger\Client\Model\OrderAcknowledgementViewModel | Relations between the id's returned by ChannelEngine and the references              which the merchant uses

try {
    $result = $api_instance->orderCreate_0($model);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrderApi->orderCreate_0: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **model** | [**\Swagger\Client\Model\OrderAcknowledgementViewModel**](../Model/\Swagger\Client\Model\OrderAcknowledgementViewModel.md)| Relations between the id&#39;s returned by ChannelEngine and the references              which the merchant uses |

### Return type

[**\Swagger\Client\Model\OrderViewModel**](../Model/OrderViewModel.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, text/json, text/xml, application/x-www-form-urlencoded
 - **Accept**: application/json, text/json, text/xml

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **orderGet**
> \Swagger\Client\Model\OrderViewModel orderGet($merchant_reference)



### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$api_instance = new Swagger\Client\Api\OrderApi();
$merchant_reference = "merchant_reference_example"; // string | 

try {
    $result = $api_instance->orderGet($merchant_reference);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrderApi->orderGet: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **merchant_reference** | **string**|  |

### Return type

[**\Swagger\Client\Model\OrderViewModel**](../Model/OrderViewModel.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/json, text/xml

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **orderGetNew**
> \Swagger\Client\Model\OrderViewModel[] orderGetNew()

Fetch newly placed orders (order with status NEW).

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$api_instance = new Swagger\Client\Api\OrderApi();

try {
    $result = $api_instance->orderGetNew();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling OrderApi->orderGetNew: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**\Swagger\Client\Model\OrderViewModel[]**](../Model/OrderViewModel.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/json, text/xml

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

