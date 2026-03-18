# Finbourne.Sdk.Notifications.Model.EventTypeSchema

An EventType object
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **string** | Optional | The identifier of the event type |
| **DisplayName** | **string** | Optional | Identifier name of the event |
| **Description** | **string** | Optional | The summary of the event |
| **Application** | **string** | Optional | The application associated with the event |
| **HeaderSchema** | [List&lt;EventFieldDefinition&gt;](EventFieldDefinition.md) | Optional | The header schema for the event type *(read-only)* |
| **BodySchema** | [List&lt;EventFieldDefinition&gt;](EventFieldDefinition.md) | Optional | The body schema for the event type *(read-only)* |
| **Href** | **string** | Optional | A URI for retrieving this schema |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Notifications.Model;

var instance = new EventTypeSchema(
    id: "...",  // optional — The identifier of the event type
    displayName: "...",  // optional — Identifier name of the event
    description: "...",  // optional — The summary of the event
    application: "...",  // optional — The application associated with the event
    headerSchema: new List<EventFieldDefinition>(),  // optional — The header schema for the event type
    bodySchema: new List<EventFieldDefinition>(),  // optional — The body schema for the event type
    href: "..."  // optional — A URI for retrieving this schema
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EventTypeSchema>(json);
```

- [EventFieldDefinition](EventFieldDefinition.md) — used in `HeaderSchema`
- [EventFieldDefinition](EventFieldDefinition.md) — used in `BodySchema`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

