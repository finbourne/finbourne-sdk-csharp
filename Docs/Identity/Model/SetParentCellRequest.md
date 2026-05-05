# Finbourne.Sdk.Identity.Model.SetParentCellRequest

Request body for setting the parent cell.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AdminDomainName** | **string** | Required | The name of the admin domain in the parent cell. |
| **Confirm** | **bool** | Required | Whether to confirm the parent cell attachment (second invocation). First call with false creates a Proposed state; second call with true transitions to Attaching. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new SetParentCellRequest(
    adminDomainName: "...",  // required — The name of the admin domain in the parent cell.
    confirm: true  // required — Whether to confirm the parent cell attachment (second invocation). First call with false creates a Proposed state; second call with true transitions to Attaching.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SetParentCellRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

