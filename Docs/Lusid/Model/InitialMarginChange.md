# Finbourne.Sdk.Lusid.Model.InitialMarginChange

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **WePostBefore** | **decimal** | Required | What we must post to the set today, after the threshold. |
| **WePostAfter** | **decimal** | Required | What we would post to the set after the move, after the threshold. |
| **TheyPostBefore** | **decimal?** | Optional | What the counterparty must post today. Null where the run does not know it, as under SIMM without their sensitivities. |
| **TheyPostAfter** | **decimal?** | Optional | What the counterparty would post after the move. Null where the run does not know it. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InitialMarginChange(
    wePostBefore: 0.0d,  // required — What we must post to the set today, after the threshold.
    wePostAfter: 0.0d,  // required — What we would post to the set after the move, after the threshold.
    theyPostBefore: 0.0d,  // optional — What the counterparty must post today. Null where the run does not know it, as under SIMM without their sensitivities.
    theyPostAfter: 0.0d  // optional — What the counterparty would post after the move. Null where the run does not know it.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InitialMarginChange>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

