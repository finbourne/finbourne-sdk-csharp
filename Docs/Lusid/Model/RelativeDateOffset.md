# Finbourne.Sdk.Lusid.Model.RelativeDateOffset

Defines a date offset which is relative to some anchor date.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Days** | **int** | Required | The number of days to add to the anchor date. |
| **BusinessDayConvention** | **string** | Required | The adjustment type to apply to dates that fall upon a non-business day, e.g. modified following or following.    Supported string (enumeration) values are: [NoAdjustment, Previous, P, Following, F, ModifiedPrevious, MP, ModifiedFollowing, MF, HalfMonthModifiedFollowing, Nearest]. |
| **DayType** | **string** | Optional | Indicates if consideration is given to whether a day is a good business day or not when calculating the offset date.    Supported string (enumeration) values are: [Business, Calendar].  Defaults to \&quot;Business\&quot; if not set. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new RelativeDateOffset(
    days: 0,  // required — The number of days to add to the anchor date.
    businessDayConvention: "...",  // required — The adjustment type to apply to dates that fall upon a non-business day, e.g. modified following or following.    Supported string (enumeration) values are: [NoAdjustment, Previous, P, Following, F, ModifiedPrevious, MP, ModifiedFollowing, MF, HalfMonthModifiedFollowing, Nearest].
    dayType: "..."  // optional — Indicates if consideration is given to whether a day is a good business day or not when calculating the offset date.    Supported string (enumeration) values are: [Business, Calendar].  Defaults to \&quot;Business\&quot; if not set.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RelativeDateOffset>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

