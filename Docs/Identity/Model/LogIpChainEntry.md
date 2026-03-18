# Finbourne.Sdk.Identity.Model.LogIpChainEntry

Represents a LogIpChainEntry resource in the Okta API
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Ip** | **string** | Optional | *No description available.* |
| **GeographicalContext** | [LogGeographicalContext](LogGeographicalContext.md) | Optional | *No description available.* |
| **VarVersion** | **string** | Optional | *No description available.* |
| **Source** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new LogIpChainEntry(
    ip: "...",  // optional
    geographicalContext: new LogGeographicalContext(...),  // optional
    varVersion: "...",  // optional
    source: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LogIpChainEntry>(json);
```

- [LogGeographicalContext](LogGeographicalContext.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

