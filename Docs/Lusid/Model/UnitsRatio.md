# Finbourne.Sdk.Lusid.Model.UnitsRatio

The number of units you have after the event (output) for a given number of units you have prior to the event (input).
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Input** | **decimal** | Required | Input amount.  Denominator of the Ratio |
| **Output** | **decimal** | Required | Output amount. Numerator of the Ratio |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UnitsRatio(
    input: 0.0d,  // required — Input amount.  Denominator of the Ratio
    output: 0.0d  // required — Output amount. Numerator of the Ratio
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UnitsRatio>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

