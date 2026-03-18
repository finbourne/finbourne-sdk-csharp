# Finbourne.Sdk.Lusid.Model.SidesDefinitionRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Side** | **string** | Required | A unique label identifying the side definition. |
| **SideRequest** | [SideDefinitionRequest](SideDefinitionRequest.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SidesDefinitionRequest(
    side: "...",  // required — A unique label identifying the side definition.
    sideRequest: new SideDefinitionRequest(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SidesDefinitionRequest>(json);
```

- [SideDefinitionRequest](SideDefinitionRequest.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

