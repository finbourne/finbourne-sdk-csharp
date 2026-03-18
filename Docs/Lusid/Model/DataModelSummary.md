# Finbourne.Sdk.Lusid.Model.DataModelSummary

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **DisplayName** | **string** | Required | The name of the Custom Data Model. |
| **Description** | **string** | Optional | A description for the Custom Data Model. |
| **EntityType** | **string** | Required | The entity type that the Custom Data Model binds to. |
| **Type** | **string** | Required | Either Root or Leaf or Intermediate. |
| **Precedence** | **int** | Required | Where in the hierarchy this model sits. |
| **Parent** | [ResourceId](ResourceId.md) | Optional | *No description available.* |
| **Children** | [List&lt;DataModelSummary&gt;](DataModelSummary.md) | Required | Child Custom Data Models that will inherit from this data model. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new DataModelSummary(
    id: new ResourceId(...),  // required
    displayName: "...",  // required — The name of the Custom Data Model.
    description: "...",  // optional — A description for the Custom Data Model.
    entityType: "...",  // required — The entity type that the Custom Data Model binds to.
    type: "...",  // required — Either Root or Leaf or Intermediate.
    precedence: 0,  // required — Where in the hierarchy this model sits.
    parent: new ResourceId(...),  // optional
    children: new List<DataModelSummary>()  // required — Child Custom Data Models that will inherit from this data model.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<DataModelSummary>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [ResourceId](ResourceId.md)
- [DataModelSummary](DataModelSummary.md) — used in `Children`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

