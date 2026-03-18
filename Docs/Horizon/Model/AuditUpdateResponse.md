# Finbourne.Sdk.Horizon.Model.AuditUpdateResponse

Response type for Horizon Audit Event
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **ProcessName** | **string** | Required | The name of the Process the events will be visible under |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new AuditUpdateResponse(
    processName: "..."  // required — The name of the Process the events will be visible under
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AuditUpdateResponse>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

