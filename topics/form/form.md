# AG.form

The **AG.form** namespace gives access to form handling javascript helpers. They are useful for getting form values to json and/or submitting form via ajax.

## Methods

* [AG.form.serialize](methods/serialize.md)
* [AG.form.hijack](methods/hijack.md)

## Full example

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <script src="../appgyver/appgyver.js"></script>
    <script>
  <script>
    document.addEventListener("DOMContentLoaded", function(){
      var formEl = document.querySelector("form#myForm");
      AG.form.hijack(formEl, {
        success: function(xhr){
          AG.GUI.alert("XHR successful!", "Posted data: +" JSON.stringify(AG.form.serialize(formEl)));
        },
        failure: function(xhr){
          AG.GUI.alert("XHR failure!", "Posted data: +" JSON.stringify(AG.form.serialize(formEl)));
        }
      })
    });
  </script>
</head>
<body>
  <form id="myForm" action="http://example.com/target.php">
    Name:<input name="name" value="Obama" /><br />
    Description:<textarea name="description">Lorem ipsum.</textarea><br />
    Boolean:<input name="boolean"type="checkbox" /><br />
    Textarea:<textarea id="nameless"></textarea><br />
    Nameless and idless input:<input value="nameless_idless" /><br />
    Sex:
    <input type="radio" name="sex" value="male" /> Male
    <input type="radio" name="sex" value="female" /> Female
    <input type="radio" name="sex" value="yesplease" /> Yes please<br />
    When:
    <select name="when">
      <option value="rightnow">Right Now</options>
      <option value="waitasec">Wait a sec</options>
    </select><br />
    <input type="submit" />
  </form>
</body>
</html>
```