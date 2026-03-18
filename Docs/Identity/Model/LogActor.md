# Finbourne.Sdk.Identity.Model.LogActor

Represents a LogActor resource in the Okta API
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **string** | Optional | *No description available.* |
| **Type** | **string** | Optional | *No description available.* |
| **AlternateId** | **string** | Optional | *No description available.* |
| **DisplayName** | **string** | Optional | *No description available.* |
| **DetailEntry** | **Dictionary&lt;string, Object&gt;** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new LogActor(
    id: "...",  // optional
    type: "...",  // optional
    alternateId: "...",  // optional
    displayName: "...",  // optional
    detailEntry:   // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LogActor>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

