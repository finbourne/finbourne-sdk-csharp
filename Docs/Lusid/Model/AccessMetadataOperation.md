# Finbourne.Sdk.Lusid.Model.AccessMetadataOperation

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Value** | [List&lt;AccessMetadataValue&gt;](AccessMetadataValue.md) | Required | *No description available.* |
| **Path** | **string** | Required | *No description available.* |
| **Op** | **string** | Required | The available values are: add, remove |
| **From** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AccessMetadataOperation(
    value: new List<AccessMetadataValue>(),  // required
    path: "...",  // required
    op: "...",  // required — The available values are: add, remove
    from: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AccessMetadataOperation>(json);
```


## Related Models

- [AccessMetadataValue](AccessMetadataValue.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

