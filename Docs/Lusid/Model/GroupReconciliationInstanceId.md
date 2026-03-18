# Finbourne.Sdk.Lusid.Model.GroupReconciliationInstanceId

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstanceIdType** | **string** | Required | Type of the reconciliation run, manual or automatic (via the workflow). \&quot;Manual\&quot; | \&quot;WorkflowServiceTaskId\&quot; |
| **InstanceIdValue** | **string** | Required | Reconciliation run identifier: a manually-provided key or taskId. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GroupReconciliationInstanceId(
    instanceIdType: "...",  // required — Type of the reconciliation run, manual or automatic (via the workflow). \&quot;Manual\&quot; | \&quot;WorkflowServiceTaskId\&quot;
    instanceIdValue: "..."  // required — Reconciliation run identifier: a manually-provided key or taskId.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GroupReconciliationInstanceId>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

