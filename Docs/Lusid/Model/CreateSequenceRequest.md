# Finbourne.Sdk.Lusid.Model.CreateSequenceRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Code** | **string** | Required | The code of the sequence definition to create |
| **Increment** | **long?** | Optional | The value to increment between each value in the sequence |
| **MinValue** | **long?** | Optional | The minimum value of the sequence |
| **MaxValue** | **long?** | Optional | The maximum value of the sequence |
| **Start** | **long?** | Optional | The start value of the sequence |
| **Cycle** | **bool** | Optional | Set to true to start the sequence over again when it reaches the end. Defaults to false if not provided. |
| **Pattern** | **string** | Optional | The pattern to be used to generate next values in the sequence. Defaults to null if not provided. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreateSequenceRequest(
    code: "...",  // required — The code of the sequence definition to create
    increment: 0L,  // optional — The value to increment between each value in the sequence
    minValue: 0L,  // optional — The minimum value of the sequence
    maxValue: 0L,  // optional — The maximum value of the sequence
    start: 0L,  // optional — The start value of the sequence
    cycle: true,  // optional — Set to true to start the sequence over again when it reaches the end. Defaults to false if not provided.
    pattern: "..."  // optional — The pattern to be used to generate next values in the sequence. Defaults to null if not provided.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateSequenceRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

