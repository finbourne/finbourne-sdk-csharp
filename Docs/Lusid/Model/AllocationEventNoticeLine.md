# Finbourne.Sdk.Lusid.Model.AllocationEventNoticeLine

One line of a notice: an amount allocated to the partner under an ILPA transaction type.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **IlpaTransactionType** | **string** | Required | The ILPA transaction type of the line. |
| **Component** | **string** | Optional | The allocation event component the line is for. |
| **InsideFund** | **bool** | Required | Whether the line moves capital inside the fund, as opposed to a fee or expense outside it. |
| **Amount** | **decimal** | Required | The amount of the line. |
| **UnfundedImpact** | **decimal** | Required | The effect of the line on the partner&#39;s unfunded commitment. |
| **RecallableUntil** | **DateTimeOffset?** | Optional | The date until which a recallable distribution may be recalled, or null. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationEventNoticeLine(
    ilpaTransactionType: "...",  // required — The ILPA transaction type of the line.
    component: "...",  // optional — The allocation event component the line is for.
    insideFund: true,  // required — Whether the line moves capital inside the fund, as opposed to a fee or expense outside it.
    amount: 0.0d,  // required — The amount of the line.
    unfundedImpact: 0.0d,  // required — The effect of the line on the partner&#39;s unfunded commitment.
    recallableUntil: DateTimeOffset.Now  // optional — The date until which a recallable distribution may be recalled, or null.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationEventNoticeLine>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

