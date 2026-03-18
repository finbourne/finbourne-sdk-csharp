# Finbourne.Sdk.Lusid.Model.LevelStep

Item which is stepped in level/quantity.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Date** | **DateTimeOffset** | Required | The date from which the level should apply. |
| **Quantity** | **decimal** | Required | The quantity which is applied. This might be an absolute, percentage, fractional or other value. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new LevelStep(
    date: DateTimeOffset.Now,  // required — The date from which the level should apply.
    quantity: 0.0d  // required — The quantity which is applied. This might be an absolute, percentage, fractional or other value.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LevelStep>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

