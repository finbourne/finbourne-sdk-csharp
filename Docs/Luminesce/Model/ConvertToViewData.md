# Finbourne.Sdk.Luminesce.Model.ConvertToViewData

Representation of view data where will template the data into a 'create view' sql
## Properties

| Name | Type | Required | Description |
|------|------|----------|-------------|
| **Query** | **string** | Required | view query |
| **Name** | **string** | Required | Name of view |
| **Description** | **string** | Optional | Description of view |
| **DocumentationLink** | **string** | Optional | Documentation link |
| **ViewParameters** | [List&lt;ViewParameter&gt;](ViewParameter.md) | Optional | View parameters |
| **OtherParameters** | **Dictionary&lt;string, string&gt;** | Optional | Other parameters not explicitly handled by the ConvertToView generation. These will be populated by the \&quot;From SQL\&quot; and should simply be returned by the web GUI should the user edit / update / regenerate |
| **StartingVariableName** | **string** | Optional | Which variable the this start with, null if not started from a full Create View Sql Statement. |


## Usage

### Creating an instance

```csharp
using Finbourne.Sdk.Services.Luminesce.Model;

var instance = new ConvertToViewData(
    query: "...",  // required — view query
    name: "...",  // required — Name of view
    description: "...",  // optional — Description of view
    documentationLink: "...",  // optional — Documentation link
    viewParameters: new List<ViewParameter>(),  // optional — View parameters
    otherParameters: ,  // optional — Other parameters not explicitly handled by the ConvertToView generation. These will be populated by the \&quot;From SQL\&quot; and should simply be returned by the web GUI should the user edit / update / regenerate
    startingVariableName: "..."  // optional — Which variable the this start with, null if not started from a full Create View Sql Statement.
);
```
### Serializing to JSON

```csharp
var json = JsonConvert.SerializeObject(instance, Formatting.Indented);
```

### Deserializing from JSON

```csharp
var instance = JsonConvert.DeserializeObject<ConvertToViewData>(json);
```

- [ViewParameter](ViewParameter.md) — used in `ViewParameters`


[Back to top](#) · [Back to API list](../../api_endpoints.md) · [Back to Model list](../../models.md) · [Back to README](../../../README.md)

