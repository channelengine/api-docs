
# ReturnViewModel

## Properties
Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**merchantReturnReference** | **String** |  |  [optional]
**merchantOrderReference** | **String** |  |  [optional]
**channelOrderReference** | **String** |  |  [optional]
**channelReturnReference** | **String** |  |  [optional]
**status** | [**StatusEnum**](#StatusEnum) |  |  [optional]
**reason** | [**ReasonEnum**](#ReasonEnum) |  |  [optional]
**customerComment** | **String** |  |  [optional]
**merchantComment** | **String** |  |  [optional]
**refundInclVat** | **Double** |  |  [optional]
**refundExclVat** | **Double** |  |  [optional]
**lines** | [**List&lt;ReturnLineViewModel&gt;**](ReturnLineViewModel.md) |  |  [optional]


<a name="StatusEnum"></a>
## Enum: StatusEnum
Name | Value
---- | -----
ON_THE_WAY | &quot;ON_THE_WAY&quot;
ACCEPTED | &quot;ACCEPTED&quot;
REJECTED | &quot;REJECTED&quot;


<a name="ReasonEnum"></a>
## Enum: ReasonEnum
Name | Value
---- | -----
PRODUCT_DEFECT | &quot;PRODUCT_DEFECT&quot;
PRODUCT_UNSATISFACTORY | &quot;PRODUCT_UNSATISFACTORY&quot;
REFUSED | &quot;REFUSED&quot;
REFUSED_DAMAGED | &quot;REFUSED_DAMAGED&quot;
WRONG_ADDRESS | &quot;WRONG_ADDRESS&quot;
NOT_COLLECTED | &quot;NOT_COLLECTED&quot;
OTHER | &quot;OTHER&quot;



