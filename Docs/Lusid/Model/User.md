# Finbourne.Sdk.Lusid.Model.User

The unique id of the user that issued the command.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **string** | Optional | The unique id of the user. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new User(
    id: "..."  // optional — The unique id of the user.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<User>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

