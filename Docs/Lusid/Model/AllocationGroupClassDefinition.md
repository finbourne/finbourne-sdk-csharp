# Finbourne.Sdk.Lusid.Model.AllocationGroupClassDefinition

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ShareClassShortCode** | **string** | Required | A short code that uniquely identifies the share class within the Fund and is attached to the transaction. |
| **ApportionmentFactor** | **decimal?** | Optional | The weighting factor used for apportionment across this share class. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationGroupClassDefinition(
    shareClassShortCode: "...",  // required — A short code that uniquely identifies the share class within the Fund and is attached to the transaction.
    apportionmentFactor: 0.0d  // optional — The weighting factor used for apportionment across this share class.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationGroupClassDefinition>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

