# Finbourne.Sdk.Lusid.Model.FundStructureEdge

A link from one member of a Fund Structure to another, and how that link is held.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **From** | **string** | Required | The node code of the member that holds the link: the investor or the owner. |
| **To** | [FundStructureEdgeTarget](FundStructureEdgeTarget.md) | Required | *No description available.* |
| **LinkageType** | **string** | Optional | How the link is held. DedicatedShareClass (the default) means the source invests into a share class of the target; DirectEquityInstrument, GPInterest, LPInterest and CarryInterest mean the source holds that interest in the target through the instrument in viaInstrumentId. Available values: DedicatedShareClass, DirectEquityInstrument, GPInterest, LPInterest, CarryInterest. |
| **ViaInstrumentId** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **SharingPercentage** | **decimal?** | Optional | The holder&#39;s ILPA sharing percentage in the target member, adjusted for transfers and equalisation but not reduced by ordinary distributions. Between 0 and 1 inclusive; the percentages declared into any one member must sum to no more than 1. Defaults to 1 (sole ownership) when not supplied. A value of 0 records a full exit: keep the edge and set it to 0 from the date the interest ended, so that the change in percentage from one version of the structure to the next tells the P&amp;L flow what was disposed of. Each disposal or acquisition trade of the holder&#39;s needs its own version of the structure, effective on that trade&#39;s date: proceeds received on a date with no change in percentage are taken as a distribution on the retained interest, not a disposal. A change in percentage with no trade of the holder&#39;s on its date takes effect at the holder&#39;s next transaction on the member or period close, whichever comes first. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundStructureEdge(
    from: "...",  // required — The node code of the member that holds the link: the investor or the owner.
    to: new FundStructureEdgeTarget(...),  // required
    linkageType: "...",  // optional — How the link is held. DedicatedShareClass (the default) means the source invests into a share class of the target; DirectEquityInstrument, GPInterest, LPInterest and CarryInterest mean the source holds that interest in the target through the instrument in viaInstrumentId. Available values: DedicatedShareClass, DirectEquityInstrument, GPInterest, LPInterest, CarryInterest.
    viaInstrumentId: new ResourceId(...),  // optional
    sharingPercentage: 0.0d  // optional — The holder&#39;s ILPA sharing percentage in the target member, adjusted for transfers and equalisation but not reduced by ordinary distributions. Between 0 and 1 inclusive; the percentages declared into any one member must sum to no more than 1. Defaults to 1 (sole ownership) when not supplied. A value of 0 records a full exit: keep the edge and set it to 0 from the date the interest ended, so that the change in percentage from one version of the structure to the next tells the P&amp;L flow what was disposed of. Each disposal or acquisition trade of the holder&#39;s needs its own version of the structure, effective on that trade&#39;s date: proceeds received on a date with no change in percentage are taken as a distribution on the retained interest, not a disposal. A change in percentage with no trade of the holder&#39;s on its date takes effect at the holder&#39;s next transaction on the member or period close, whichever comes first.
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

