# Finbourne.Sdk.Lusid.Model.WithholdingTaxRateSplit

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StopAtSourceRate** | **decimal** | Required | The rate withheld at source. |
| **IrrecoverableRate** | **decimal** | Required | The part of the country rate that cannot be recovered. |
| **ReliefAtSourceRate** | **decimal** | Required | The part of the country rate relieved at source. |
| **ReclaimableRate** | **decimal** | Required | The part of the rate withheld at source that can be reclaimed. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new WithholdingTaxRateSplit(
    stopAtSourceRate: 0.0d,  // required — The rate withheld at source.
    irrecoverableRate: 0.0d,  // required — The part of the country rate that cannot be recovered.
    reliefAtSourceRate: 0.0d,  // required — The part of the country rate relieved at source.
    reclaimableRate: 0.0d  // required — The part of the rate withheld at source that can be reclaimed.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<WithholdingTaxRateSplit>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

