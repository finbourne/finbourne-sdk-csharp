# Finbourne.Sdk.Lusid.Model.GroupReconciliationRunRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstanceId** | **string** | Required | Reconciliation run Id. Consists of run type (manual or workflow) and identifier. |
| **DatesToReconcile** | [GroupReconciliationDates](GroupReconciliationDates.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GroupReconciliationRunRequest(
    instanceId: "...",  // required — Reconciliation run Id. Consists of run type (manual or workflow) and identifier.
    datesToReconcile: new GroupReconciliationDates(...)  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GroupReconciliationRunRequest>(json);
```

- [GroupReconciliationDates](GroupReconciliationDates.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

