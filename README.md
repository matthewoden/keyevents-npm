KeyEvents v1.0.5
=================
 A simple shortcut mixin for react.js. Useful for single button presses.

Installation
------------
```bash
$ npm install keyevents

```
Usage
-----

This mixin exposes as itself as a function which looks for a listener object.

#### Example

``` js
var KeyEvents = require('keyevents');


var ExampleComponent = React.createComponent({
  mixins:[keyEvents],

  componentKeyEvents:function(){
    return{
       a:function() {
        console.log('you pressed a!');
      },
      backspace: function() {
        console.log('back that space up!');
      }
    }
  }


...

```

The object's key is the human-readable version, the value is the keycode associated with it. Currently, everything runs on mousedown, so you'll probably want to include a timeout in your method to handle long presses.

#### Key Mapping


The keys included so far map as the following:
``` js
{
  8 : 'backspace',
  9 : 'tab',
  13 : 'enter',
  16 : 'shift',
  17 : 'ctrl',
  18 : 'alt',
  19 : 'pause',
  20 : 'capsLock',
  27 : 'escape',
  33 : 'pageUp',
  34 : 'pageDown',
  35 : 'end',
  36 : 'home',
  37 : 'left',
  38 : 'up',
  39 : 'right',
  40 : 'down',
  45 : 'insert',
  46 : 'delete',
  48 : '0',
  49 : '1',
  50 : '2',
  51 : '3',
  52 : '4',
  53 : '5',
  54 : '6',
  55 : '7',
  56 : '8',
  57 : '9',
  65 : 'a',
  66 : 'b',
  67 : 'c',
  68 : 'd',
  69 : 'e',
  70 : 'f',
  71 : 'g',
  72 : 'h',
  73 : 'i',
  74 : 'j',
  75 : 'k',
  76 : 'l',
  77 : 'm',
  78 : 'n',
  79 : 'o',
  80 : 'p',
  81 : 'q',
  82 : 'r',
  83 : 's',
  84 : 't',
  85 : 'u',
  86 : 'v',
  87 : 'w',
  88 : 'x',
  89 : 'y',
  90 : 'z',
  91 : 'leftWindowKey',
  92 : 'rightWindowKey',
  93 : 'select',
  96 : 'numpad0',
  97 : 'numpad1',
  98 : 'numpad2',
  99 : 'numpad3',
  100 : 'numpad4',
  101 : 'numpad5',
  102 : 'numpad6',
  103 : 'numpad7',
  104 : 'numpad8',
  105 : 'numpad9',
  106 : 'multiply',
  107 : 'add',
  109 : 'subtract',
  110 : 'decimal ',
  111 : 'divide',
  112 : 'f1',
  113 : 'f2',
  114 : 'f3',
  115 : 'f4',
  116 : 'f5',
  117 : 'f6',
  118 : 'f7',
  119 : 'f8',
  120 : 'f9',
  121 : 'f10',
  122 : 'f11',
  123 : 'f12',
  144 : 'numLock',
  145 : 'scrollLock',
  186 : ';',
  187 : '=',
  188 : ',',
  189 : '-',
  190 : '.',
  191 : '/',
  192 : '`',
  219 : '{',
  220 : '\\',
  221 : '}',
  22 : '\''
}

```
## Roadmap
Handle shift + Key, and general key combinations.

## License
[MIT](https://github.com/matthewoden/keyevents-npm/blob/master/LICENSE)
