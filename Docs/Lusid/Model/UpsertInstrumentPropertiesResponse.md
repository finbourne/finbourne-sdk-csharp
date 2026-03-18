# Finbourne.Sdk.Lusid.Model.UpsertInstrumentPropertiesResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AsAtDate** | **DateTimeOffset** | Required | The as-at datetime at which properties were created or updated. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new UpsertInstrumentPropertiesResponse(
    asAtDate: DateTimeOffset.Now,  // required — The as-at datetime at which properties were created or updated.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<UpsertInstrumentPropertiesResponse>(json);
```

- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

