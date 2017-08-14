# Requiring a Quick Filter Value

If you require a Quick Filter value for a field then you can follow some approaches below.

### Lookup Editors

##### Disable the Ability to clear the Lookup Value

Set the Select2 option `allowClear` to false by using the Attribute `[QuickFilterOption("AllowClear", false)]` on a column property.

