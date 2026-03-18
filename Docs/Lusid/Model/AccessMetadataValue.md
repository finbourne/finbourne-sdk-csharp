# Finbourne.Sdk.Lusid.Model.AccessMetadataValue

An access control value. Provider should only be used if you are a service provider licensing data. In that case  the provider value must match your domain.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Value** | **string** | Required | *No description available.* |
| **Provider** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AccessMetadataValue(
    value: "...",  // required
    provider: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AccessMetadataValue>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

