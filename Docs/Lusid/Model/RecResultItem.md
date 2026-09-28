# Finbourne.Sdk.Lusid.Model.RecResultItem

An individual item that makes up (one side of) a rec result. Polymorphic by itemType; each value has a  corresponding inherited class.

## oneOf Type

`RecResultItem` can be one of the following types:

* [RecResultHoldingItem](./RecResultHoldingItem.md)
* [RecResultSettlementActivityItem](./RecResultSettlementActivityItem.md)
* [RecResultTransactionItem](./RecResultTransactionItem.md)

## Usage

### Creating from a compatible type

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var inner = new RecResultHoldingItem(...);
var instance = new RecResultItem(inner);
```

### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RecResultItem>(json);
```

## Related Models

- [RecResultHoldingItem](./RecResultHoldingItem.md)
- [RecResultSettlementActivityItem](./RecResultSettlementActivityItem.md)
- [RecResultTransactionItem](./RecResultTransactionItem.md)

[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

