# ShipmentApi

All URIs are relative to *https://demo.channelengine.net/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**shipmentCreate**](ShipmentApi.md#shipmentCreate) | **POST** /v2/shipments | Mark (part of) an order as shipped.
[**shipmentGet**](ShipmentApi.md#shipmentGet) | **GET** /v2/shipments/{merchantReference} | Get a shipment by its merchant reference.
[**shipmentIndex**](ShipmentApi.md#shipmentIndex) | **GET** /v2/shipments | Gets all shipments created since the supplied date.


<a name="shipmentCreate"></a>
# **shipmentCreate**
> ShipmentViewModel shipmentCreate(model)

Mark (part of) an order as shipped.

### Example
```java
// Import classes:
//import io.swagger.client.ApiException;
//import io.swagger.client.api.ShipmentApi;


ShipmentApi apiInstance = new ShipmentApi();
ShipmentViewModel model = new ShipmentViewModel(); // ShipmentViewModel | 
try {
    ShipmentViewModel result = apiInstance.shipmentCreate(model);
    System.out.println(result);
} catch (ApiException e) {
    System.err.println("Exception when calling ShipmentApi#shipmentCreate");
    e.printStackTrace();
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **model** | [**ShipmentViewModel**](ShipmentViewModel.md)|  |

### Return type

[**ShipmentViewModel**](ShipmentViewModel.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: application/json, text/json, text/xml, application/x-www-form-urlencoded
 - **Accept**: application/json, text/json, text/xml

<a name="shipmentGet"></a>
# **shipmentGet**
> ShipmentViewModel shipmentGet(merchantReference)

Get a shipment by its merchant reference.

### Example
```java
// Import classes:
//import io.swagger.client.ApiException;
//import io.swagger.client.api.ShipmentApi;


ShipmentApi apiInstance = new ShipmentApi();
String merchantReference = "merchantReference_example"; // String | The unique shipment reference supplied by the merchant
try {
    ShipmentViewModel result = apiInstance.shipmentGet(merchantReference);
    System.out.println(result);
} catch (ApiException e) {
    System.err.println("Exception when calling ShipmentApi#shipmentGet");
    e.printStackTrace();
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **merchantReference** | **String**| The unique shipment reference supplied by the merchant |

### Return type

[**ShipmentViewModel**](ShipmentViewModel.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/json, text/xml

<a name="shipmentIndex"></a>
# **shipmentIndex**
> List&lt;ShipmentViewModel&gt; shipmentIndex(createdSince)

Gets all shipments created since the supplied date.

### Example
```java
// Import classes:
//import io.swagger.client.ApiException;
//import io.swagger.client.api.ShipmentApi;


ShipmentApi apiInstance = new ShipmentApi();
Date createdSince = new Date(); // Date | 
try {
    List<ShipmentViewModel> result = apiInstance.shipmentIndex(createdSince);
    System.out.println(result);
} catch (ApiException e) {
    System.err.println("Exception when calling ShipmentApi#shipmentIndex");
    e.printStackTrace();
}
```

### Parameters

Name | Type | Description  | Notes
------------- | ------------- | ------------- | -------------
 **createdSince** | **Date**|  |

### Return type

[**List&lt;ShipmentViewModel&gt;**](ShipmentViewModel.md)

### Authorization

No authorization required

### HTTP request headers

 - **Content-Type**: Not defined
 - **Accept**: application/json, text/json, text/xml

