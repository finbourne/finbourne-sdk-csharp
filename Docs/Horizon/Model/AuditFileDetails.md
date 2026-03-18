# Finbourne.Sdk.Horizon.Model.AuditFileDetails

Holds information about Horizon Audit Files
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FileType** | **string** | Required | The type of the audit file |
| **FilePathAndName** | **string** | Required | The file path and name |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Horizon.Model;

var instance = new AuditFileDetails(
    fileType: "...",  // required — The type of the audit file
    filePathAndName: "..."  // required — The file path and name
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AuditFileDetails>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

