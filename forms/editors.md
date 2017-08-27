# Form Editors

The following form editors are configured via attributes set on the fields in a `Form.cs` file.

## Text

### Text Area Editor

### String Editor

### Email Editor

![](/assets/email.png)

The email editor consists of two texts boxes divided by an at \(@\) symbol.

### Password Editor

### Masked Editor

### URL Editor

### 

## Numerical

![](/assets/decint.png)

Numerical fields restrict the input mainly to numerals. In the case of the Decimal Editor, the decimal point can also be pressed.

### Integer Editor

The integer editor only allows for numerals to be entered into a input box.

### Decimal Editor

The Decimal Editor allows for a fractional value to be entered into a form.

#### Options

##### Minimum and Maximum values

By default the Decimal Editor does not allow negative values. To allow this the `MinValue` and `MaxValue` options must be set.

```csharp
[DecimalEditor(MinValue = "-999.99", MaxValue = "999.99")]
public Decimal ExampleProperty { get; set; }
```

> When setting the `MinValue` and `MaxValue` options, make sure you use the same number of digits in both the minimum and maximum.

##### Decimal places

The decimal places can be configured by setting the `Scale` attribute to the amount of places. For example, to set an input of two decimal places:

```csharp
[DisplayName("Example Property"), Scale(2)]
public Decimal? ExampleProperty
{
    get { return Fields.ExampleProperty[this]; }
    set { Fields.ExampleProperty[this] = value; }
}
```

> In some cases like accounting, you may want to `Scale` to 4 decimal places.

### Phone Editor

### Boolean Editor

![](/assets/bool.png)

The boolean editor is typically a checkbox field.

### Radio Button Editor

### Check List Editor

### Check Tree Editor

### Html Content Editor

## Files and Uploading

### FileUploadEditor

![](/assets/fileupload.png)

### ImageUploadEditor

![](/assets/filesel.png)

## Date and Time

### DateTimeEditor

![](/assets/date.png)

The Date and Time editor allows you to select a date from a drop down.

### DateYearEditor

### TimeEditor

## Drop downs

### EnumEditor

### [LookupEditor](/lookup-editors.md)

![](/assets/lookup.png)

The lookup editor is a drop down that references data from another table in the database. It has a Filter text at the top and can dynamically load additional data. It is the [Select2 ](http://select2.github.io/select2/)drop down for jQuery. Refer to the [Lookup Editors](/lookup-editors.md) section for more information on how to use this Editor.

### 

### 


