# Finbourne.Sdk.Lusid.Model.SweepBlocksRequest

A request to sweep specified blocks.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BlockIds** | [Dictionary&lt;string, ResourceId&gt;](ResourceId.md) | Required | A dictionary mapping ephemeral identifiers, which live as long as the request, to specific blocks to sweep. |
| **LatestAllowableModificationTime** | **string** | Required | Timestamp or cut label which the  block or related entities must not have been updated after. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SweepBlocksRequest(
    blockIds: new ResourceId(...),  // required — A dictionary mapping ephemeral identifiers, which live as long as the request, to specific blocks to sweep.
    latestAllowableModificationTime: "..."  // required — Timestamp or cut label which the  block or related entities must not have been updated after.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SweepBlocksRequest>(json);
```


## Related Models

- [ResourceId](ResourceId.md) — used in `BlockIds`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

