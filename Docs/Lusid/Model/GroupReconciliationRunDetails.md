# Finbourne.Sdk.Lusid.Model.GroupReconciliationRunDetails

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CompletionStatus** | **string** | Required | Provides the reconciliation completion status \&quot;Completed\&quot; | \&quot;FailedToComplete\&quot; |
| **ErrorDetail** | **string** | Optional | Error information if the reconciliation failed to complete |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GroupReconciliationRunDetails(
    completionStatus: "...",  // required — Provides the reconciliation completion status \&quot;Completed\&quot; | \&quot;FailedToComplete\&quot;
    errorDetail: "..."  // optional — Error information if the reconciliation failed to complete
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GroupReconciliationRunDetails>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

