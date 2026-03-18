# Finbourne.Sdk.Configuration.Model.ConfigurationItem

The full version of the configuration item
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CreatedAt** | **DateTimeOffset** | Required | The date referring to the creation date of the configuration item |
| **CreatedBy** | **string** | Required | Who created the configuration item |
| **LastModifiedAt** | **DateTimeOffset** | Required | The date referring to the date when the configuration item was last modified |
| **LastModifiedBy** | **string** | Required | Who modified the configuration item most recently |
| **Description** | **string** | Optional | Describes the configuration item |
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

var instance = new ConfigurationItem(
    createdAt: DateTimeOffset.Now,  // required — The date referring to the creation date of the configuration item
    createdBy: "...",  // required — Who created the configuration item
    lastModifiedAt: DateTimeOffset.Now,  // required — The date referring to the date when the configuration item was last modified
    lastModifiedBy: "...",  // required — Who modified the configuration item most recently
    description: "...",  // optional — Describes the configuration item
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
var instance = JsonConvert.DeserializeObject<ConfigurationItem>(json);
```

- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

