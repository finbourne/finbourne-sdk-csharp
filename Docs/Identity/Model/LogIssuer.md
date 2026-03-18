# Finbourne.Sdk.Identity.Model.LogIssuer

Represents a LogIssuer resource in the Okta API
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **string** | Optional | *No description available.* |
| **Type** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new LogIssuer(
    id: "...",  // optional
    type: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LogIssuer>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

