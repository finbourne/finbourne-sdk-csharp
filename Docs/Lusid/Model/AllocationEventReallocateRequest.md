# Finbourne.Sdk.Lusid.Model.AllocationEventReallocateRequest

The request used to recompute an unbooked Allocation Event: why, and with which basis values.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Reason** | **string** | Required | Why the event is being recomputed. |
| **BasisValues** | [List&lt;AllocationMapBasisValue&gt;](AllocationMapBasisValue.md) | Optional | Optional replacement basis values per investor record. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new AllocationEventReallocateRequest(
    reason: "...",  // required — Why the event is being recomputed.
    basisValues: new List<AllocationMapBasisValue>()  // optional — Optional replacement basis values per investor record.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AllocationEventReallocateRequest>(json);
```

- [AllocationMapBasisValue](AllocationMapBasisValue.md) — used in `BasisValues`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

