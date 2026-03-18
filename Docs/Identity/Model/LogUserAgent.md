# Finbourne.Sdk.Identity.Model.LogUserAgent

Represents a LogUserAgent resource in the Okta API
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RawUserAgent** | **string** | Optional | *No description available.* |
| **VarOperatingSystem** | **string** | Optional | *No description available.* |
| **Browser** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new LogUserAgent(
    rawUserAgent: "...",  // optional
    varOperatingSystem: "...",  // optional
    browser: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LogUserAgent>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

