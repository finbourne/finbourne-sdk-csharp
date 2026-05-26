# Finbourne.Sdk.Horizon.Model.InstanceDestinations

record containing details of the destinations for an instance.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DestinationType** | **string** | Required | *No description available.* |
| **Name** | **string** | Required | *No description available.* |
| **DestinationPath** | **string** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new InstanceDestinations(
    destinationType: "...",  // required
    name: "...",  // required
    destinationPath: "..."  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InstanceDestinations>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

