# List and List Editors

#### Expression Fields \(Calculated / Joined fields\)

When using a picker to insert items into a List when you have a calculated field, you need to populate the calculated field as the List is inserted client side and no server callback is performed \(calculated/joined fields are done Server side\). For example, the `ProductName` field below:

```js
var item = <EntityRow>{
    ProductID: sourcerow.ProductID,
    ProductName: sourcerow.ProductName //This is a calculated field
};

var id = this.getNextId();
item[this.getIdProperty()] = id;
this.view.addItem(item);
```

This will then make sure this field is populated when inserted. This does not apply to existing items in a List.

