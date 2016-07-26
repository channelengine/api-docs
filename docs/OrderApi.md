# OrderApi

All URIs are relative to *https://demo.channelengine.net/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**orderCreate**](OrderApi.md#orderCreate) | **POST** /v2/orders | Create a new order in ChannelEngine.
[**orderCreate_0**](OrderApi.md#orderCreate_0) | **POST** /v2/orders/acknowledge | Acknowledge an order. By acknowledging the order the merchant can confirm that              the order has been imported. When acknowledging an order the merchant has to supply              references that uniquely identify the order and the order lines. These references              will be used in the other API calls.
[**orderGet**](OrderApi.md#orderGet) | **GET** /v2/orders/{merchantReference} | 
[**orderGetNew**](OrderApi.md#orderGetNew) | **GET** /v2/orders/new | Fetch newly placed orders (order with status NEW).


<a name="orderCreate"></a>
# **orderCreate**
> OrderViewModel orderCreate(model)

Create a new order in ChannelEngine.

### Example
```java
// Import classes:
//import io.swagger.client.ApiException;
//import io.swagger.client.api.OrderApi;


OrderApi apiInstance = new OrderApi();
CreateOrderViewModel model = new CreateOrderViewModel(); // CreateOrderViewModel | 
try {
    OrderViewModel result = apiInstance.orderCreate(model);
    System.out.println(result);
} catch (ApiException e) {
    System.err.println("Exception when calling OrderApi#orderCreate");
    e.printStackTrace();
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **model** | [**CreateOrderViewModel**](CreateOrderViewModel.md)|  |

### Return type

[**OrderViewModel**](OrderViewModel.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, text/json, text/xml, application/x-www-form-urlencoded
 - **Accept**: application/json, text/json, text/xml

<a name="orderCreate_0"></a>
# **orderCreate_0**
> OrderViewModel orderCreate_0(model)

Acknowledge an order. By acknowledging the order the merchant can confirm that              the order has been imported. When acknowledging an order the merchant has to supply              references that uniquely identify the order and the order lines. These references              will be used in the other API calls.

### Example
```java
// Import classes:
//import io.swagger.client.ApiException;
//import io.swagger.client.api.OrderApi;


OrderApi apiInstance = new OrderApi();
OrderAcknowledgementViewModel model = new OrderAcknowledgementViewModel(); // OrderAcknowledgementViewModel | Relations between the id's returned by ChannelEngine and the references              which the merchant uses
try {
    OrderViewModel result = apiInstance.orderCreate_0(model);
    System.out.println(result);
} catch (ApiException e) {
    System.err.println("Exception when calling OrderApi#orderCreate_0");
    e.printStackTrace();
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **model** | [**OrderAcknowledgementViewModel**](OrderAcknowledgementViewModel.md)| Relations between the id&#39;s returned by ChannelEngine and the references              which the merchant uses |

### Return type

[**OrderViewModel**](OrderViewModel.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, text/json, text/xml, application/x-www-form-urlencoded
 - **Accept**: application/json, text/json, text/xml

<a name="orderGet"></a>
# **orderGet**
> OrderViewModel orderGet(merchantReference)



### Example
```java
// Import classes:
//import io.swagger.client.ApiException;
//import io.swagger.client.api.OrderApi;


OrderApi apiInstance = new OrderApi();
String merchantReference = "merchantReference_example"; // String | 
try {
    OrderViewModel result = apiInstance.orderGet(merchantReference);
    System.out.println(result);
} catch (ApiException e) {
    System.err.println("Exception when calling OrderApi#orderGet");
    e.printStackTrace();
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **merchantReference** | **String**|  |

### Return type

[**OrderViewModel**](OrderViewModel.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/json, text/xml

<a name="orderGetNew"></a>
# **orderGetNew**
> List&lt;OrderViewModel&gt; orderGetNew()

Fetch newly placed orders (order with status NEW).

### Example
```java
// Import classes:
//import io.swagger.client.ApiException;
//import io.swagger.client.api.OrderApi;


OrderApi apiInstance = new OrderApi();
try {
    List<OrderViewModel> result = apiInstance.orderGetNew();
    System.out.println(result);
} catch (ApiException e) {
    System.err.println("Exception when calling OrderApi#orderGetNew");
    e.printStackTrace();
}
```

### Parameters
This endpoint does not need any parameter.

### Return type

[**List&lt;OrderViewModel&gt;**](OrderViewModel.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/json, text/xml

