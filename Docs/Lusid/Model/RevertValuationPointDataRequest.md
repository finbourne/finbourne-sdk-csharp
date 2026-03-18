# Finbourne.Sdk.Lusid.Model.RevertValuationPointDataRequest

The RevertValuationPointDataRequest.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **DiaryEntryCode** | **string** | Required | Unique code for the Valuation Point. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RevertValuationPointDataRequest(
    diaryEntryCode: "..."  // required — Unique code for the Valuation Point.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RevertValuationPointDataRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

