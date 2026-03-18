# Finbourne.Sdk.Configuration.Model.ConfigurationItemSummary

A single configuration object
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Key** | **string** | Required | The key which identifies the configuration item |
| **Value** | **string** | Required | The value of the configuration item |
| **ValueType** | **string** | Required | The type of the configuration item&#39;s value |
| **IsSecret** | **bool** | Required | Defines whether or not the value is a secret. |
| **Ref** | **string** | Required | The reference to the configuration item *(read-only)* |
| **BlockReveal** | **bool** | Required | Defines whether the value is blocked with non-internal request. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Configuration.Model;

var instance = new ConfigurationItemSummary(
    key: "...",  // required — The key which identifies the configuration item
    value: "...",  // required — The value of the configuration item
    valueType: "...",  // required — The type of the configuration item&#39;s value
    isSecret: true,  // required — Defines whether or not the value is a secret.
    varRef: "...",  // required — The reference to the configuration item
    blockReveal: true,  // required — Defines whether the value is blocked with non-internal request.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ConfigurationItemSummary>(json);
```

- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

