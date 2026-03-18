# Finbourne.Sdk.Lusid.Model.UpdateTimelineRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DisplayName** | **string** | Required | The name of the Timeline. |
| **Description** | **string** | Optional | A description for the Timeline. |
| **Properties** | [Dictionary&lt;string, Property&gt;](Property.md) | Optional | The Timelines properties. These will be from the &#39;Timeline&#39; domain. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpdateTimelineRequest(
    displayName: "...",  // required — The name of the Timeline.
    description: "...",  // optional — A description for the Timeline.
    properties: new Property(...)  // optional — The Timelines properties. These will be from the &#39;Timeline&#39; domain.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpdateTimelineRequest>(json);
```

- [Property](Property.md) — used in `Properties`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

