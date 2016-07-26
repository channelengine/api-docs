# swagger-java-client

## Requirements

Building the API client library requires [Maven](https://maven.apache.org/) to be installed.

## Installation

To install the API client library to your local Maven repository, simply execute:

```shell
mvn install
```

To deploy it to a remote Maven repository instead, configure the settings of the repository and execute:

```shell
mvn deploy
```

Refer to the [official documentation](https://maven.apache.org/plugins/maven-deploy-plugin/usage.html) for more information.

### Maven users

Add this dependency to your project's POM:

```xml
<dependency>
    <groupId>io.swagger</groupId>
    <artifactId>swagger-java-client</artifactId>
    <version>1.0.0</version>
    <scope>compile</scope>
</dependency>
```

### Gradle users

Add this dependency to your project's build file:

```groovy
compile "io.swagger:swagger-java-client:1.0.0"
```

### Others

At first generate the JAR by executing:

    mvn package

Then manually install the following JARs:

* target/swagger-java-client-1.0.0.jar
* target/lib/*.jar

## Getting Started

Please follow the [installation](#installation) instruction and execute the following Java code:

```java

import io.swagger.client.*;
import io.swagger.client.auth.*;
import io.swagger.client.model.*;
import io.swagger.client.api.BackOrderApi;

import java.io.File;
import java.util.*;

public class BackOrderApiExample {

    public static void main(String[] args) {
        
        BackOrderApi apiInstance = new BackOrderApi();
        BackOrderViewModel backOrder = new BackOrderViewModel(); // BackOrderViewModel | 
        try {
            BackOrderViewModel result = apiInstance.backOrderCreate(backOrder);
            System.out.println(result);
        } catch (ApiException e) {
            System.err.println("Exception when calling BackOrderApi#backOrderCreate");
            e.printStackTrace();
        }
    }
}

```

## Documentation for API Endpoints

All URIs are relative to *https://demo.channelengine.net/api*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*BackOrderApi* | [**backOrderCreate**](docs/BackOrderApi.md#backOrderCreate) | **POST** /v2/backorders | Mark (part of) an order as in backorder.
*BackOrderApi* | [**backOrderGet**](docs/BackOrderApi.md#backOrderGet) | **GET** /v2/backorders/{merchantReference} | Retrieve a backorder by its reference. A back order references the order              which is temporarly out of stock.
*BackOrderApi* | [**backOrderIndex**](docs/BackOrderApi.md#backOrderIndex) | **GET** /v2/backorders | Gets all backorders created since the supplied date.
*CancellationApi* | [**cancellationCreate**](docs/CancellationApi.md#cancellationCreate) | **POST** /v2/cancellations | Mark (part of) an order as cancelled.
*CancellationApi* | [**cancellationGet**](docs/CancellationApi.md#cancellationGet) | **GET** /v2/cancellations/{merchantReference} | Get a cancellation by its merchant reference.
*CancellationApi* | [**cancellationIndex**](docs/CancellationApi.md#cancellationIndex) | **GET** /v2/cancellations | Gets all cancellations created since the supplied date.
*OrderApi* | [**orderCreate**](docs/OrderApi.md#orderCreate) | **POST** /v2/orders | Create a new order in ChannelEngine.
*OrderApi* | [**orderCreate_0**](docs/OrderApi.md#orderCreate_0) | **POST** /v2/orders/acknowledge | Acknowledge an order. By acknowledging the order the merchant can confirm that              the order has been imported. When acknowledging an order the merchant has to supply              references that uniquely identify the order and the order lines. These references              will be used in the other API calls.
*OrderApi* | [**orderGet**](docs/OrderApi.md#orderGet) | **GET** /v2/orders/{merchantReference} | 
*OrderApi* | [**orderGetNew**](docs/OrderApi.md#orderGetNew) | **GET** /v2/orders/new | Fetch newly placed orders (order with status NEW).
*ProductApi* | [**productAcknowledgeDataChanges**](docs/ProductApi.md#productAcknowledgeDataChanges) | **POST** /v2/products/data | This endpoint should be called after a call to GET &#39;v2/products/data&#39;. After a call to              this endpoint ChannelEngine &#39;knows&#39; which products are known to the channel (and the last              time they have been updated) and is therefore able to only return the products              that really have changed since the last call to POST &#39;v2/products/data&#39;.              The supplied ChannelReference will be saved              in our database and is supposed to be unique, the &#39;Updated&#39; and &#39;Removed&#39;              fields consist of ChannelReferences which are sent in a previous call              within the field &#39;Created&#39;.
*ProductApi* | [**productAcknowledgeOfferChanges**](docs/ProductApi.md#productAcknowledgeOfferChanges) | **POST** /v2/products/offers | After a call to GET &#39;v2/products/offers&#39; this endpoint should be called with the              ChannelReference of the products that are successfully updated.              Please see &#39;v2/products/data&#39; and &#39;v2/products/data&#39; for documentation.
*ProductApi* | [**productCreate**](docs/ProductApi.md#productCreate) | **POST** /v2/products | Create a product. The parent serves as the &#39;base&#39; product of the children.              For example, the children could be different sizes or colors of the parent product.              For channels where every size and color are different products this does not make any difference              (the children will just be sent separately, while ignoring the parent).              But there are channels where the parent and the children need to be sent together, for example              when there is one product with a list of sizes. In this case all the product information is retrieved              from the parent product while the size list is generated from the children.                            Note that the parent itself is a &#39;blueprint&#39; of the child products and we do our best to make sure it              does not end up on the marketplaces itself. Only the children can be purchased.                            It&#39;s not possible to nest parent and children more than one level (A parent can have many children,              but any child cannot itself also have children).                            The supplied MerchantProductReference needs to be unique.
*ProductApi* | [**productDelete**](docs/ProductApi.md#productDelete) | **DELETE** /v2/products/{merchantReference} | Deactivate a product based on the merchant reference.              Note that we do not really delete a product, as the product              might still be referenced by orders etc.
*ProductApi* | [**productGet**](docs/ProductApi.md#productGet) | **GET** /v2/products/{merchantReference} | Retrieve a product based on the merchant reference.
*ProductApi* | [**productGetDataChanges**](docs/ProductApi.md#productGetDataChanges) | **GET** /v2/products/data | Get all products which have changes since the post http call to POST &#39;v2/products/data&#39;.              The response contains the products which should be created, updated or removed from the channel.              After the products have been received and processed successfully &#39;v2/products/data&#39; should              be called with the merchant references of the products which have been processed (see POST &#39;v2/products/data&#39;).               ChannelEnginewill save this information to make sure that the next call to GET &#39;v2/products/data&#39; only returns the              products that really have changes (and therefore should be created, updated or deleted).              A channel willing to integrate with channelengine should therefore only do the following things:                  1. Periodically poll &#39;v2/products/data&#39; for changes.                  2. If any products are returned, save, update or remove these products.                  3. Send the merchant references of the products that have succesfully been processed                  in step 2 to POST &#39;v2/products/data&#39;.                               These three simple steps will make sure that the products on the channel will be synchronized               with the products on ChannelEngine. ChannelEngine will use the API key to determine the customer              whose products should be returned.
*ProductApi* | [**productGetOfferChanges**](docs/ProductApi.md#productGetOfferChanges) | **GET** /v2/products/offers | GET &#39;v2/products/offers&#39; and POST &#39;v2/products/offers&#39; closely resemble GET &#39;v2/products/data&#39; and POST &#39;v2/products/data&#39;. See the &#39;v2/products/data&#39;              endpoints for documentation. The difference between both endpoints is that &#39;v2/products/offers&#39; only returns Price and Stock updates and can (and should)              therefore be called more often to keep this information (which might change frequently) up to date.
*ReturnApi* | [**returnCreate**](docs/ReturnApi.md#returnCreate) | **POST** /v2/returns | Mark (part of) an order as returned by the customer
*ReturnApi* | [**returnGet**](docs/ReturnApi.md#returnGet) | **GET** /v2/returns/{merchantReference} | Get a return by its merchant reference.
*ReturnApi* | [**returnIndex**](docs/ReturnApi.md#returnIndex) | **GET** /v2/returns | Gets all returns created since the supplied date.
*ShipmentApi* | [**shipmentCreate**](docs/ShipmentApi.md#shipmentCreate) | **POST** /v2/shipments | Mark (part of) an order as shipped.
*ShipmentApi* | [**shipmentGet**](docs/ShipmentApi.md#shipmentGet) | **GET** /v2/shipments/{merchantReference} | Get a shipment by its merchant reference.
*ShipmentApi* | [**shipmentIndex**](docs/ShipmentApi.md#shipmentIndex) | **GET** /v2/shipments | Gets all shipments created since the supplied date.


## Documentation for Models

 - [AcknowledgementLineViewModel](docs/AcknowledgementLineViewModel.md)
 - [Address](docs/Address.md)
 - [BackOrderLineViewModel](docs/BackOrderLineViewModel.md)
 - [BackOrderViewModel](docs/BackOrderViewModel.md)
 - [CancellationLineViewModel](docs/CancellationLineViewModel.md)
 - [CancellationViewModel](docs/CancellationViewModel.md)
 - [CreateOrderLineViewModel](docs/CreateOrderLineViewModel.md)
 - [CreateOrderViewModel](docs/CreateOrderViewModel.md)
 - [Object](docs/Object.md)
 - [OfferViewModel](docs/OfferViewModel.md)
 - [OrderAcknowledgementViewModel](docs/OrderAcknowledgementViewModel.md)
 - [OrderLineViewModel](docs/OrderLineViewModel.md)
 - [OrderViewModel](docs/OrderViewModel.md)
 - [ProcessedChanges](docs/ProcessedChanges.md)
 - [ProductChangesViewModel](docs/ProductChangesViewModel.md)
 - [ProductRequestViewModel](docs/ProductRequestViewModel.md)
 - [ProductResponseViewModel](docs/ProductResponseViewModel.md)
 - [ProductViewModel](docs/ProductViewModel.md)
 - [References](docs/References.md)
 - [ReturnLineViewModel](docs/ReturnLineViewModel.md)
 - [ReturnViewModel](docs/ReturnViewModel.md)
 - [ShipmentLineViewModel](docs/ShipmentLineViewModel.md)
 - [ShipmentMethod](docs/ShipmentMethod.md)
 - [ShipmentViewModel](docs/ShipmentViewModel.md)


## Documentation for Authorization

Authentication schemes defined for the API:
### apikey

- **Type**: API key
- **API key parameter name**: apikey
- **Location**: URL query string


## Recommendation

It's recommended to create an instance of `ApiClient` per thread in a multithreaded environment to avoid any potential issue.

## Author



