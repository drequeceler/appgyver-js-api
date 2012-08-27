# AG.form.hijack

## Summary
`hijack()` allows you to change form HTTP POST to ajax POST. Form action attribute is used as a default POST target.

## Quick example:
```javascript
AG.form.hijack(document.querySelector("form#myForm"), {
  success: function(xhr) {
    // ajax request was successful
  },
  failure:function(xhr) {
    // ajax request failed
  }
}));
```

## Syntax
```javascript
AG.form.hijack(formNode, options);
```

**Parameters**

* *node* **formNode**<br>
  FORM DOM Node.

* *object* **options**<br>
  Options object takes optional keys:
    url - target url for POST (string)
    success - success callback (function)
    failure - failure callback (function)

## Returns

*node*
Returns given form node.

## Supported platforms
* iOS