# Finbourne.Sdk.Identity.Model.LogClientInfo

Represents a LogClientInfo resource in the Okta API
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **UserAgent** | [LogUserAgent](LogUserAgent.md) | Optional | *No description available.* |
| **Zone** | **string** | Optional | *No description available.* |
| **Device** | **string** | Optional | *No description available.* |
| **Id** | **string** | Optional | *No description available.* |
| **IpAddress** | **string** | Optional | *No description available.* |
| **GeographicalContext** | [LogGeographicalContext](LogGeographicalContext.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new LogClientInfo(
    userAgent: new LogUserAgent(...),  // optional
    zone: "...",  // optional
    device: "...",  // optional
    id: "...",  // optional
    ipAddress: "...",  // optional
    geographicalContext: new LogGeographicalContext(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LogClientInfo>(json);
```


## Related Models

- [LogUserAgent](LogUserAgent.md)
- [LogGeographicalContext](LogGeographicalContext.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

