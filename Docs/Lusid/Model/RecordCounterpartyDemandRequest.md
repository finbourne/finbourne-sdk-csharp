# Finbourne.Sdk.Lusid.Model.RecordCounterpartyDemandRequest

The counterparty's figure for a margin call, to match against ours.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Amount** | **decimal** | Required | The counterparty&#39;s figure for the call, signed as the call. |
| **ReceivedAt** | **DateTimeOffset?** | Optional | When the demand was received. Defaults to the current LUSID system datetime if not specified. |
| **StatementReference** | **string** | Optional | A reference to the counterparty&#39;s statement, such as a Drive path. Optional. |
| **Note** | **string** | Optional | A note to record with the demand. Optional. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RecordCounterpartyDemandRequest(
    amount: 0.0d,  // required — The counterparty&#39;s figure for the call, signed as the call.
    receivedAt: DateTimeOffset.Now,  // optional — When the demand was received. Defaults to the current LUSID system datetime if not specified.
    statementReference: "...",  // optional — A reference to the counterparty&#39;s statement, such as a Drive path. Optional.
    note: "..."  // optional — A note to record with the demand. Optional.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecordCounterpartyDemandRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

