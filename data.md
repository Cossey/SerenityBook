# Data

Data table definitions are specified in a `Row.cs` file. Refer to the [Rows ](/rows.md)page for more information.

### Server Side Operations

##### Retrieving Data

You can retrieve data from a row by using an instantiated connection object.

```csharp
using (IDbConnection connection = SqlConnections.NewFor<ProjectRow>())
{
    var Row = connection.TryById<CustomerRow>(1);
}
```





