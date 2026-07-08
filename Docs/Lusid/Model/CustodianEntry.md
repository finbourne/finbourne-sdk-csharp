# Finbourne.Sdk.Lusid.Model.CustodianEntry

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **AccountId** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **AccountSelector** | **string** | Optional | Available values: From, To. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new CustodianEntry(
    accountId: new ResourceId(...),  // required
    accountSelector: "..."  // optional — Available values: From, To.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<CustodianEntry>(json);
```


## Related Models

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

