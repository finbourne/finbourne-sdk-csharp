# Finbourne.Sdk.Lusid.Model.AllocationBasisRule

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Character** | **string** | Required | *No description available.* |
| **Basis** | **string** | Required | Available values: CommittedCapital, PaidInCapital, DealPaidIn. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationBasisRule(
    character: "...",  // required
    basis: "..."  // required — Available values: CommittedCapital, PaidInCapital, DealPaidIn.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationBasisRule>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

