# Finbourne.Sdk.Access.Model.RequestedActionKey

A fully qualified action identifier
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **EntityCode** | **string** | Required | The type of the resource on which the activity would be performed |
| **Scope** | **string** | Required | The scope/provider/vendor of the activity |
| **Activity** | **string** | Required | The identifier of the action to be performed on the resource |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new RequestedActionKey(
    entityCode: "...",  // required — The type of the resource on which the activity would be performed
    scope: "...",  // required — The scope/provider/vendor of the activity
    activity: "..."  // required — The identifier of the action to be performed on the resource
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RequestedActionKey>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

