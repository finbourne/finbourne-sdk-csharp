# Finbourne.Sdk.Lusid.Model.PartnerAllocationPoolSources

The amount reaching a pool by each route: its bucket's lines, lines tagged with its character and lines allocated  directly to one partner.
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Bucket** | **decimal** | Required | The amount reaching the pool from the lines its bucket&#39;s rule placed. |
| **LineTag** | **decimal** | Required | The amount reaching the pool from lines tagged with its character. |
| **Direct** | **decimal** | Required | The amount reaching the pool from lines allocated directly to one partner. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Lusid.Model;

var instance = new PartnerAllocationPoolSources(
    bucket: 0.0d,  // required — The amount reaching the pool from the lines its bucket&#39;s rule placed.
    lineTag: 0.0d,  // required — The amount reaching the pool from lines tagged with its character.
    direct: 0.0d  // required — The amount reaching the pool from lines allocated directly to one partner.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<PartnerAllocationPoolSources>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

