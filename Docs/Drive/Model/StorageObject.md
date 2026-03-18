# Finbourne.Sdk.Drive.Model.StorageObject

An object representation of a drive file or folder
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **string** | Required | File or folder identifier |
| **Path** | **string** | Required | Path of the folder or file |
| **Name** | **string** | Required | Name of the folder or file |
| **CreatedBy** | **string** | Required | Identifier of the user who created the file or folder |
| **CreatedOn** | **DateTimeOffset** | Required | Date of file/folder creation |
| **UpdatedBy** | **string** | Required | Identifier of the last user to modify the file or folder |
| **UpdatedOn** | **DateTimeOffset** | Required | Date of file/folder modification |
| **Type** | **string** | Required | Type of storage object (file or folder) |
| **Size** | **int?** | Optional | Size of the file in bytes |
| **Status** | **string** | Optional | File status corresponding to virus scan status. (Active, Available, Checking, MalwareDetected, Failed) |
| **StatusDetail** | **string** | Optional | Detailed description describing any negative terminal state of file |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Drive.Model;

var instance = new StorageObject(
    id: "...",  // required — File or folder identifier
    path: "...",  // required — Path of the folder or file
    name: "...",  // required — Name of the folder or file
    createdBy: "...",  // required — Identifier of the user who created the file or folder
    createdOn: DateTimeOffset.Now,  // required — Date of file/folder creation
    updatedBy: "...",  // required — Identifier of the last user to modify the file or folder
    updatedOn: DateTimeOffset.Now,  // required — Date of file/folder modification
    type: "...",  // required — Type of storage object (file or folder)
    size: 0,  // optional — Size of the file in bytes
    status: "...",  // optional — File status corresponding to virus scan status. (Active, Available, Checking, MalwareDetected, Failed)
    statusDetail: "...",  // optional — Detailed description describing any negative terminal state of file
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<StorageObject>(json);
```

- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

