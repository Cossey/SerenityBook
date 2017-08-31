# Grid Quick Search

### Options

Options are configured via the `QuickSearch` attribute.

##### Options

| Option | Name | Type | Description |
| :--- | :--- | :--- | :--- |
| searchType | Search Type | Enum _Serenity.Data.Mapping.SearchType_ | Sets the Search type, by default this is StartsWith |
| numericOnly | Numerical Only | int |  |
| isExplicit |  | bool |  |

##### SearchType \(Serenity.Data.Mapping\)

| Value | Info |
| :--- | :--- |
| Auto |  |
| Contains | Search anywhere within the columns value for a match |
| Equals | Search must match columns value exactly |
| StartsWith | Column value must start with search text |

### Quick Search Fields

Since it is possible to apply the QuickSearch attribute to multiple columns in a `Row.cs` file, when searching using the Quick Search it will search all columns with the attribute. You can additionally offer specific fields to perform a Quick Search on instead of all fields via the Quick Search Fields option.

![](/assets/quicksearchfields.png)

The possible fields to choose from are configured from the function `getQuickSearchFields` in the `Grid.ts` file. You must return an object array with name and title properties.

```typescript
protected getQuickSearchFields(): Serenity.QuickSearchField[] {
    return [
        { name: '', title: 'All' },
        { name: 'CustomerID', title: 'Customer ID' },
        { name: 'CompanyName', title: 'Company Name' },
        { name: 'ContactName', title: 'Contact Name' }
    ];
}
```

> You should also include the `{ name: '', title: 'all' }` object first in your own Quick Search Fields so that you can disable filtering by a specific field.

### How To's

##### Quick Search a Column using Contains

```csharp
[DisplayName("Name"), Size(255), NotNull, QuickSearch(SearchType.Contains)]
public String Name
{
    get { return Fields.Name[this]; }
    set { Fields.Name[this] = value; }
}
```

##### Remove the Quick Search

To remove the Quick Search from a Grid, override the `createQuickSearchInput()` function to do nothing in an `Grid.ts` file like below:

```typescript
protected createQuickSearchInput() { }
```



