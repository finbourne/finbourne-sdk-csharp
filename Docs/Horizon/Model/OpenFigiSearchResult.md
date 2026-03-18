# Finbourne.Sdk.Horizon.Model.OpenFigiSearchResult

Response coming back from a search request to OpenFIGI
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Results** | [List&lt;OpenFigiData&gt;](OpenFigiData.md) | Required | Enumerable list of OpenFIGI results |
| **PermIdUri** | **string** | Optional | URI of the related PermID response, if requested |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new OpenFigiSearchResult(
    results: new List<OpenFigiData>(),  // required — Enumerable list of OpenFIGI results
    permIdUri: "..."  // optional — URI of the related PermID response, if requested
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OpenFigiSearchResult>(json);
```


## Related Models

- [OpenFigiData](OpenFigiData.md) — used in `Results`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

