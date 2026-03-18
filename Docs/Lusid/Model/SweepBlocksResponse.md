# Finbourne.Sdk.Lusid.Model.SweepBlocksResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Values** | [Dictionary&lt;string, ResourceId&gt;](ResourceId.md) | Optional | The identifiers of blocks which have been successfully swept, indexed by ephemeral request-lived id. |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | The identifiers of blocks that could not be swept, along with a reason for their failure. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SweepBlocksResponse(
    values: new ResourceId(...),  // optional — The identifiers of blocks which have been successfully swept, indexed by ephemeral request-lived id.
    failed: new ErrorDetail(...)  // optional — The identifiers of blocks that could not be swept, along with a reason for their failure.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SweepBlocksResponse>(json);
```


## Related Models

- [ResourceId](ResourceId.md) — used in `Values`
- [ErrorDetail](ErrorDetail.md) — used in `Failed`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

