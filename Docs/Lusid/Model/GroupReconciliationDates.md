# Finbourne.Sdk.Lusid.Model.GroupReconciliationDates

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Left** | [GroupReconciliationDatePair](GroupReconciliationDatePair.md) | Optional | *No description available.* |
| **Right** | [GroupReconciliationDatePair](GroupReconciliationDatePair.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GroupReconciliationDates(
    left: new GroupReconciliationDatePair(...),  // optional
    right: new GroupReconciliationDatePair(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GroupReconciliationDates>(json);
```


## Related Models

- [GroupReconciliationDatePair](GroupReconciliationDatePair.md)
- [GroupReconciliationDatePair](GroupReconciliationDatePair.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

