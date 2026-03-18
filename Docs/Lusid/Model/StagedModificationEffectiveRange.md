# Finbourne.Sdk.Lusid.Model.StagedModificationEffectiveRange

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FromDate** | **DateTimeOffset** | Optional | The datetime that this requested change is effective from. |
| **UntilDate** | **DateTimeOffset** | Optional | The datetime that this requested change is effective until. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new StagedModificationEffectiveRange(
    fromDate: DateTimeOffset.Now,  // optional — The datetime that this requested change is effective from.
    untilDate: DateTimeOffset.Now  // optional — The datetime that this requested change is effective until.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<StagedModificationEffectiveRange>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

