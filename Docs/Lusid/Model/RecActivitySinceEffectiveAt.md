# Finbourne.Sdk.Lusid.Model.RecActivitySinceEffectiveAt

A per-side exclusive lower bound on an activity window's effective range.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Left** | **DateTimeOffset** | Required | The exclusive lower bound for the left side. Activity effective at exactly this datetime falls outside the window. |
| **Right** | **DateTimeOffset** | Required | The exclusive lower bound for the right side. Activity effective at exactly this datetime falls outside the window. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecActivitySinceEffectiveAt(
    left: DateTimeOffset.Now,  // required — The exclusive lower bound for the left side. Activity effective at exactly this datetime falls outside the window.
    right: DateTimeOffset.Now  // required — The exclusive lower bound for the right side. Activity effective at exactly this datetime falls outside the window.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecActivitySinceEffectiveAt>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

