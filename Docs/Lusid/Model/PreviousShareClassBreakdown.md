# Finbourne.Sdk.Lusid.Model.PreviousShareClassBreakdown

The data for a Share Class at the previous valuation point.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Nav** | [PreviousNAV](PreviousNAV.md) | Required | *No description available.* |
| **Unitisation** | [UnitisationData](UnitisationData.md) | Optional | *No description available.* |
| **ShareClassToFundFxRate** | **decimal** | Required | The fx rate from the Share Class currency to the fund currency at this valuation point. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PreviousShareClassBreakdown(
    nav: new PreviousNAV(...),  // required
    unitisation: new UnitisationData(...),  // optional
    shareClassToFundFxRate: 0.0d  // required — The fx rate from the Share Class currency to the fund currency at this valuation point.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PreviousShareClassBreakdown>(json);
```


## Related Models

- [PreviousNAV](PreviousNAV.md)
- [UnitisationData](UnitisationData.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

