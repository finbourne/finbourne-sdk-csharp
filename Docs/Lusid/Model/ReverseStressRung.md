# Finbourne.Sdk.Lusid.Model.ReverseStressRung

One evaluated factor and what the portfolio was worth under it.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Scale** | **decimal** | Optional | The factor the scenario&#39;s shifts were multiplied by. |
| **Value** | **decimal** | Optional | The value of the measure under the scaled scenario. |
| **Pnl** | **decimal** | Optional | The change from the unstressed value. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ReverseStressRung(
    scale: 0.0d,  // optional — The factor the scenario&#39;s shifts were multiplied by.
    value: 0.0d,  // optional — The value of the measure under the scaled scenario.
    pnl: 0.0d  // optional — The change from the unstressed value.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ReverseStressRung>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

