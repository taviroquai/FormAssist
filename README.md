# FormAssist

FormAssist is a javascript utility based on jQuery and Ajax that allows the user to configure form validation rules.

## Another one? Why? What's the difference?

Because web application validation is a mess and normally the same form have splitten validation rules on client and server which leads to 
unmaintainable and buggy code.
This centralizes validation on server, where you may also need to do database validation.
Nevertheless, the main purpose is to submit the form just once!

## Features?

- Validates single form fields
- Validates groups of related form fields
- Field inline messages

## How to use? Could not be simpler...

Just create a form and add a tag with class **.assist-msg** and a class refering the name of the rule ie. **.assist-msg-rule1** where you want the inline validation message

```html
<span class="assist-msg assist-msg-rule1"></span>
```

And the full form example ...
```html
<form action="submit.php">
    <div class="form-group">
        <label>Email?</label>
        <span class="assist-msg assist-msg-rule1"></span>
        <input class="form-control" type="text" name="email" placeholder="Email address" />
    </div>
    <button class="btn btn-large btn-primary btn-block" type="submit">Submit</button>
</form>
```

Then just create a new FormAssist instance with:
```javascript
$('form').FormAssist(function(form, e) {
    e.preventDefault(); // example purposes only
    form.validateAll();
    return false; // example purposes only
}).rule('rule1', 'input[name="email"]');
```

## What's the expected server result?

JSON response example for an invalid field:
```javascript
{"result":0,"type":"has-error","msg":"Email cannot be empty"}
```
JSON response example for a valid field:
```javascript
{"result":1,"type":"has-success","msg":"My custom message..."}
```
## Live example?

See a live example on how to use it in http://marcoafonso.pt/tests/validator/index.php

## TODO: documentation
