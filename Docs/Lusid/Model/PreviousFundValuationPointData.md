# Finbourne.Sdk.Lusid.Model.PreviousFundValuationPointData

The data for a Fund at the previous valuation point.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Nav** | [FundPreviousNAV](FundPreviousNAV.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PreviousFundValuationPointData(
    nav: new FundPreviousNAV(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PreviousFundValuationPointData>(json);
```


## Related Models

- [FundPreviousNAV](FundPreviousNAV.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

