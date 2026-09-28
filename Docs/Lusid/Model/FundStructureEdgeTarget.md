# Finbourne.Sdk.Lusid.Model.FundStructureEdgeTarget

The member a link points at, and for a dedicated share class link the share class on that member.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Node** | **string** | Required | The node code of the member the link points at. |
| **ShareClassShortCode** | **string** | Optional | The short code of the share class on the target member that the source invests into. Required for a DedicatedShareClass link and not allowed on any other. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundStructureEdgeTarget(
    node: "...",  // required — The node code of the member the link points at.
    shareClassShortCode: "..."  // optional — The short code of the share class on the target member that the source invests into. Required for a DedicatedShareClass link and not allowed on any other.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundStructureEdgeTarget>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

