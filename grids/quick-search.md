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
| StartsWith |  Column value must start with search text |



##### Contains Quick Search

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



