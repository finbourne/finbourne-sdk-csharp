# Finbourne.Sdk.Lusid.Model.FundCalendarEntries

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **FundCalendarEntriesType** | **string** | Required | The type of the Calendar Entry. The available values are: FinalisedValuationPoint, FundEstimateValuationPoint, FundBookmark |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundCalendarEntries(
    fundCalendarEntriesType: "..."  // required — The type of the Calendar Entry. The available values are: FinalisedValuationPoint, FundEstimateValuationPoint, FundBookmark
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundCalendarEntries>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

