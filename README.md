
# FormAssist

FormAssist is a javascript utility based on jQuery and Ajax that allows the user to configure form validation rules.

## Another one? Why? Whats the difference?

Because web application validation is a mess and normally the same form have splitten validation rules on client and server which leads to 
unmaintainable and buggy code.
This centralizes validation on server, where you may also need to do database validation.
Nevertheless, the main purpose is to submit the form just once!

## Features?

- Validates single form fields
- Validates groups of related form fields
- Field inline messages

## How to use? Could not be simpler...

```javascript
$('form').FormAssist().rule('rule1', 'input[name="email"]');
```

## Whats the expected Ajax server result?

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
