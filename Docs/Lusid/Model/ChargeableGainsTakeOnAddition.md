# Finbourne.Sdk.Lusid.Model.ChargeableGainsTakeOnAddition

One acquisition added to a taken-on 1982 holding since 31 March 1982, carried as its own record inside the holding
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Date** | **DateTimeOffset** | Required | *No description available.* |
| **Cost** | **decimal** | Required | *No description available.* |
| **Indexation** | **decimal** | Required | *No description available.* |
| **PaidCost** | **decimal?** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ChargeableGainsTakeOnAddition(
    date: DateTimeOffset.Now,  // required
    cost: 0.0d,  // required
    indexation: 0.0d,  // required
    paidCost: 0.0d  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ChargeableGainsTakeOnAddition>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

