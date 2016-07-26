# BackOrderApi

All URIs are relative to *https://demo.channelengine.net/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**backOrderCreate**](BackOrderApi.md#backOrderCreate) | **POST** /v2/backorders | Mark (part of) an order as in backorder.
[**backOrderGet**](BackOrderApi.md#backOrderGet) | **GET** /v2/backorders/{merchantReference} | Retrieve a backorder by its reference. A back order references the order              which is temporarly out of stock.
[**backOrderIndex**](BackOrderApi.md#backOrderIndex) | **GET** /v2/backorders | Gets all backorders created since the supplied date.


<a name="backOrderCreate"></a>
# **backOrderCreate**
> BackOrderViewModel backOrderCreate(backOrder)

Mark (part of) an order as in backorder.

### Example
```java
// Import classes:
//import io.swagger.client.ApiException;
//import io.swagger.client.api.BackOrderApi;


BackOrderApi apiInstance = new BackOrderApi();
BackOrderViewModel backOrder = new BackOrderViewModel(); // BackOrderViewModel | 
try {
    BackOrderViewModel result = apiInstance.backOrderCreate(backOrder);
    System.out.println(result);
} catch (ApiException e) {
    System.err.println("Exception when calling BackOrderApi#backOrderCreate");
    e.printStackTrace();
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **backOrder** | [**BackOrderViewModel**](BackOrderViewModel.md)|  |

### Return type

[**BackOrderViewModel**](BackOrderViewModel.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, text/json, text/xml, application/x-www-form-urlencoded
 - **Accept**: application/json, text/json, text/xml

<a name="backOrderGet"></a>
# **backOrderGet**
> BackOrderViewModel backOrderGet(merchantReference)

Retrieve a backorder by its reference. A back order references the order              which is temporarly out of stock.

### Example
```java
// Import classes:
//import io.swagger.client.ApiException;
//import io.swagger.client.api.BackOrderApi;


BackOrderApi apiInstance = new BackOrderApi();
String merchantReference = "merchantReference_example"; // String | The unique backorder reference supplied by the merchant
try {
    BackOrderViewModel result = apiInstance.backOrderGet(merchantReference);
    System.out.println(result);
} catch (ApiException e) {
    System.err.println("Exception when calling BackOrderApi#backOrderGet");
    e.printStackTrace();
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **merchantReference** | **String**| The unique backorder reference supplied by the merchant |

### Return type

[**BackOrderViewModel**](BackOrderViewModel.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/json, text/xml

<a name="backOrderIndex"></a>
# **backOrderIndex**
> List&lt;BackOrderViewModel&gt; backOrderIndex(createdSince)

Gets all backorders created since the supplied date.

### Example
```java
// Import classes:
//import io.swagger.client.ApiException;
//import io.swagger.client.api.BackOrderApi;


BackOrderApi apiInstance = new BackOrderApi();
Date createdSince = new Date(); // Date | 
try {
    List<BackOrderViewModel> result = apiInstance.backOrderIndex(createdSince);
    System.out.println(result);
} catch (ApiException e) {
    System.err.println("Exception when calling BackOrderApi#backOrderIndex");
    e.printStackTrace();
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **createdSince** | **Date**|  |

### Return type

[**List&lt;BackOrderViewModel&gt;**](BackOrderViewModel.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/json, text/xml

