# Finbourne.Sdk.Lusid.Model.GroupReconciliationDatePair

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EffectiveAt** | **DateTimeOffset?** | Optional | The effective at date for the reconciliation |
| **AsAt** | **DateTimeOffset?** | Optional | The as at date for the reconciliation |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GroupReconciliationDatePair(
    effectiveAt: DateTimeOffset.Now,  // optional — The effective at date for the reconciliation
    asAt: DateTimeOffset.Now  // optional — The as at date for the reconciliation
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GroupReconciliationDatePair>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

