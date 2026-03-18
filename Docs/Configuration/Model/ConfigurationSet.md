# Finbourne.Sdk.Configuration.Model.ConfigurationSet

The full version of the configuration set
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **CreatedAt** | **DateTimeOffset** | Required | The date referring to the creation date of the configuration set |
| **CreatedBy** | **string** | Required | Who created the configuration set |
| **LastModifiedAt** | **DateTimeOffset** | Required | The date referring to the date when the configuration set was last modified |
| **LastModifiedBy** | **string** | Required | Who modified the configuration set most recently |
| **Description** | **string** | Optional | Describes the configuration set |
| **Items** | [List&lt;ConfigurationItemSummary&gt;](ConfigurationItemSummary.md) | Optional | The collection of the configuration items that this set contains. |
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Type** | **string** | Required | The type (personal or shared) of the configuration set |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Configuration.Model;

var instance = new ConfigurationSet(
    createdAt: DateTimeOffset.Now,  // required — The date referring to the creation date of the configuration set
    createdBy: "...",  // required — Who created the configuration set
    lastModifiedAt: DateTimeOffset.Now,  // required — The date referring to the date when the configuration set was last modified
    lastModifiedBy: "...",  // required — Who modified the configuration set most recently
    description: "...",  // optional — Describes the configuration set
    items: new List<ConfigurationItemSummary>(),  // optional — The collection of the configuration items that this set contains.
    id: new ResourceId(...),  // required
    type: "...",  // required — The type (personal or shared) of the configuration set
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ConfigurationSet>(json);
```

- [ConfigurationItemSummary](ConfigurationItemSummary.md) — used in `Items`
- [ResourceId](ResourceId.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

