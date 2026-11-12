# Finbourne.Sdk.Lusid.Model.QualifyingInvestmentsObservation

The qualifying-investments test result for one scheme on one day.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Date** | **DateTimeOffset** | Required | The date the test was evaluated for. |
| **NonEquityPercent** | **decimal** | Required | The percentage of the scheme&#39;s assets that were qualifying (non-equity) investments on the date. |
| **IsBondFund** | **bool** | Required | Whether more than the threshold percentage of the scheme&#39;s assets were qualifying investments on the date, making it a bond fund. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new QualifyingInvestmentsObservation(
    date: DateTimeOffset.Now,  // required — The date the test was evaluated for.
    nonEquityPercent: 0.0d,  // required — The percentage of the scheme&#39;s assets that were qualifying (non-equity) investments on the date.
    isBondFund: true  // required — Whether more than the threshold percentage of the scheme&#39;s assets were qualifying investments on the date, making it a bond fund.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<QualifyingInvestmentsObservation>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

