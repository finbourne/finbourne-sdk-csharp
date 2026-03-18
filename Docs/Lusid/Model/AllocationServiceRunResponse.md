# Finbourne.Sdk.Lusid.Model.AllocationServiceRunResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Values** | [List&lt;ResourceId&gt;](ResourceId.md) | Optional | *No description available.* |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationServiceRunResponse(
    values: new List<ResourceId>(),  // optional
    failed: new ErrorDetail(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationServiceRunResponse>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ErrorDetail](ErrorDetail.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

