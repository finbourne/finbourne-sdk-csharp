# Finbourne.Sdk.Lusid.Model.PartnerStatementRequest

The request to produce a partner statement over a period.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **PeriodStart** | **DateTimeOffset** | Required | The start of the statement period, exclusive. |
| **PeriodEnd** | **DateTimeOffset** | Required | The end of the statement period, inclusive. |
| **NavTypeCode** | **string** | Optional | The NAV type to produce the statement under. Defaults to the fund&#39;s primary NAV type. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PartnerStatementRequest(
    periodStart: DateTimeOffset.Now,  // required — The start of the statement period, exclusive.
    periodEnd: DateTimeOffset.Now,  // required — The end of the statement period, inclusive.
    navTypeCode: "..."  // optional — The NAV type to produce the statement under. Defaults to the fund&#39;s primary NAV type.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PartnerStatementRequest>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

