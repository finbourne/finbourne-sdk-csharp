# Finbourne.Sdk.Lusid.Model.OverrideVirtualTransactionsResponse

## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **VarVersion** | [ModelVersion](ModelVersion.md) | Required | *No description available.* |
| **Href** | **string** | Optional | The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime. |
| **Metadata** | **Dictionary&lt;string, List&lt;ResponseMetaData&gt;&gt;** | Optional | Contains warnings related to unresolved instruments or non-existent transaction types for the override transactions. |
| **InstrumentEventId** | **string** | Required | The identifier of the instrument event that was overridden. |
| **CancelInstructionId** | **string** | Required | The identifier of the cancel instruction that was created for the overridden instrument event. |
| **Links** | [List&lt;Link&gt;](Link.md) | Optional | *No description available.* |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new OverrideVirtualTransactionsResponse(
    varVersion: new ModelVersion(...),  // required
    href: "...",  // optional — The specific Uniform Resource Identifier (URI) for this resource at the requested effective and asAt datetime.
    metadata: ,  // optional — Contains warnings related to unresolved instruments or non-existent transaction types for the override transactions.
    instrumentEventId: "...",  // required — The identifier of the instrument event that was overridden.
    cancelInstructionId: "...",  // required — The identifier of the cancel instruction that was created for the overridden instrument event.
    links: new List<Link>()  // optional
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<OverrideVirtualTransactionsResponse>(json);
```


## Related Models

- [ModelVersion](ModelVersion.md)
- [Link](Link.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

