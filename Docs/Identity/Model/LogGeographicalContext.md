# Finbourne.Sdk.Identity.Model.LogGeographicalContext

Represents a LogGeographicalContext resource in the Okta API
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **City** | **string** | Optional | *No description available.* |
| **State** | **string** | Optional | *No description available.* |
| **Country** | **string** | Optional | *No description available.* |
| **PostalCode** | **string** | Optional | *No description available.* |
| **Geolocation** | [LogGeolocation](LogGeolocation.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new LogGeographicalContext(
    city: "...",  // optional
    state: "...",  // optional
    country: "...",  // optional
    postalCode: "...",  // optional
    geolocation: new LogGeolocation(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LogGeographicalContext>(json);
```

- [LogGeolocation](LogGeolocation.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

