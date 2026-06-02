# Finbourne.Sdk.Lusid.Model.PreviousValuationPoint

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ValuationPointCode** | **string** | Required | The code of the Valuation Point. |
| **Name** | **string** | Optional | Identifiable Name assigned to the Valuation Point. |
| **EffectiveAt** | **DateTimeOffset** | Required | The effective time of the Valuation Point. |
| **QueryAsAt** | **DateTimeOffset** | Required | The AsAt time of the Valuation Point. This is the AsAt time that will be used when requests are made using the entry. |
| **HoldingsAsAt** | **DateTimeOffset** | Optional | The AsAt time used for building holdings in the Valuation Point. |
| **ValuationAsAt** | **DateTimeOffset** | Optional | The AsAt time used for performing valuations in the Valuation Point. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PreviousValuationPoint(
    valuationPointCode: "...",  // required — The code of the Valuation Point.
    name: "...",  // optional — Identifiable Name assigned to the Valuation Point.
    effectiveAt: DateTimeOffset.Now,  // required — The effective time of the Valuation Point.
    queryAsAt: DateTimeOffset.Now,  // required — The AsAt time of the Valuation Point. This is the AsAt time that will be used when requests are made using the entry.
    holdingsAsAt: DateTimeOffset.Now,  // optional — The AsAt time used for building holdings in the Valuation Point.
    valuationAsAt: DateTimeOffset.Now  // optional — The AsAt time used for performing valuations in the Valuation Point.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PreviousValuationPoint>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

