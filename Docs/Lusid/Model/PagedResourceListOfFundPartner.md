# Finbourne.Sdk.Lusid.Model.PagedResourceListOfFundPartner

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **NextPage** | **string** | Optional | *No description available.* |
| **PreviousPage** | **string** | Optional | *No description available.* |
| **Values** | [List&lt;FundPartner&gt;](FundPartner.md) | Required | *No description available.* |
| **Href** | **string** | Optional | *No description available.* |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PagedResourceListOfFundPartner(
    nextPage: "...",  // optional
    previousPage: "...",  // optional
    values: new List<FundPartner>(),  // required
    href: "...",  // optional
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PagedResourceListOfFundPartner>(json);
```

- [FundPartner](FundPartner.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

