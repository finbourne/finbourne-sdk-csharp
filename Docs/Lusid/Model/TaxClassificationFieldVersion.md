# Finbourne.Sdk.Lusid.Model.TaxClassificationFieldVersion

One stored value of a classification input or override and the bitemporal window it held for.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Field** | **string** | Required | The name of the classification input or override the version belongs to. |
| **Value** | **string** | Optional | The value of the field over the version&#39;s effective and asAt window. |
| **EffectiveFrom** | **DateTimeOffset** | Required | The start of the effective window the value applies from. |
| **EffectiveUntil** | **DateTimeOffset** | Required | The end of the effective window the value applies until. |
| **AsAtFrom** | **DateTimeOffset** | Required | The asAt time the value was recorded. |
| **AsAtUntil** | **DateTimeOffset?** | Optional | The asAt time the value was superseded, if it has been. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TaxClassificationFieldVersion(
    field: "...",  // required — The name of the classification input or override the version belongs to.
    value: "...",  // optional — The value of the field over the version&#39;s effective and asAt window.
    effectiveFrom: DateTimeOffset.Now,  // required — The start of the effective window the value applies from.
    effectiveUntil: DateTimeOffset.Now,  // required — The end of the effective window the value applies until.
    asAtFrom: DateTimeOffset.Now,  // required — The asAt time the value was recorded.
    asAtUntil: DateTimeOffset.Now  // optional — The asAt time the value was superseded, if it has been.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaxClassificationFieldVersion>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

