# Finbourne.Sdk.Notifications.Model.EventFieldDefinition

An EventFieldDefinition object
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Optional | Name of the field |
| **Type** | **string** | Optional | Type of the field |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Notifications.Model;

var instance = new EventFieldDefinition(
    name: "...",  // optional — Name of the field
    type: "..."  // optional — Type of the field
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<EventFieldDefinition>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

