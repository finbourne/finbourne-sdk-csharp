# Finbourne.Sdk.Lusid.Model.RecResultException

The exception lifecycle of a rec result. Present only for exception result types  (Break, PartialMatch, PartialCross); null for Match and Cross.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Status** | **string** | Required | Whether the exception is Open or Closed. Available values: Open, Closed. |
| **ClosureType** | **string** | Optional | How the exception was closed. Non-null only when status is Closed. Available values: Cleared, Accepted, ForceMatched. |
| **AsAtClosed** | **DateTimeOffset?** | Optional | The asAt of the transaction that closed the exception. Non-null only when status is Closed. |
| **AsAtClosureInvalidated** | **DateTimeOffset?** | Optional | First-failure bookmark: the asAt at which a judgement closure&#39;s validity condition first failed against the latest run&#39;s data. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecResultException(
    status: "...",  // required — Whether the exception is Open or Closed. Available values: Open, Closed.
    closureType: "...",  // optional — How the exception was closed. Non-null only when status is Closed. Available values: Cleared, Accepted, ForceMatched.
    asAtClosed: DateTimeOffset.Now,  // optional — The asAt of the transaction that closed the exception. Non-null only when status is Closed.
    asAtClosureInvalidated: DateTimeOffset.Now  // optional — First-failure bookmark: the asAt at which a judgement closure&#39;s validity condition first failed against the latest run&#39;s data.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecResultException>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

