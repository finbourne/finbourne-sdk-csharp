# Finbourne.Sdk.Insights.Model.AuditData

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Action** | **string** | Required | *No description available.* |
| **Category** | **string** | Required | *No description available.* |
| **UserId** | **string** | Optional | *No description available.* |
| **Message** | **string** | Optional | *No description available.* |
| **Resource** | [Resource](Resource.md) | Optional | *No description available.* |
| **DetailsType** | **string** | Optional | *No description available.* |
| **Details** | **Object** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new AuditData(
    action: "...",  // required
    category: "...",  // required
    userId: "...",  // optional
    message: "...",  // optional
    resource: new Resource(...),  // optional
    detailsType: "...",  // optional
    details:   // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AuditData>(json);
```

- [Resource](Resource.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

