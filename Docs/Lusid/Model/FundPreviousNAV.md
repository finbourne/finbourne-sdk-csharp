# Finbourne.Sdk.Lusid.Model.FundPreviousNAV

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Amount** | **decimal** | Optional | The amount of the previous NAV. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundPreviousNAV(
    amount: 0.0d  // optional — The amount of the previous NAV.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundPreviousNAV>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

