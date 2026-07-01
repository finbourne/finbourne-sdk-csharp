# Finbourne.Sdk.Lusid.Model.ResolveTenorsRequest

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StartDate** | **DateTimeOffset** | Required | *No description available.* |
| **Calendars** | [List&lt;ResourceId&gt;](ResourceId.md) | Required | *No description available.* |
| **SpotDays** | **int** | Required | *No description available.* |
| **Tenors** | **List&lt;string&gt;** | Required | *No description available.* |
| **BusinessDayConvention** | **string** | Optional | Available values: NoAdjustment, None, Previous, P, Following, F, ModifiedPrevious, MP, ModifiedFollowing, MF, HalfMonthModifiedFollowing, Nearest, Invalid. |
| **EomRule** | **string** | Optional | *No description available.* |
| **AsAt** | **DateTimeOffset?** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ResolveTenorsRequest(
    startDate: DateTimeOffset.Now,  // required
    calendars: new List<ResourceId>(),  // required
    spotDays: 0,  // required
    tenors: ,  // required
    businessDayConvention: "...",  // optional — Available values: NoAdjustment, None, Previous, P, Following, F, ModifiedPrevious, MP, ModifiedFollowing, MF, HalfMonthModifiedFollowing, Nearest, Invalid.
    eomRule: "...",  // optional
    asAt: DateTimeOffset.Now  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ResolveTenorsRequest>(json);
```

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

