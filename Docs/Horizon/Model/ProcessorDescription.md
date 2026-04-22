# Finbourne.Sdk.Horizon.Model.ProcessorDescription

Represents a processor in the Horizon integration system.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | *No description available.* |
| **DisplayName** | **string** | Required | *No description available.* |
| **Description** | **string** | Required | *No description available.* |
| **Category** | **string** | Required | *No description available.* |
| **IsActive** | **bool** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new ProcessorDescription(
    name: "...",  // required
    displayName: "...",  // required
    description: "...",  // required
    category: "...",  // required
    isActive: true  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ProcessorDescription>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

