# Finbourne.Sdk.Lusid.Model.AllocationMapBasisValue

The value one investor record is weighted by when an Allocation Map is resolved.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InvestorRecordId** | **string** | Required | The investor record the basis value belongs to. |
| **BasisValue** | **decimal** | Required | The value the investor record is weighted by, for example its commitment. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationMapBasisValue(
    investorRecordId: "...",  // required — The investor record the basis value belongs to.
    basisValue: 0.0d  // required — The value the investor record is weighted by, for example its commitment.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationMapBasisValue>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

