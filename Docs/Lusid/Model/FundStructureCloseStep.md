# Finbourne.Sdk.Lusid.Model.FundStructureCloseStep

One member's step in a fund structure close.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **MemberShortCode** | **string** | Required | The node code of the member in the structure. |
| **Fund** | [ResourceId](ResourceId.md) | Required | *No description available.* |
| **Step** | **int** | Required | The position of the member in the close order. |
| **Status** | **string** | Required | What happened to the member. Available values: Finalised, AlreadyFinal, Failed, Skipped. |
| **Failure** | **string** | Optional | The failure that stopped the member finalising, if any. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new FundStructureCloseStep(
    memberShortCode: "...",  // required — The node code of the member in the structure.
    fund: new ResourceId(...),  // required
    step: 0,  // required — The position of the member in the close order.
    status: "...",  // required — What happened to the member. Available values: Finalised, AlreadyFinal, Failed, Skipped.
    failure: "..."  // optional — The failure that stopped the member finalising, if any.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<FundStructureCloseStep>(json);
```

- [ResourceId](ResourceId.md)


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

