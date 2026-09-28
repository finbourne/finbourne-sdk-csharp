# Finbourne.Sdk.Lusid.Model.FundStructureEdge

A link from one member of a Fund Structure to another, and how that link is held.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **From** | **string** | Required | The node code of the member that holds the link: the investor or the owner. |
| **To** | [FundStructureEdgeTarget](FundStructureEdgeTarget.md) | Required | *No description available.* |
| **LinkageType** | **string** | Optional | How the link is held. DedicatedShareClass (the default) means the source invests into a share class of the target; DirectEquityInstrument, GPInterest, LPInterest and CarryInterest mean the source holds that interest in the target through the instrument in viaInstrumentId. Available values: DedicatedShareClass, DirectEquityInstrument, GPInterest, LPInterest, CarryInterest. |
| **ViaInstrumentId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundStructureEdge(
    from: "...",  // required — The node code of the member that holds the link: the investor or the owner.
    to: new FundStructureEdgeTarget(...),  // required
    linkageType: "...",  // optional — How the link is held. DedicatedShareClass (the default) means the source invests into a share class of the target; DirectEquityInstrument, GPInterest, LPInterest and CarryInterest mean the source holds that interest in the target through the instrument in viaInstrumentId. Available values: DedicatedShareClass, DirectEquityInstrument, GPInterest, LPInterest, CarryInterest.
    viaInstrumentId: new ResourceId(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundStructureEdge>(json);
```

- [FundStructureEdgeTarget](FundStructureEdgeTarget.md)
- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

