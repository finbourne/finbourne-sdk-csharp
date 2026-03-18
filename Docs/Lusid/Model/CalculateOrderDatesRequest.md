# Finbourne.Sdk.Lusid.Model.CalculateOrderDatesRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InstrumentIdentifierType** | **string** | Required | *No description available.* |
| **InstrumentIdentifier** | **string** | Required | *No description available.* |
| **InstrumentScope** | **string** | Optional | *No description available.* |
| **ReceivedDate** | **DateTimeOffset?** | Optional | *No description available.* |
| **PriceDate** | **DateTimeOffset?** | Optional | *No description available.* |
| **TransactionCategory** | **string** | Optional | *No description available.* |
| **LiquidatingShareClassIdentifier** | **string** | Optional | *No description available.* |
| **LiquidatingShareClassIdentifierType** | **string** | Optional | *No description available.* |
| **LiquidatingShareClassInstrumentScope** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CalculateOrderDatesRequest(
    instrumentIdentifierType: "...",  // required
    instrumentIdentifier: "...",  // required
    instrumentScope: "...",  // optional
    receivedDate: DateTimeOffset.Now,  // optional
    priceDate: DateTimeOffset.Now,  // optional
    transactionCategory: "...",  // optional
    liquidatingShareClassIdentifier: "...",  // optional
    liquidatingShareClassIdentifierType: "...",  // optional
    liquidatingShareClassInstrumentScope: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CalculateOrderDatesRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

