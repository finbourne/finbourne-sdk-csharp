# Finbourne.Sdk.Horizon.Model.ReplayOptions

Optional parameters for replay operations.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **OverridePublicationStatus** | **string** | Optional | Override publication status for all transactions (e.g., force as \&quot;New\&quot;). |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new ReplayOptions(
    overridePublicationStatus: "..."  // optional — Override publication status for all transactions (e.g., force as \&quot;New\&quot;).
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ReplayOptions>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

