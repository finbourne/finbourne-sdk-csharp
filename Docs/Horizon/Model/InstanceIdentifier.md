# Finbourne.Sdk.Horizon.Model.InstanceIdentifier

Identifies a single instance of an integration.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **string** | Required | Instance identifier. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new InstanceIdentifier(
    id: "..."  // required — Instance identifier.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InstanceIdentifier>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

