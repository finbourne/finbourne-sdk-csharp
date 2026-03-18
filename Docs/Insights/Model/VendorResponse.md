# Finbourne.Sdk.Insights.Model.VendorResponse

Details of a response to a request made to a vendor service.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Id** | **string** | Required | The ID of the log. |
| **Response** | **string** | Required | The body of the response. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Insights.Model;

var instance = new VendorResponse(
    id: "...",  // required — The ID of the log.
    response: "...",  // required — The body of the response.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<VendorResponse>(json);
```

- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

