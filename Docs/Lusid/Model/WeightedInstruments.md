# Finbourne.Sdk.Lusid.Model.WeightedInstruments

Class that models a set of instruments of which each has some quantity and can be identified by a unique label.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Instruments** | [List&lt;WeightedInstrument&gt;](WeightedInstrument.md) | Required | The instruments that are held in the set. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new WeightedInstruments(
    instruments: new List<WeightedInstrument>()  // required — The instruments that are held in the set.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WeightedInstruments>(json);
```


## Related Models

- [WeightedInstrument](WeightedInstrument.md) — used in `Instruments`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

