# Finbourne.Sdk.Lusid.Model.UnconfirmClosedPeriodRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DeleteSubsequentPeriods** | **bool** | Optional | Whether to delete every Closed Period that comes after the requested Closed Period on the Timeline. When false (the default) only the latest confirmed Closed Period may be unconfirmed. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UnconfirmClosedPeriodRequest(
    deleteSubsequentPeriods: true  // optional — Whether to delete every Closed Period that comes after the requested Closed Period on the Timeline. When false (the default) only the latest confirmed Closed Period may be unconfirmed.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UnconfirmClosedPeriodRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

