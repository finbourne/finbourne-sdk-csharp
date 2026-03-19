# Finbourne.Sdk.Lusid.Model.TransactionFee

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Name** | **string** | Optional | The display name of the transaction fee. |
| **Description** | **string** | Optional | A description of the transaction fee. |
| **Calculation** | [FeeCalculationRequest](FeeCalculationRequest.md) | Optional | *No description available.* |
| **Condition** | **string** | Optional | The condition that the transaction must meet in order for the fee to be applied. |
| **TxnPropertyKey** | **string** | Optional | The property key to which the fee value will be applied and decorated onto the transaction. Must be in the &#39;Transaction&#39; property domain. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | A set of properties for the transaction fee. |
| **VarVersion** | [ModelVersion](ModelVersion.md) | Optional | *No description available.* |
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **IsActive** | **bool** | Optional | Indicates whether the transaction fee is currently active and should be applied to transactions. Optional when creating a transaction fee, defaults to true, if a value is not provided. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransactionFee(
    id: new ResourceId(...),  // optional
    name: "...",  // optional — The display name of the transaction fee.
    description: "...",  // optional — A description of the transaction fee.
    calculation: new FeeCalculationRequest(...),  // optional
    condition: "...",  // optional — The condition that the transaction must meet in order for the fee to be applied.
    txnPropertyKey: "...",  // optional — The property key to which the fee value will be applied and decorated onto the transaction. Must be in the &#39;Transaction&#39; property domain.
    properties: new Property(...),  // optional — A set of properties for the transaction fee.
    varVersion: new ModelVersion(...),  // optional
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    isActive: true,  // optional — Indicates whether the transaction fee is currently active and should be applied to transactions. Optional when creating a transaction fee, defaults to true, if a value is not provided.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransactionFee>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [FeeCalculationRequest](FeeCalculationRequest.md)
- [Property](Property.md) — used in `Properties`
- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

