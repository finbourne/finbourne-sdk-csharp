# Finbourne.Sdk.Lusid.Model.FundStructureCloseResult

The outcome of closing a fund structure: one step per member in the order they were closed.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StructureId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **ValuationPointCode** | **string** | Required | The code of the valuation point to finalise on every member fund. |
| **Steps** | [List&lt;FundStructureCloseStep&gt;](FundStructureCloseStep.md) | Required | The finalisation of each member, in the order attempted. |
| **Completed** | **bool** | Required | Whether every member finalised. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundStructureCloseResult(
    structureId: new ResourceId(...),  // required
    valuationPointCode: "...",  // required — The code of the valuation point to finalise on every member fund.
    steps: new List<FundStructureCloseStep>(),  // required — The finalisation of each member, in the order attempted.
    completed: true  // required — Whether every member finalised.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundStructureCloseResult>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [FundStructureCloseStep](FundStructureCloseStep.md) — used in `Steps`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

