# Finbourne.Sdk.Lusid.Model.FundPartnerUnfundedReconciliationWarning

A soft warning on an unfunded commitment statement: the statement is still produced, with a caveat.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | The warning. PeriodStartsBeforeAdmission: the period opens before the partner was admitted, so the opening balances are zero and the admission commitment is counted as a commitment change. |
| **AdmittedOn** | **DateTimeOffset?** | Optional | For PeriodStartsBeforeAdmission, the date the partner was admitted to the fund. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundPartnerUnfundedReconciliationWarning(
    code: "...",  // required — The warning. PeriodStartsBeforeAdmission: the period opens before the partner was admitted, so the opening balances are zero and the admission commitment is counted as a commitment change.
    admittedOn: DateTimeOffset.Now  // optional — For PeriodStartsBeforeAdmission, the date the partner was admitted to the fund.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundPartnerUnfundedReconciliationWarning>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

