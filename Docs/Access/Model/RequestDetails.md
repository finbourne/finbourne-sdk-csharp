# Finbourne.Sdk.Access.Model.RequestDetails

The details of the requested evaluation
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Action** | [RequestedActionKey](RequestedActionKey.md) | Required | *No description available.* |
| **FromEffectiveDate** | **DateTimeOffset?** | Optional | The start date for the requested effective date range for the resource (if null, UtcNow) |
| **ToEffectiveDate** | **DateTimeOffset?** | Optional | The end date for the requested effective date range for the resource (if null, same as from date) |
| **FromAsAt** | **DateTimeOffset?** | Optional | The requested AsAt date for the resource (if null, Latest). If specifying a range of AsAt dates, this is the lower bounds. |
| **ToAsAt** | **DateTimeOffset?** | Optional | Upper bound if specifying a request that requires a range of AsAt dates. This is used if specifying the desire to grant access for a user between an AsAt range. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Access.Model;

var instance = new RequestDetails(
    action: new RequestedActionKey(...),  // required
    fromEffectiveDate: DateTimeOffset.Now,  // optional — The start date for the requested effective date range for the resource (if null, UtcNow)
    toEffectiveDate: DateTimeOffset.Now,  // optional — The end date for the requested effective date range for the resource (if null, same as from date)
    fromAsAt: DateTimeOffset.Now,  // optional — The requested AsAt date for the resource (if null, Latest). If specifying a range of AsAt dates, this is the lower bounds.
    toAsAt: DateTimeOffset.Now  // optional — Upper bound if specifying a request that requires a range of AsAt dates. This is used if specifying the desire to grant access for a user between an AsAt range.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<RequestDetails>(json);
```


## Related Models

- [RequestedActionKey](RequestedActionKey.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

