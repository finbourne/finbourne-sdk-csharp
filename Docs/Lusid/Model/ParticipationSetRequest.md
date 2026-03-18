# Finbourne.Sdk.Lusid.Model.ParticipationSetRequest

A request to create or update multiple Participations.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Requests** | [List&lt;ParticipationRequest&gt;](ParticipationRequest.md) | Optional | A collection of ParticipationRequests. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ParticipationSetRequest(
    requests: new List<ParticipationRequest>()  // optional — A collection of ParticipationRequests.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ParticipationSetRequest>(json);
```


## Related Models

- [ParticipationRequest](ParticipationRequest.md) — used in `Requests`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

