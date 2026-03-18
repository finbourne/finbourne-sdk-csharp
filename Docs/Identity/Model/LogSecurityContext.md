# Finbourne.Sdk.Identity.Model.LogSecurityContext

Represents a LogSecurityContext resource in the Okta API
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AsNumber** | **int?** | Optional | *No description available.* |
| **AsOrg** | **string** | Optional | *No description available.* |
| **Isp** | **string** | Optional | *No description available.* |
| **Domain** | **string** | Optional | *No description available.* |
| **IsProxy** | **bool?** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Identity.Model;

var instance = new LogSecurityContext(
    asNumber: 0,  // optional
    asOrg: "...",  // optional
    isp: "...",  // optional
    domain: "...",  // optional
    isProxy: true  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<LogSecurityContext>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

