# Finbourne.Sdk.Lusid.Model.Membership

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Scope** | **string** | Required | The scope of the unique identifier associated with the Custom Data Model. |
| **Code** | **string** | Required | The code of the unique identifier associated with the Custom Data Model. |
| **DisplayName** | **string** | Required | The name of the Custom Data Model. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new Membership(
    scope: "...",  // required — The scope of the unique identifier associated with the Custom Data Model.
    code: "...",  // required — The code of the unique identifier associated with the Custom Data Model.
    displayName: "..."  // required — The name of the Custom Data Model.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Membership>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

