# Finbourne.Sdk.Luminesce.Model.AvailableField

Information about a field that can be designed on (regardless if it currently is) Kind of a \"mini-available catalog entry\"
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Name** | **string** | Required | Name of the Field |
| **DataType** | **DataType** | Optional | *No description available.* |
| **FieldType** | **FieldType** | Required | *No description available.* |
| **IsMain** | **bool?** | Optional | Is this a Main Field within the Provider |
| **IsPrimaryKey** | **bool?** | Optional | Is this a member of the PrimaryKey of the Provider |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new AvailableField(
    name: "...",  // required — Name of the Field
    dataType: ,  // optional
    fieldType: ,  // required
    isMain: true,  // optional — Is this a Main Field within the Provider
    isPrimaryKey: true  // optional — Is this a member of the PrimaryKey of the Provider
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<AvailableField>(json);
```



[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

