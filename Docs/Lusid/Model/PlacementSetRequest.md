# Finbourne.Sdk.Lusid.Model.PlacementSetRequest

A request to create or update multiple Placements.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Requests** | [List&lt;PlacementRequest&gt;](PlacementRequest.md) | Optional | A collection of PlacementRequests. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PlacementSetRequest(
    requests: new List<PlacementRequest>()  // optional — A collection of PlacementRequests.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PlacementSetRequest>(json);
```


## Related Models

- [PlacementRequest](PlacementRequest.md) — used in `Requests`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

