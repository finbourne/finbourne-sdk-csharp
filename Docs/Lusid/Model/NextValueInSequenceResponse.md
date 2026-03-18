# Finbourne.Sdk.Lusid.Model.NextValueInSequenceResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Values** | **List&lt;string&gt;** | Required | The next set of values for the specified Sequence. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new NextValueInSequenceResponse(
    values: ,  // required — The next set of values for the specified Sequence.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<NextValueInSequenceResponse>(json);
```

- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

