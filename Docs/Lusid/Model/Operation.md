# Finbourne.Sdk.Lusid.Model.Operation

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Value** | **Object** | Optional | *No description available.* |
| **Path** | **string** | Required | *No description available.* |
| **Op** | **string** | Required | *No description available.* |
| **From** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new Operation(
    value: ,  // optional
    path: "...",  // required
    op: "...",  // required
    from: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Operation>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

