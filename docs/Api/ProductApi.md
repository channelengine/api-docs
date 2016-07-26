# Swagger\Client\ProductApi

All URIs are relative to *https://demo.channelengine.net/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**productAcknowledgeDataChanges**](ProductApi.md#productAcknowledgeDataChanges) | **POST** /v2/products/data | This endpoint should be called after a call to GET &#39;v2/products/data&#39;. After a call to              this endpoint ChannelEngine &#39;knows&#39; which products are known to the channel (and the last              time they have been updated) and is therefore able to only return the products              that really have changed since the last call to POST &#39;v2/products/data&#39;.              The supplied ChannelReference will be saved              in our database and is supposed to be unique, the &#39;Updated&#39; and &#39;Removed&#39;              fields consist of ChannelReferences which are sent in a previous call              within the field &#39;Created&#39;.
[**productAcknowledgeOfferChanges**](ProductApi.md#productAcknowledgeOfferChanges) | **POST** /v2/products/offers | After a call to GET &#39;v2/products/offers&#39; this endpoint should be called with the              ChannelReference of the products that are successfully updated.              Please see &#39;v2/products/data&#39; and &#39;v2/products/data&#39; for documentation.
[**productCreate**](ProductApi.md#productCreate) | **POST** /v2/products | Create a product. The parent serves as the &#39;base&#39; product of the children.              For example, the children could be different sizes or colors of the parent product.              For channels where every size and color are different products this does not make any difference              (the children will just be sent separately, while ignoring the parent).              But there are channels where the parent and the children need to be sent together, for example              when there is one product with a list of sizes. In this case all the product information is retrieved              from the parent product while the size list is generated from the children.                            Note that the parent itself is a &#39;blueprint&#39; of the child products and we do our best to make sure it              does not end up on the marketplaces itself. Only the children can be purchased.                            It&#39;s not possible to nest parent and children more than one level (A parent can have many children,              but any child cannot itself also have children).                            The supplied MerchantProductReference needs to be unique.
[**productDelete**](ProductApi.md#productDelete) | **DELETE** /v2/products/{merchantReference} | Deactivate a product based on the merchant reference.              Note that we do not really delete a product, as the product              might still be referenced by orders etc.
[**productGet**](ProductApi.md#productGet) | **GET** /v2/products/{merchantReference} | Retrieve a product based on the merchant reference.
[**productGetDataChanges**](ProductApi.md#productGetDataChanges) | **GET** /v2/products/data | Get all products which have changes since the post http call to POST &#39;v2/products/data&#39;.              The response contains the products which should be created, updated or removed from the channel.              After the products have been received and processed successfully &#39;v2/products/data&#39; should              be called with the merchant references of the products which have been processed (see POST &#39;v2/products/data&#39;).               ChannelEnginewill save this information to make sure that the next call to GET &#39;v2/products/data&#39; only returns the              products that really have changes (and therefore should be created, updated or deleted).              A channel willing to integrate with channelengine should therefore only do the following things:                  1. Periodically poll &#39;v2/products/data&#39; for changes.                  2. If any products are returned, save, update or remove these products.                  3. Send the merchant references of the products that have succesfully been processed                  in step 2 to POST &#39;v2/products/data&#39;.                               These three simple steps will make sure that the products on the channel will be synchronized               with the products on ChannelEngine. ChannelEngine will use the API key to determine the customer              whose products should be returned.
[**productGetOfferChanges**](ProductApi.md#productGetOfferChanges) | **GET** /v2/products/offers | GET &#39;v2/products/offers&#39; and POST &#39;v2/products/offers&#39; closely resemble GET &#39;v2/products/data&#39; and POST &#39;v2/products/data&#39;. See the &#39;v2/products/data&#39;              endpoints for documentation. The difference between both endpoints is that &#39;v2/products/offers&#39; only returns Price and Stock updates and can (and should)              therefore be called more often to keep this information (which might change frequently) up to date.


# **productAcknowledgeDataChanges**
> \Swagger\Client\Model\Object productAcknowledgeDataChanges($changes)

This endpoint should be called after a call to GET 'v2/products/data'. After a call to              this endpoint ChannelEngine 'knows' which products are known to the channel (and the last              time they have been updated) and is therefore able to only return the products              that really have changed since the last call to POST 'v2/products/data'.              The supplied ChannelReference will be saved              in our database and is supposed to be unique, the 'Updated' and 'Removed'              fields consist of ChannelReferences which are sent in a previous call              within the field 'Created'.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$api_instance = new Swagger\Client\Api\ProductApi();
$changes = new \Swagger\Client\Model\ProcessedChanges(); // \Swagger\Client\Model\ProcessedChanges | The merchant references of the products which have been               successfully created, updated or deleted (after a call to 'GetDataChanges')

try {
    $result = $api_instance->productAcknowledgeDataChanges($changes);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ProductApi->productAcknowledgeDataChanges: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **changes** | [**\Swagger\Client\Model\ProcessedChanges**](../Model/\Swagger\Client\Model\ProcessedChanges.md)| The merchant references of the products which have been               successfully created, updated or deleted (after a call to &#39;GetDataChanges&#39;) |

### Return type

[**\Swagger\Client\Model\Object**](../Model/Object.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, text/json, text/xml, application/x-www-form-urlencoded
 - **Accept**: application/json, text/json, text/xml

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **productAcknowledgeOfferChanges**
> \Swagger\Client\Model\Object productAcknowledgeOfferChanges($changes)

After a call to GET 'v2/products/offers' this endpoint should be called with the              ChannelReference of the products that are successfully updated.              Please see 'v2/products/data' and 'v2/products/data' for documentation.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$api_instance = new Swagger\Client\Api\ProductApi();
$changes = array(new string[]()); // string[] | The channel references of the updated products

try {
    $result = $api_instance->productAcknowledgeOfferChanges($changes);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ProductApi->productAcknowledgeOfferChanges: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **changes** | **string[]**| The channel references of the updated products |

### Return type

[**\Swagger\Client\Model\Object**](../Model/Object.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, text/json, text/xml, application/x-www-form-urlencoded
 - **Accept**: application/json, text/json, text/xml

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **productCreate**
> \Swagger\Client\Model\ProductResponseViewModel productCreate($product_view)

Create a product. The parent serves as the 'base' product of the children.              For example, the children could be different sizes or colors of the parent product.              For channels where every size and color are different products this does not make any difference              (the children will just be sent separately, while ignoring the parent).              But there are channels where the parent and the children need to be sent together, for example              when there is one product with a list of sizes. In this case all the product information is retrieved              from the parent product while the size list is generated from the children.                            Note that the parent itself is a 'blueprint' of the child products and we do our best to make sure it              does not end up on the marketplaces itself. Only the children can be purchased.                            It's not possible to nest parent and children more than one level (A parent can have many children,              but any child cannot itself also have children).                            The supplied MerchantProductReference needs to be unique.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$api_instance = new Swagger\Client\Api\ProductApi();
$product_view = new \Swagger\Client\Model\ProductRequestViewModel(); // \Swagger\Client\Model\ProductRequestViewModel | 

try {
    $result = $api_instance->productCreate($product_view);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ProductApi->productCreate: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **product_view** | [**\Swagger\Client\Model\ProductRequestViewModel**](../Model/\Swagger\Client\Model\ProductRequestViewModel.md)|  |

### Return type

[**\Swagger\Client\Model\ProductResponseViewModel**](../Model/ProductResponseViewModel.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, text/json, text/xml, application/x-www-form-urlencoded
 - **Accept**: application/json, text/json, text/xml

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **productDelete**
> \Swagger\Client\Model\Object productDelete($merchant_reference)

Deactivate a product based on the merchant reference.              Note that we do not really delete a product, as the product              might still be referenced by orders etc.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$api_instance = new Swagger\Client\Api\ProductApi();
$merchant_reference = "merchant_reference_example"; // string | 

try {
    $result = $api_instance->productDelete($merchant_reference);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ProductApi->productDelete: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **merchant_reference** | **string**|  |

### Return type

[**\Swagger\Client\Model\Object**](../Model/Object.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/json, text/xml

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **productGet**
> \Swagger\Client\Model\ProductResponseViewModel productGet($merchant_reference)

Retrieve a product based on the merchant reference.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$api_instance = new Swagger\Client\Api\ProductApi();
$merchant_reference = "merchant_reference_example"; // string | 

try {
    $result = $api_instance->productGet($merchant_reference);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ProductApi->productGet: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **merchant_reference** | **string**|  |

### Return type

[**\Swagger\Client\Model\ProductResponseViewModel**](../Model/ProductResponseViewModel.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/json, text/xml

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **productGetDataChanges**
> \Swagger\Client\Model\ProductChangesViewModel productGetDataChanges()

Get all products which have changes since the post http call to POST 'v2/products/data'.              The response contains the products which should be created, updated or removed from the channel.              After the products have been received and processed successfully 'v2/products/data' should              be called with the merchant references of the products which have been processed (see POST 'v2/products/data').               ChannelEnginewill save this information to make sure that the next call to GET 'v2/products/data' only returns the              products that really have changes (and therefore should be created, updated or deleted).              A channel willing to integrate with channelengine should therefore only do the following things:                  1. Periodically poll 'v2/products/data' for changes.                  2. If any products are returned, save, update or remove these products.                  3. Send the merchant references of the products that have succesfully been processed                  in step 2 to POST 'v2/products/data'.                               These three simple steps will make sure that the products on the channel will be synchronized               with the products on ChannelEngine. ChannelEngine will use the API key to determine the customer              whose products should be returned.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$api_instance = new Swagger\Client\Api\ProductApi();

try {
    $result = $api_instance->productGetDataChanges();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ProductApi->productGetDataChanges: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**\Swagger\Client\Model\ProductChangesViewModel**](../Model/ProductChangesViewModel.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/json, text/xml

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

# **productGetOfferChanges**
> \Swagger\Client\Model\OfferViewModel[] productGetOfferChanges()

GET 'v2/products/offers' and POST 'v2/products/offers' closely resemble GET 'v2/products/data' and POST 'v2/products/data'. See the 'v2/products/data'              endpoints for documentation. The difference between both endpoints is that 'v2/products/offers' only returns Price and Stock updates and can (and should)              therefore be called more often to keep this information (which might change frequently) up to date.

### Example
```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');

$api_instance = new Swagger\Client\Api\ProductApi();

try {
    $result = $api_instance->productGetOfferChanges();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ProductApi->productGetOfferChanges: ', $e->getMessage(), PHP_EOL;
}
?>
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**\Swagger\Client\Model\OfferViewModel[]**](../Model/OfferViewModel.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/json, text/xml

[[Back to top]](#) [[Back to API list]](../../README.md#documentation-for-api-endpoints) [[Back to Model list]](../../README.md#documentation-for-models) [[Back to README]](../../README.md)

