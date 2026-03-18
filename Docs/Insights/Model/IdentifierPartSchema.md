# Finbourne.Sdk.Insights.Model.IdentifierPartSchema

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Index** | **int** | Required | *No description available.* |
| **Name** | **string** | Required | *No description available.* |
| **DisplayName** | **string** | Required | *No description available.* |
| **Description** | **string** | Required | *No description available.* |
| **Required** | **bool** | Required | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new IdentifierPartSchema(
    index: 0,  // required
    name: "...",  // required
    displayName: "...",  // required
    description: "...",  // required
    required: true,  // required
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<IdentifierPartSchema>(json);
```

- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

