# Finbourne.Sdk.Lusid.Model.FundStructureNode

A node in a Fund Structure, representing a Fund and its role within the structure.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **NodeCode** | **string** | Required | A unique identifier for this node within the Fund Structure. |
| **FundScope** | **string** | Required | The scope of the Fund referenced by this node. |
| **FundCode** | **string** | Required | The code of the Fund referenced by this node. |
| **Role** | **string** | Required | The role of this node within the structure. Available values: Master, Feeder. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundStructureNode(
    nodeCode: "...",  // required — A unique identifier for this node within the Fund Structure.
    fundScope: "...",  // required — The scope of the Fund referenced by this node.
    fundCode: "...",  // required — The code of the Fund referenced by this node.
    role: "..."  // required — The role of this node within the structure. Available values: Master, Feeder.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundStructureNode>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

