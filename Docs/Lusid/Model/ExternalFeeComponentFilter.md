# Finbourne.Sdk.Lusid.Model.ExternalFeeComponentFilter

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FilterId** | **string** | Required | *No description available.* |
| **Filter** | **string** | Required | *No description available.* |
| **AppliesTo** | **string** | Required | Available values: Undefined, PnLBucket, Fees. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ExternalFeeComponentFilter(
    filterId: "...",  // required
    filter: "...",  // required
    appliesTo: "..."  // required — Available values: Undefined, PnLBucket, Fees.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ExternalFeeComponentFilter>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

