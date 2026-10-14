# Finbourne.Sdk.Lusid.Model.AllocationPostingCounts

How many postings a plan writes on each side.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **LpSide** | **int** | Optional | The number of instrument events on investors&#39; lines. |
| **RollUps** | **int** | Optional | The number of roll-ups. |
| **FundSide** | **int** | Optional | The number of fund-side transactions. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationPostingCounts(
    lpSide: 0,  // optional — The number of instrument events on investors&#39; lines.
    rollUps: 0,  // optional — The number of roll-ups.
    fundSide: 0  // optional — The number of fund-side transactions.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationPostingCounts>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

