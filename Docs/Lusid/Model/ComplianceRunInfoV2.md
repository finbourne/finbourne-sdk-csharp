# Finbourne.Sdk.Lusid.Model.ComplianceRunInfoV2

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RunId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **InstigatedAt** | **DateTimeOffset** | Required | *No description available.* |
| **CompletedAt** | **DateTimeOffset** | Required | *No description available.* |
| **Schedule** | **string** | Required | *No description available.* |
| **InstigatedBy** | **string** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ComplianceRunInfoV2(
    runId: new ResourceId(...),  // required
    instigatedAt: DateTimeOffset.Now,  // required
    completedAt: DateTimeOffset.Now,  // required
    schedule: "...",  // required
    instigatedBy: "..."  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ComplianceRunInfoV2>(json);
```


## Related Models

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

