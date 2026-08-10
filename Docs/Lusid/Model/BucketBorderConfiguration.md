# Finbourne.Sdk.Lusid.Model.BucketBorderConfiguration

Configuration determining how the borders of bucket intervals behave when allocating cash flows to buckets.  When supplied, cash flows are bucketed into intervals defined by the bucketing dates rather than being  rounded to the nearest bucketing date.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **StartInclusive** | **bool** | Optional | Is the start of the first bucket interval inclusive of its start date. Defaults to true. |
| **EndInclusive** | **bool** | Optional | Is the end of the last bucket interval inclusive of its end date. Defaults to false. |
| **BoundaryBelongsTo** | **string** | Optional | For boundaries shared by two adjacent intervals, which interval a cash flow falling exactly on the  boundary belongs to. Supported string (enumeration) values are: [Earlier, Later]. Defaults to &#39;Earlier&#39;. Available values: Earlier, Later. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BucketBorderConfiguration(
    startInclusive: true,  // optional — Is the start of the first bucket interval inclusive of its start date. Defaults to true.
    endInclusive: true,  // optional — Is the end of the last bucket interval inclusive of its end date. Defaults to false.
    boundaryBelongsTo: "..."  // optional — For boundaries shared by two adjacent intervals, which interval a cash flow falling exactly on the  boundary belongs to. Supported string (enumeration) values are: [Earlier, Later]. Defaults to &#39;Earlier&#39;. Available values: Earlier, Later.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BucketBorderConfiguration>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

