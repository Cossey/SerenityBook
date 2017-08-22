# List and List Editors

#### Expression Fields \(Calculated / Joined fields\)

When using a picker and in code you want to insert data into a List

```js
var item = <EntityRow>{
    ProductID: sourcerow.ProductID,
    ProductName: sourcerow.ProductName
};

var id = this.getNextId();
item[this.getIdProperty()] = id;
this.view.addItem(item);
```



