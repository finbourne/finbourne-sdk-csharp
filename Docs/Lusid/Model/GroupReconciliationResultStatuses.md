# Finbourne.Sdk.Lusid.Model.GroupReconciliationResultStatuses

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CountNew** | **int** | Required | The number of comparison results of resultStatus \&quot;New\&quot; with this instanceId and reconciliationType |
| **LinkNew** | [Link](Link.md) | Required | *No description available.* |
| **CountConfirmed** | **int** | Required | The number of comparison results of resultStatus \&quot;Confirmed\&quot; with this instanceId and reconciliationType |
| **LinkConfirmed** | [Link](Link.md) | Required | *No description available.* |
| **CountChanged** | **int** | Required | The number of comparison results of resultStatus \&quot;Changed\&quot; with this instanceId and reconciliationType |
| **LinkChanged** | [Link](Link.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GroupReconciliationResultStatuses(
    countNew: 0,  // required — The number of comparison results of resultStatus \&quot;New\&quot; with this instanceId and reconciliationType
    linkNew: new Link(...),  // required
    countConfirmed: 0,  // required — The number of comparison results of resultStatus \&quot;Confirmed\&quot; with this instanceId and reconciliationType
    linkConfirmed: new Link(...),  // required
    countChanged: 0,  // required — The number of comparison results of resultStatus \&quot;Changed\&quot; with this instanceId and reconciliationType
    linkChanged: new Link(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GroupReconciliationResultStatuses>(json);
```

- [Link](Link.md)
- [Link](Link.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

