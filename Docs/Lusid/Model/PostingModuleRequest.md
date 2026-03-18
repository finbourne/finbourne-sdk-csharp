# Finbourne.Sdk.Lusid.Model.PostingModuleRequest

A Posting Module request definition
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | The code of the Posting Module. |
| **DisplayName** | **string** | Required | The name of the Posting Module. |
| **Description** | **string** | Optional | A description for the Posting Module. |
| **Rules** | [List&lt;PostingModuleRule&gt;](PostingModuleRule.md) | Optional | The Posting Rules that apply for the Posting Module. Rules are evaluated in the order they occur in this collection. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PostingModuleRequest(
    code: "...",  // required — The code of the Posting Module.
    displayName: "...",  // required — The name of the Posting Module.
    description: "...",  // optional — A description for the Posting Module.
    rules: new List<PostingModuleRule>()  // optional — The Posting Rules that apply for the Posting Module. Rules are evaluated in the order they occur in this collection.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PostingModuleRequest>(json);
```

- [PostingModuleRule](PostingModuleRule.md) — used in `Rules`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

