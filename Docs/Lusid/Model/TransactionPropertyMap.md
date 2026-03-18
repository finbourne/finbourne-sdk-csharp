# Finbourne.Sdk.Lusid.Model.TransactionPropertyMap

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PropertyKey** | **string** | Optional | The key that uniquely identifies the property. It has the format {domain}/{scope}/{code}. |
| **Value** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TransactionPropertyMap(
    propertyKey: "...",  // optional — The key that uniquely identifies the property. It has the format {domain}/{scope}/{code}.
    value: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TransactionPropertyMap>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

