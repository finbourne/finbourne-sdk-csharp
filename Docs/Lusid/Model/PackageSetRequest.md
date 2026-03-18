# Finbourne.Sdk.Lusid.Model.PackageSetRequest

A request to create or update multiple Packages.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Requests** | [List&lt;PackageRequest&gt;](PackageRequest.md) | Optional | A collection of PackageRequests. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PackageSetRequest(
    requests: new List<PackageRequest>()  // optional — A collection of PackageRequests.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PackageSetRequest>(json);
```


## Related Models

- [PackageRequest](PackageRequest.md) — used in `Requests`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

