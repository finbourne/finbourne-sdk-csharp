# Finbourne.Sdk.Lusid.Model.EffectiveRange

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FromDate** | **DateTimeOffset** | Optional | The effective from datetime that this range applies to. |
| **UntilDate** | **DateTimeOffset** | Optional | The effective from datetime that this range applies to. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new EffectiveRange(
    fromDate: DateTimeOffset.Now,  // optional — The effective from datetime that this range applies to.
    untilDate: DateTimeOffset.Now  // optional — The effective from datetime that this range applies to.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EffectiveRange>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

