# Finbourne.Sdk.Lusid.Model.AllocationMapAllocation

One investor record's share of a resolved allocation event.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InvestorRecordId** | **string** | Optional | The investor record that receives the share. |
| **BasisValue** | **decimal?** | Optional | The basis value the pro rata share was weighted by. Absent for a fixed or excluded investor record. |
| **Weight** | **decimal** | Optional | The fraction of the remainder the investor record receives, or the fixed fraction of the whole amount for a FixedPercentage exception. |
| **Amount** | **decimal** | Optional | The amount allocated to the investor record. |
| **Treatment** | **string** | Optional | How the share was found. Derived means pro rata from the basis; FixedPercentage means off the top from an exception; Excluded means an exception removed the investor record and it receives nothing. Available values: Derived, FixedPercentage, Excluded. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationMapAllocation(
    investorRecordId: "...",  // optional — The investor record that receives the share.
    basisValue: 0.0d,  // optional — The basis value the pro rata share was weighted by. Absent for a fixed or excluded investor record.
    weight: 0.0d,  // optional — The fraction of the remainder the investor record receives, or the fixed fraction of the whole amount for a FixedPercentage exception.
    amount: 0.0d,  // optional — The amount allocated to the investor record.
    treatment: "..."  // optional — How the share was found. Derived means pro rata from the basis; FixedPercentage means off the top from an exception; Excluded means an exception removed the investor record and it receives nothing. Available values: Derived, FixedPercentage, Excluded.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationMapAllocation>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

