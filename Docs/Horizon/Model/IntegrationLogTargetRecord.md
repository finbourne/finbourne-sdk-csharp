# Finbourne.Sdk.Horizon.Model.IntegrationLogTargetRecord

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RecordAction** | **string** | Optional | *No description available.* |
| **RecordType** | **string** | Optional | *No description available.* |
| **IdType** | **string** | Optional | *No description available.* |
| **IdValue** | **string** | Optional | *No description available.* |
| **AttributeName** | **string** | Optional | *No description available.* |
| **AttributeValue** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new IntegrationLogTargetRecord(
    recordAction: "...",  // optional
    recordType: "...",  // optional
    idType: "...",  // optional
    idValue: "...",  // optional
    attributeName: "...",  // optional
    attributeValue: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<IntegrationLogTargetRecord>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

