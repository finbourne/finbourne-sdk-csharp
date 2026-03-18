# Finbourne.Sdk.Identity.Model.TemporaryPassword

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Password** | **string** | Required | The user&#39;s temporary password |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new TemporaryPassword(
    password: "..."  // required — The user&#39;s temporary password
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<TemporaryPassword>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

