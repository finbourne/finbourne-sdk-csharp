# Finbourne.Sdk.Lusid.Model.ReferenceListRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Name** | **string** | Required | The name of the reference list. |
| **Description** | **string** | Optional | The description of the reference list. |
| **Tags** | **List&lt;string&gt;** | Optional | The tags associated with the reference list. |
| **ReferenceList** | [ReferenceList](ReferenceList.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ReferenceListRequest(
    id: new ResourceId(...),  // required
    name: "...",  // required — The name of the reference list.
    description: "...",  // optional — The description of the reference list.
    tags: ,  // optional — The tags associated with the reference list.
    referenceList: new ReferenceList(...)  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ReferenceListRequest>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ReferenceList](ReferenceList.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

