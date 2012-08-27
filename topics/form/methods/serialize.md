# AG.form.serialize

## Summary
`serialize()` allows you to get form values in one nice object.

When you are developing an application that needs to read form values (for example to save to local storage), you can read them from form element using this function.

Key name for the input/textarea/select field is resolved using the following order: DOM name attribute, DOM id attribute, index number of field in Form DOM.

## Quick example:
```javascript
var valueobject = AG.form.serialize(document.querySelector("form#myForm"));
```

## Syntax
```javascript
AG.form.serialize(formNode);
```

**Parameters**

* *node* **formNode**<br>
  FORM DOM Node.

## Returns

*object*
Contains key/value pairs of form input/textarea/select fields.

## Supported platforms
* iOS