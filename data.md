# Data

Data table definitions are specified in a `Row.cs` file. Refer to the [Rows ](/rows.md)page for more information.

### Server Side Operations

##### Retrieving Data by ID

You can retrieve data from a row by using an instantiated connection object.

```csharp
using (IDbConnection connection = SqlConnections.NewFor<CustomerRow>())
{
    var Row = connection.TryById<CustomerRow>(1); //Retrieve Customer by ID 1
}
```

##### Retrieving Data by Criteria

You can retrieve a single or multiple rows based on provided criteria.

```csharp
using (IDbConnection connection = SqlConnections.NewFor<CustomerRow>())
{
    var Row = connection.TryFirst<CustomerRow>(CustomerRow.Fields.Country == "New Zealand"); 
}
```



