# Finbourne.Sdk.Lusid.Model.PostingModuleDetails

A posting Module request definition
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Required | The name of the Posting Module. |
| **Description** | **string** | Optional | A description for the Posting Module. |
| **Status** | **string** | Required | The Posting Module status. Can be Active or Inactive. Defaults to Active. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PostingModuleDetails(
    displayName: "...",  // required — The name of the Posting Module.
    description: "...",  // optional — A description for the Posting Module.
    status: "..."  // required — The Posting Module status. Can be Active or Inactive. Defaults to Active.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PostingModuleDetails>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

