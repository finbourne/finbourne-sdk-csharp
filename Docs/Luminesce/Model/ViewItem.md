# Finbourne.Sdk.Luminesce.Model.ViewItem

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Optional | The name of the view |
| **Domain** | **string** | Optional | The domain the view applies to |
| **FilePath** | **string** | Optional | The full file path in the HcFs |
| **FileContent** | **string** | Optional | The full file content in the HcFs. This will be needed for Upserting the view to a different domain / for use in fbn-config. |
| **LastUpdatedExecutionId** | **Guid?** | Optional | The last ExecutionId, needed to get the creating Sql out of the logs |
| **LastUpdatedAt** | **DateTimeOffset?** | Optional | The last updated at time, needed to get the creating Sql out of the logs |
| **LastUpdatedBy** | **string** | Optional | The last updated by this user |
| **CreatedByUserId** | **string** | Optional | Originally created by this user |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new ViewItem(
    name: "...",  // optional — The name of the view
    domain: "...",  // optional — The domain the view applies to
    filePath: "...",  // optional — The full file path in the HcFs
    fileContent: "...",  // optional — The full file content in the HcFs. This will be needed for Upserting the view to a different domain / for use in fbn-config.
    lastUpdatedExecutionId: "...",  // optional — The last ExecutionId, needed to get the creating Sql out of the logs
    lastUpdatedAt: DateTimeOffset.Now,  // optional — The last updated at time, needed to get the creating Sql out of the logs
    lastUpdatedBy: "...",  // optional — The last updated by this user
    createdByUserId: "..."  // optional — Originally created by this user
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ViewItem>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

