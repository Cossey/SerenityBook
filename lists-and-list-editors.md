# List and List Editors

### Expression Fields \(Calculated / Joined fields\)

#### Inserting via a Form

When inserting a new item into a List via a Form/Dialog you must override the `validateEntity` function to set the values of expression fields that can't be evaluated in memory:

```js
protected validateEntity(row: EntityRow, id: number) {
    if (!super.validateEntity(row, id)) return false;  

    row.ProductID = Q.toId(row.ProductID);    
    row.ProductName = ProductRow.getLookup().itemById[row.ProductID].ProductName;

    return true;
}
```

#### Inserting via a Picker

When using a picker to insert items into a List when you have a expression field, you need to populate the expression field as the List is inserted client side and no server callback is performed \(expression fields are done Server side\). For example, the `ProductName` field below:

```js
var item = <EntityRow>{
    ProductID: sourcerow.ProductID,
    ProductName: sourcerow.ProductName //This is an expression field
};

var id = this.getNextId();
item[this.getIdProperty()] = id;
this.view.addItem(item);
```

This will then make sure this field is populated when inserted. This does not apply to existing items in a List.

