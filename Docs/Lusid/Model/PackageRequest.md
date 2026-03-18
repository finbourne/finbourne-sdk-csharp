# Finbourne.Sdk.Lusid.Model.PackageRequest

A request to create or update a Package.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **OrderIds** | [List&lt;ResourceId&gt;](ResourceId.md) | Required | Related order ids. |
| **OrderInstructionIds** | [List&lt;ResourceId&gt;](ResourceId.md) | Required | Related order instruction ids. |
| **Properties** | [Dictionary&lt;string, PerpetualProperty&gt;](PerpetualProperty.md) | Optional | Client-defined properties associated with this execution. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PackageRequest(
    id: new ResourceId(...),  // required
    orderIds: new List<ResourceId>(),  // required — Related order ids.
    orderInstructionIds: new List<ResourceId>(),  // required — Related order instruction ids.
    properties: new PerpetualProperty(...)  // optional — Client-defined properties associated with this execution.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PackageRequest>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md) — used in `OrderIds`
- [ResourceId](ResourceId.md) — used in `OrderInstructionIds`
- [PerpetualProperty](PerpetualProperty.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

