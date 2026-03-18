# Finbourne.Sdk.Lusid.Model.ResourceListOfGetCounterpartyAgreementResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Values** | [List&lt;GetCounterpartyAgreementResponse&gt;](GetCounterpartyAgreementResponse.md) | Required | *No description available.* |
| **Href** | **string** | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |
| **NextPage** | **string** | Optional | *No description available.* |
| **PreviousPage** | **string** | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new ResourceListOfGetCounterpartyAgreementResponse(
    values: new List<GetCounterpartyAgreementResponse>(),  // required
    href: "...",  // optional
    links: new List<Link>(),  // optional
    nextPage: "...",  // optional
    previousPage: "..."  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ResourceListOfGetCounterpartyAgreementResponse>(json);
```


## Related Models

- [GetCounterpartyAgreementResponse](GetCounterpartyAgreementResponse.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

