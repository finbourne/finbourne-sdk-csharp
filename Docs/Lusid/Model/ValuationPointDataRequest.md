# Finbourne.Sdk.Lusid.Model.ValuationPointDataRequest

The ValuationPointDataRequest.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DiaryEntryCode** | **string** | Required | Unique code for the Valuation Point. |
| **DiaryEntryVariant** | **string** | Optional | Optional variant code. Only required when it is necessary to choose between scenarios with multiple estimates. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ValuationPointDataRequest(
    diaryEntryCode: "...",  // required — Unique code for the Valuation Point.
    diaryEntryVariant: "..."  // optional — Optional variant code. Only required when it is necessary to choose between scenarios with multiple estimates.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ValuationPointDataRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

