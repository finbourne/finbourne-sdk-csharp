# Finbourne.Sdk.Lusid.Model.PreviousNAV

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Amount** | [ShareClassAmount](ShareClassAmount.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PreviousNAV(
    amount: new ShareClassAmount(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PreviousNAV>(json);
```


## Related Models

- [ShareClassAmount](ShareClassAmount.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

