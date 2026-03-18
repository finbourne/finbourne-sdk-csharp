# Finbourne.Sdk.Identity.Model.SetPassword

Set password request
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Value** | **string** | Required | The value of the new password |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new SetPassword(
    value: "..."  // required — The value of the new password
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SetPassword>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

