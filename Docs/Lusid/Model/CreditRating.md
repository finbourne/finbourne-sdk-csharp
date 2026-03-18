# Finbourne.Sdk.Lusid.Model.CreditRating

Object describing a credit rating,  which assesses the stability and credit worthiness of a legal entity  and hence its likelihood of defaulting on its outstanding obligations (typically debt).
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **RatingSource** | **string** | Required | The provider of the credit rating, which will typically be an agency such as Moody&#39;s or Standard and Poor. |
| **Rating** | **string** | Required | The credit rating provided by the rating source. This would expected to be consistent with the rating scheme of that agency/source. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CreditRating(
    ratingSource: "...",  // required — The provider of the credit rating, which will typically be an agency such as Moody&#39;s or Standard and Poor.
    rating: "..."  // required — The credit rating provided by the rating source. This would expected to be consistent with the rating scheme of that agency/source.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CreditRating>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

