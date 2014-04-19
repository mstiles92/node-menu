node-menu
=========

This module allows to create cosole menue for your REPL application. It allows you to register menu items with their handlers. Optionally you may provide set of arguments being passed to handler.

## Installation

    npm install node-menu

## Usage

```javascript
var menu = require('node-menu');

menu.addItem(
    "No parameters", 
    function() {
        console.log("No parameters is invoked");
    });

menu.addItem(
    "Sum", 
    function(op1, op2) {
        var sum = op1 + op2;
        console.log("Sum " + op1 + "+" + op2 + "=" + sum);
    }, 
    ["op1", "op2"]);

menu.addItem(
    "String and Bool parameters", 
    function(str, b) {
        console.log("String is: " + str);
        console.log("Bool is: " + b);
    },
    ["str", "bool"]);
menu.start();
```

Output of this example:

        _   __            __       __  ___
       / | / /____   ____/ /___   /  |/  /___   ____   __  __
      /  |/ // __ \ / __  // _ \ / /|_/ // _ \ / __ \ / / / /
     / /|  // /_/ // /_/ //  __// /  / //  __// / / // /_/ /
    /_/ |_/ \____/ \__,_/ \___//_/  /_/ \___//_/ /_/ \__,_/  v.0.0.2
     
     
    1. No parameters
    2. Sum: "op1" "op2"
    3. String and Bool parameters: "str" "bool"
    4. Quit
      
    Please provide input at promt as: >> ItemNumber arg1, arg2 ... (i.e. >> 2 "some string", 2, 4, true)
     
    >> 

To invoke item without arguments just type number and Enter. To invoke item with arguments, type number comma delimitered arguments after space. String arguments must be double quoted.

## To be continued...