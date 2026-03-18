# Finbourne.Sdk.Lusid.Model.GetCounterpartyAgreementResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Value** | [CounterpartyAgreement](CounterpartyAgreement.md) | Optional | *No description available.* |
| **Failed** | [Dictionary&lt;string, ErrorDetail&gt;](ErrorDetail.md) | Optional | The counterparty agreement that could not be retrieved along with a reason for failure. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new GetCounterpartyAgreementResponse(
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    value: new CounterpartyAgreement(...),  // optional
    failed: new ErrorDetail(...),  // optional — The counterparty agreement that could not be retrieved along with a reason for failure.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<GetCounterpartyAgreementResponse>(json);
```

- [CounterpartyAgreement](CounterpartyAgreement.md)
- [ErrorDetail](ErrorDetail.md) — used in `Failed`
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

