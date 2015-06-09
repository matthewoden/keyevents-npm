KeyEvents
=========

Installation
------------
```bash
$ npm install keyevents

```

Upgrading
-----
KeyEvents 2.0 is out! If you're not familiar with SemVer, that means you'll have to do some work to hop on the new version. See changes to componentKeyEvents below.

Usage
-----

This library takes the result of event.which, and returns the key in a human readable format (in english). It can be used as a mixin, or as a utility method (in case you're moving on to ES6 Classes). The main method, componentKeyEvents, runs on keydown, and returns the key assigned. The exact functionality is up to you.

### Example (using an object lookup)

``` js
var KeyEvents = require('keyevents');

var ExampleComponent = React.createComponent({
  mixins:[KeyEvents],

  componentKeyEvents:function(keypressed){

     var ExampleObject = {
      // You can assign functions directly:
      a:function() {
        console.log('you pressed a!')
      },

      backspace: function() {
        console.log('back that space up!')
      },

      // ... or use component methods!
      p: this.componentMethod(arguments)
    }

    ExampleObject[keypressed]();
  }


...

```

Again, how you handle it is up to you. You could run through your keybindings as with a switch. You can also define all your keybindings in an external file, then share them components.

### Methods

#### this.componentKeyEvents()
Your component's method for handling key presses. It's run on keyDown.

#### this.destroyKeyEvents()
this removes all keydown event listners. When used as a mixin, it runs automatically on componentWillUnmount.

#### this.createKeyEvents()
this initializes keydown event listeners. When used as a mixin, it runs automatically on componentWillMount.

### Key Mapping

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

## Changelog
- June 9th, 2015: Changed the functionality of ComponentKeyEvents to be an implementation detail.

## Roadmap
- Add in support for custom key dictionaries
- Handle shift + Key, and general key combinations.

## License
[MIT](https://github.com/matthewoden/keyevents-npm/blob/master/LICENSE)
