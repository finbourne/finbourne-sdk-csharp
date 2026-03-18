# Finbourne.Sdk.Lusid.Model.BucketedCashFlowResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | *No description available.* |
| **Data** | **List&lt;Dictionary&lt;string, Object&gt;&gt;** | Optional | List of dictionary bucketed cash flow result set.  Each dictionary represent a bucketed cashflow result set keyed by AddressKeys.  e.g. dictionary[\&quot;Valuation/CashFlowAmount\&quot;] for the aggregated cash flow amount for the bucket.  e.g. suppose \&quot;RoundUp\&quot; method, then dictionary[\&quot;Valuation/CashFlowDate/RoundUp\&quot;] returns the bucketed cashflow date. |
| **ReportCurrency** | **string** | Optional | Three letter ISO currency string indicating what currency to report in for ReportCcy denominated queries.  If not present then the currency of the relevant portfolio will be used in its place where relevant. |
| **DataSchema** | [ResultDataSchema](ResultDataSchema.md) | Optional | *No description available.* |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | Information about where instruments have failed to return cashflows in so far as it is available.  e.g., failure to retrieve a market quote for a floating rate instrument. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new BucketedCashFlowResponse(
    href: "...",  // optional
    data: ,  // optional — List of dictionary bucketed cash flow result set.  Each dictionary represent a bucketed cashflow result set keyed by AddressKeys.  e.g. dictionary[\&quot;Valuation/CashFlowAmount\&quot;] for the aggregated cash flow amount for the bucket.  e.g. suppose \&quot;RoundUp\&quot; method, then dictionary[\&quot;Valuation/CashFlowDate/RoundUp\&quot;] returns the bucketed cashflow date.
    reportCurrency: "...",  // optional — Three letter ISO currency string indicating what currency to report in for ReportCcy denominated queries.  If not present then the currency of the relevant portfolio will be used in its place where relevant.
    dataSchema: new ResultDataSchema(...),  // optional
    failed: new ErrorDetail(...),  // optional — Information about where instruments have failed to return cashflows in so far as it is available.  e.g., failure to retrieve a market quote for a floating rate instrument.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<BucketedCashFlowResponse>(json);
```

- [ResultDataSchema](ResultDataSchema.md)
- [ErrorDetail](ErrorDetail.md) — used in `Failed`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

