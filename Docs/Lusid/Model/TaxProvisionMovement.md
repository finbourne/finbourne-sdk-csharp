# Finbourne.Sdk.Lusid.Model.TaxProvisionMovement

The movement in a fund's deferred tax provision between the previous valuation point and this one,  split into the realised gains crystallised in the period, the change in the unrealised position,  the effect of a change in the applied rate and the offset from losses brought forward.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Realised** | **decimal** | Required | The part of the movement that is due to gains realised in the period. |
| **UnrealisedChange** | **decimal** | Required | The part of the movement that is due to the change in the unrealised position. |
| **RateChange** | **decimal** | Required | The part of the movement that is due to a change in the applied rate. |
| **LossOffset** | **decimal** | Required | The part of the movement that is due to losses brought forward being offset against gains. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new TaxProvisionMovement(
    realised: 0.0d,  // required — The part of the movement that is due to gains realised in the period.
    unrealisedChange: 0.0d,  // required — The part of the movement that is due to the change in the unrealised position.
    rateChange: 0.0d,  // required — The part of the movement that is due to a change in the applied rate.
    lossOffset: 0.0d  // required — The part of the movement that is due to losses brought forward being offset against gains.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TaxProvisionMovement>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

