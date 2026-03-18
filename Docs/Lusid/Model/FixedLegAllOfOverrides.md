# Finbourne.Sdk.Lusid.Model.FixedLegAllOfOverrides

Any overriding data for notionals, spreads or rates that would affect generation of a leg.  This supports the case where an amortisation schedule is given but otherwise generation is allowed as usual.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Amortization** | **List&lt;decimal&gt;** | Optional | *No description available.* |
| **Spreads** | **List&lt;decimal&gt;** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FixedLegAllOfOverrides(
    amortization: ,  // optional
    spreads:   // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FixedLegAllOfOverrides>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

