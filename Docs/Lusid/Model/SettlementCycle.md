# Finbourne.Sdk.Lusid.Model.SettlementCycle

The settlement cycle for an instrument
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **BusinessDayOffset** | **int** | Required | *No description available.* |
| **Calendars** | [List&lt;ResourceId&gt;](ResourceId.md) | Required | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new SettlementCycle(
    businessDayOffset: 0,  // required
    calendars: new List<ResourceId>()  // required
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<SettlementCycle>(json);
```

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

