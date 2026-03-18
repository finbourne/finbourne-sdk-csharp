# Finbourne.Sdk.Drive.Model.Link

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Relation** | **string** | Required | *No description available.* |
| **Href** | **string** | Required | *No description available.* |
| **Description** | **string** | Optional | *No description available.* |
| **Method** | **string** | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Drive.Model;

var instance = new Link(
    relation: "...",  // required
    href: "...",  // required
    description: "...",  // optional
    method: "..."  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<Link>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

