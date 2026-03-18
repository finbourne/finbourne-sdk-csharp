# Finbourne.Sdk.Lusid.Model.InflationIndexConventions

A set of conventions that describe the conventions for an inflation index.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **InflationIndexName** | **string** | Required | Name of the index, e.g. UKRPI. |
| **Currency** | **string** | Required | Currency of the inflation index convention. |
| **ObservationLag** | **string** | Required | Observation lag. This is a string that must have units of Month.  This field is typically 3 or 4 months, but can vary, older bonds and swaps have 8 months lag.  For Bonds with a calculation type of Ratio, this property, if set, must be 0Invalid.    For more information on tenors, see [knowledge base article KA-02097](https://support.lusid.com/knowledgebase/article/KA-02097) |
| **InflationInterpolation** | **string** | Optional | Inflation Interpolation. This is optional and defaults to Linear if not set.    Supported string (enumeration) values are: [Linear, Flat]. |
| **InflationFrequency** | **string** | Optional | Frequency of inflation updated. Optional and defaults to Monthly which is the most common.  However both Australian and New Zealand inflation is published Quarterly. Only tenors of 1M or 3M are supported.    For more information on tenors, see [knowledge base article KA-02097](https://support.lusid.com/knowledgebase/article/KA-02097) |
| **InflationRollDay** | **int** | Optional | Day of the month that inflation rolls from one month to the next. This is optional and defaults to 1, which is  the typically value for the majority of inflation bonds (exceptions include Japan which rolls on the 10th  and some LatAm bonds which roll on the 15th). Default: `1` |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new InflationIndexConventions(
    inflationIndexName: "...",  // required — Name of the index, e.g. UKRPI.
    currency: "...",  // required — Currency of the inflation index convention.
    observationLag: "...",  // required — Observation lag. This is a string that must have units of Month.  This field is typically 3 or 4 months, but can vary, older bonds and swaps have 8 months lag.  For Bonds with a calculation type of Ratio, this property, if set, must be 0Invalid.    For more information on tenors, see [knowledge base article KA-02097](https://support.lusid.com/knowledgebase/article/KA-02097)
    inflationInterpolation: "...",  // optional — Inflation Interpolation. This is optional and defaults to Linear if not set.    Supported string (enumeration) values are: [Linear, Flat].
    inflationFrequency: "...",  // optional — Frequency of inflation updated. Optional and defaults to Monthly which is the most common.  However both Australian and New Zealand inflation is published Quarterly. Only tenors of 1M or 3M are supported.    For more information on tenors, see [knowledge base article KA-02097](https://support.lusid.com/knowledgebase/article/KA-02097)
    inflationRollDay: 0  // optional — Day of the month that inflation rolls from one month to the next. This is optional and defaults to 1, which is  the typically value for the majority of inflation bonds (exceptions include Japan which rolls on the 10th  and some LatAm bonds which roll on the 15th).
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<InflationIndexConventions>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

