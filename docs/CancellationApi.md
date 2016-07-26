# CancellationApi

All URIs are relative to *https://demo.channelengine.net/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**cancellationCreate**](CancellationApi.md#cancellationCreate) | **POST** /v2/cancellations | Mark (part of) an order as cancelled.
[**cancellationGet**](CancellationApi.md#cancellationGet) | **GET** /v2/cancellations/{merchantReference} | Get a cancellation by its merchant reference.
[**cancellationIndex**](CancellationApi.md#cancellationIndex) | **GET** /v2/cancellations | Gets all cancellations created since the supplied date.


<a name="cancellationCreate"></a>
# **cancellationCreate**
> CancellationViewModel cancellationCreate(cancellation)

Mark (part of) an order as cancelled.

### Example
```java
// Import classes:
//import io.swagger.client.ApiException;
//import io.swagger.client.api.CancellationApi;


CancellationApi apiInstance = new CancellationApi();
CancellationViewModel cancellation = new CancellationViewModel(); // CancellationViewModel | 
try {
    CancellationViewModel result = apiInstance.cancellationCreate(cancellation);
    System.out.println(result);
} catch (ApiException e) {
    System.err.println("Exception when calling CancellationApi#cancellationCreate");
    e.printStackTrace();
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **cancellation** | [**CancellationViewModel**](CancellationViewModel.md)|  |

### Return type

[**CancellationViewModel**](CancellationViewModel.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, text/json, text/xml, application/x-www-form-urlencoded
 - **Accept**: application/json, text/json, text/xml

<a name="cancellationGet"></a>
# **cancellationGet**
> CancellationViewModel cancellationGet(merchantReference)

Get a cancellation by its merchant reference.

### Example
```java
// Import classes:
//import io.swagger.client.ApiException;
//import io.swagger.client.api.CancellationApi;


CancellationApi apiInstance = new CancellationApi();
String merchantReference = "merchantReference_example"; // String | The unique cancellation reference supplied by the merchant
try {
    CancellationViewModel result = apiInstance.cancellationGet(merchantReference);
    System.out.println(result);
} catch (ApiException e) {
    System.err.println("Exception when calling CancellationApi#cancellationGet");
    e.printStackTrace();
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **merchantReference** | **String**| The unique cancellation reference supplied by the merchant |

### Return type

[**CancellationViewModel**](CancellationViewModel.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/json, text/xml

<a name="cancellationIndex"></a>
# **cancellationIndex**
> List&lt;CancellationViewModel&gt; cancellationIndex(createdSince)

Gets all cancellations created since the supplied date.

### Example
```java
// Import classes:
//import io.swagger.client.ApiException;
//import io.swagger.client.api.CancellationApi;


CancellationApi apiInstance = new CancellationApi();
Date createdSince = new Date(); // Date | 
try {
    List<CancellationViewModel> result = apiInstance.cancellationIndex(createdSince);
    System.out.println(result);
} catch (ApiException e) {
    System.err.println("Exception when calling CancellationApi#cancellationIndex");
    e.printStackTrace();
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **createdSince** | **Date**|  |

### Return type

[**List&lt;CancellationViewModel&gt;**](CancellationViewModel.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/json, text/xml

