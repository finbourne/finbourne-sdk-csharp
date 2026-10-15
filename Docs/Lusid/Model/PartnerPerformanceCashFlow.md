# Finbourne.Sdk.Lusid.Model.PartnerPerformanceCashFlow

One dated cash flow the net IRR was solved from, signed from the partner's point of view.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Date** | **DateTimeOffset** | Required | The date of the cash flow. |
| **Amount** | **decimal** | Required | The amount of the cash flow, negative for contributions and positive for distributions and the residual value. |
| **Kind** | **string** | Required | The kind of cash flow: Contribution, Distribution or ResidualValue. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PartnerPerformanceCashFlow(
    date: DateTimeOffset.Now,  // required — The date of the cash flow.
    amount: 0.0d,  // required — The amount of the cash flow, negative for contributions and positive for distributions and the residual value.
    kind: "..."  // required — The kind of cash flow: Contribution, Distribution or ResidualValue.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PartnerPerformanceCashFlow>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

