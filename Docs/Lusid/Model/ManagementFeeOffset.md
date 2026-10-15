# Finbourne.Sdk.Lusid.Model.ManagementFeeOffset

A fee income the manager has earned elsewhere that offsets the management fee.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **SourceRef** | **string** | Required | A reference to the fee income being offset. |
| **Amount** | **decimal** | Required | The amount of fee income received. |
| **OffsetPercentage** | **decimal** | Required | The fraction of the fee income that offsets the management fee, between 0 and 1. |
| **Deal** | **string** | Optional | For a deal-linked offset, the deal the fee income relates to. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ManagementFeeOffset(
    sourceRef: "...",  // required — A reference to the fee income being offset.
    amount: 0.0d,  // required — The amount of fee income received.
    offsetPercentage: 0.0d,  // required — The fraction of the fee income that offsets the management fee, between 0 and 1.
    deal: "..."  // optional — For a deal-linked offset, the deal the fee income relates to.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ManagementFeeOffset>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

