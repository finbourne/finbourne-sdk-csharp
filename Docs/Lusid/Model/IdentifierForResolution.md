# Finbourne.Sdk.Lusid.Model.IdentifierForResolution

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **IdentifierKey** | **string** | Required | Identifier key in the format &#39;{domain}/{scope}/{code}&#39;. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new IdentifierForResolution(
    identifierKey: "..."  // required — Identifier key in the format &#39;{domain}/{scope}/{code}&#39;.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<IdentifierForResolution>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

