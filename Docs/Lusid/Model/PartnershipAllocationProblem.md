# Finbourne.Sdk.Lusid.Model.PartnershipAllocationProblem

Why the period cannot be allocated to the partners as it stands. The read reports it; the allocation run and the  acceptance refuse with the same failure.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | The problem. Available values: AllocationRulesNotConfigured, UnbucketedPnl, UnknownDistributionCharacter. |
| **Message** | **string** | Required | What is wrong and what to change, naming the accounts, amounts and values concerned. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PartnershipAllocationProblem(
    code: "...",  // required — The problem. Available values: AllocationRulesNotConfigured, UnbucketedPnl, UnknownDistributionCharacter.
    message: "..."  // required — What is wrong and what to change, naming the accounts, amounts and values concerned.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PartnershipAllocationProblem>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

