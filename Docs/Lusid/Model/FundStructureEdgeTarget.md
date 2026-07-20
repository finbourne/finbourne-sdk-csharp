# Finbourne.Sdk.Lusid.Model.FundStructureEdgeTarget

The target of a Fund Structure edge, identifying the master node and share class the feeder invests into.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Node** | **string** | Required | The node code of the master node that is the target of this relationship. |
| **ShareClassShortCode** | **string** | Required | The short code of the share class on the master fund that the feeder invests into. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundStructureEdgeTarget(
    node: "...",  // required — The node code of the master node that is the target of this relationship.
    shareClassShortCode: "..."  // required — The short code of the share class on the master fund that the feeder invests into.
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

