# Finbourne.Sdk.Lusid.Model.FundStructureDriftMateriality

How much ownership drift a Fund Structure member tolerates on the members it holds through an instrument.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **WarnAmount** | **decimal?** | Optional | The misallocated P&amp;L, in base currency, above which the valuation point carries a warning naming the holder, the held member and both shares. Optional; unset means never warn. |
| **RefuseAmount** | **decimal?** | Optional | The misallocated P&amp;L, in base currency, above which the P&amp;L flow is refused until the sharing percentage is corrected. Must not be less than the warning amount. Optional; unset means never refuse. A share bought from another investor at a premium or a discount shows as drift however correct the sharing percentage. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundStructureDriftMateriality(
    warnAmount: 0.0d,  // optional — The misallocated P&amp;L, in base currency, above which the valuation point carries a warning naming the holder, the held member and both shares. Optional; unset means never warn.
    refuseAmount: 0.0d  // optional — The misallocated P&amp;L, in base currency, above which the P&amp;L flow is refused until the sharing percentage is corrected. Must not be less than the warning amount. Optional; unset means never refuse. A share bought from another investor at a premium or a discount shows as drift however correct the sharing percentage.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundStructureDriftMateriality>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

