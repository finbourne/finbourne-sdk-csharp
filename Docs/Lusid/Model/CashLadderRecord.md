# Finbourne.Sdk.Lusid.Model.CashLadderRecord

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EffectiveDate** | **DateTimeOffset** | Optional | *No description available.* |
| **Open** | **decimal** | Required | *No description available.* |
| **Activities** | **Dictionary&lt;string, decimal&gt;** | Required | *No description available.* |
| **Close** | **decimal** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CashLadderRecord(
    effectiveDate: DateTimeOffset.Now,  // optional
    open: 0.0d,  // required
    activities: ,  // required
    close: 0.0d  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CashLadderRecord>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

