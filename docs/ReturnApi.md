# ReturnApi

All URIs are relative to *https://demo.channelengine.net/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**returnCreate**](ReturnApi.md#returnCreate) | **POST** /v2/returns | Mark (part of) an order as returned by the customer
[**returnGet**](ReturnApi.md#returnGet) | **GET** /v2/returns/{merchantReference} | Get a return by its merchant reference.
[**returnIndex**](ReturnApi.md#returnIndex) | **GET** /v2/returns | Gets all returns created since the supplied date.


<a name="returnCreate"></a>
# **returnCreate**
> ReturnViewModel returnCreate(model)

Mark (part of) an order as returned by the customer

### Example
```java
// Import classes:
//import io.swagger.client.ApiException;
//import io.swagger.client.api.ReturnApi;


ReturnApi apiInstance = new ReturnApi();
ReturnViewModel model = new ReturnViewModel(); // ReturnViewModel | 
try {
    ReturnViewModel result = apiInstance.returnCreate(model);
    System.out.println(result);
} catch (ApiException e) {
    System.err.println("Exception when calling ReturnApi#returnCreate");
    e.printStackTrace();
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **model** | [**ReturnViewModel**](ReturnViewModel.md)|  |

### Return type

[**ReturnViewModel**](ReturnViewModel.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, text/json, text/xml, application/x-www-form-urlencoded
 - **Accept**: application/json, text/json, text/xml

<a name="returnGet"></a>
# **returnGet**
> ReturnViewModel returnGet(merchantReference)

Get a return by its merchant reference.

### Example
```java
// Import classes:
//import io.swagger.client.ApiException;
//import io.swagger.client.api.ReturnApi;


ReturnApi apiInstance = new ReturnApi();
String merchantReference = "merchantReference_example"; // String | The unique return reference supplied by the merchant
try {
    ReturnViewModel result = apiInstance.returnGet(merchantReference);
    System.out.println(result);
} catch (ApiException e) {
    System.err.println("Exception when calling ReturnApi#returnGet");
    e.printStackTrace();
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **merchantReference** | **String**| The unique return reference supplied by the merchant |

### Return type

[**ReturnViewModel**](ReturnViewModel.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/json, text/xml

<a name="returnIndex"></a>
# **returnIndex**
> List&lt;ReturnViewModel&gt; returnIndex(createdSince)

Gets all returns created since the supplied date.

### Example
```java
// Import classes:
//import io.swagger.client.ApiException;
//import io.swagger.client.api.ReturnApi;


ReturnApi apiInstance = new ReturnApi();
Date createdSince = new Date(); // Date | 
try {
    List<ReturnViewModel> result = apiInstance.returnIndex(createdSince);
    System.out.println(result);
} catch (ApiException e) {
    System.err.println("Exception when calling ReturnApi#returnIndex");
    e.printStackTrace();
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **createdSince** | **Date**|  |

### Return type

[**List&lt;ReturnViewModel&gt;**](ReturnViewModel.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/json, text/xml

