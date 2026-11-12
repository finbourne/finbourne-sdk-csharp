# Finbourne.Sdk.Lusid.Model.CollateralOptimisationTerms

When a cheaper arrangement for the agreement's trades is worth recommending.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **NovationCost** | **decimal** | Required | The one-off cost of novating trades away from the counterparty, in the agreement&#39;s base currency. At least 0. |
| **MinSavingPerDay** | **decimal** | Required | A change saving no more than this a day is not recommended. At least 0. |
| **MaxPaybackDays** | **int** | Required | A change whose one-off cost takes longer than this many days to earn back is not recommended. At least 0. |
| **MaxPerAgreement** | **int** | Required | The most recommendations kept for the agreement, best first. Zero means no cap. At least 0. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CollateralOptimisationTerms(
    novationCost: 0.0d,  // required — The one-off cost of novating trades away from the counterparty, in the agreement&#39;s base currency. At least 0.
    minSavingPerDay: 0.0d,  // required — A change saving no more than this a day is not recommended. At least 0.
    maxPaybackDays: 0,  // required — A change whose one-off cost takes longer than this many days to earn back is not recommended. At least 0.
    maxPerAgreement: 0  // required — The most recommendations kept for the agreement, best first. Zero means no cap. At least 0.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CollateralOptimisationTerms>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

