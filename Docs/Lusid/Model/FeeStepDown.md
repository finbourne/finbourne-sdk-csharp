# Finbourne.Sdk.Lusid.Model.FeeStepDown

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Trigger** | **string** | Required | Available values: EndOfInvestmentPeriod, Date, Closing. |
| **StepDownDate** | **DateTimeOffset?** | Optional | *No description available.* |
| **ClosingId** | **string** | Optional | *No description available.* |
| **Rate** | **decimal?** | Optional | *No description available.* |
| **Basis** | **string** | Optional | Available values: CommittedCapital, InvestedCapital, NetInvestedCapital, Nav. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FeeStepDown(
    trigger: "...",  // required — Available values: EndOfInvestmentPeriod, Date, Closing.
    stepDownDate: DateTimeOffset.Now,  // optional
    closingId: "...",  // optional
    rate: 0.0d,  // optional
    basis: "..."  // optional — Available values: CommittedCapital, InvestedCapital, NetInvestedCapital, Nav.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FeeStepDown>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

