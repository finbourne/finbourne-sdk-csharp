# Finbourne.Sdk.Lusid.Model.CreateTradeTicketsResponse

Batch trade ticket creation response
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Values** | [List&lt;LusidTradeTicket&gt;](LusidTradeTicket.md) | Required | *No description available.* |
| **Failures** | [List&lt;ErrorDetail&gt;](ErrorDetail.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreateTradeTicketsResponse(
    values: new List<LusidTradeTicket>(),  // required
    failures: new List<ErrorDetail>()  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreateTradeTicketsResponse>(json);
```


## Related Models

- [LusidTradeTicket](LusidTradeTicket.md)
- [ErrorDetail](ErrorDetail.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

