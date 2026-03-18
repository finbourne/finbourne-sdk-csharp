# Finbourne.Sdk.Lusid.Model.PlaceBlocksRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Requests** | [List&lt;PlacementRequest&gt;](PlacementRequest.md) | Required | A collection of PlacementRequest. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PlaceBlocksRequest(
    requests: new List<PlacementRequest>()  // required — A collection of PlacementRequest.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PlaceBlocksRequest>(json);
```


## Related Models

- [PlacementRequest](PlacementRequest.md) — used in `Requests`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

