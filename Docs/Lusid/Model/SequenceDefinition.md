# Finbourne.Sdk.Lusid.Model.SequenceDefinition

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Increment** | **long** | Required | The Resource Id of the sequence definition |
| **MinValue** | **long** | Required | The minimum value of the sequence |
| **MaxValue** | **long** | Required | The maximum value of the sequence |
| **Start** | **long** | Required | The start value of the sequence |
| **Value** | **long?** | Optional | The last used value of the sequence |
| **Cycle** | **bool** | Required | Indicates if the sequence would start from minimun value once it reaches maximum value. If set to false, a failure would return if the sequence reaches maximum value. |
| **Pattern** | **string** | Optional | The pattern to be used to generate next values in the sequence. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SequenceDefinition(
    id: new ResourceId(...),  // required
    increment: 0L,  // required — The Resource Id of the sequence definition
    minValue: 0L,  // required — The minimum value of the sequence
    maxValue: 0L,  // required — The maximum value of the sequence
    start: 0L,  // required — The start value of the sequence
    value: 0L,  // optional — The last used value of the sequence
    cycle: true,  // required — Indicates if the sequence would start from minimun value once it reaches maximum value. If set to false, a failure would return if the sequence reaches maximum value.
    pattern: "...",  // optional — The pattern to be used to generate next values in the sequence.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SequenceDefinition>(json);
```


## Related Models

- [ResourceId](ResourceId.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

