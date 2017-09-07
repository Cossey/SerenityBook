# Grid Columns

Grid columns are defined in a `Columns.cs` file.

## Attributes

#### Edit Link

The `[EditLink]` attribute transforms a columns text into a link in the grid. This link will show a Form Dialog with the selected rows data.

##### Options

| Option | Type | Description |
| :--- | :--- | :--- |
| CssString | String |  |
| IdField | String |  |
| ItemType | String |  |

> You can find out more about Forms and Dialogs in the [Forms](/forms.md) section.



#### Sort Order

The `[SortOrder]` attribute sets the sorting for a column. This can be used concurrently with other columns to apply multiple column sorting.

##### Options

| Option | Type | Description |
| :--- | :--- | :--- |
| sortOrder | int | The column sort index. |
| descending | bool | Sort descending. |



#### Width

The `[Width]` attribute sets the default size \(in pixels\) of the column.

##### Options

| Option | Type | Description |
| :--- | :--- | :--- |
| value | int | The width of the column. |
| Max | int | The maximum allowed width of the column. |
| Min | int | The minimum allowed width of the column. |



