# Finbourne.Sdk.Identity.Model.SupportAccessExpiry

Time at which the support access expires
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Expiry** | **DateTimeOffset** | Required | DateTimeOffset at which the access will be revoked |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new SupportAccessExpiry(
    expiry: DateTimeOffset.Now  // required — DateTimeOffset at which the access will be revoked
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SupportAccessExpiry>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

