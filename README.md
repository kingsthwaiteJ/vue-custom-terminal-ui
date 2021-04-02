# Vue Custom Terminal UI

A custom Vue.js terminal component that gives access to the browser's console, along with access to some cool custom methods.

## Install

```
  npm i vue-terminal-ui --save
```

## Usage

```
// import plugin
import VueTerminal from 'vue-terminal-ui'

// add to components section
components{
    VueTerminal
},
// add method to call on command is typed
 methods: {
    onCliCommand(data, resolve, reject){
      // typed command is available in data.text
      // don't forget to resolve or reject the Promise
      setTimeout(()=> {
        resolve('')
      }, 300)
    }
  },
// use in template
   <VueTerminal :intro="intro"
                console-sign="$"
                allow-arbitrary
                height="500px"
                @command="onCliCommand"></VueTerminal>
```

## Properties & Events

*props*

- `intro` (String) - intro text when terminal starts;
- `console-sign`(String) - starting symbol for each command line, eg. `my-folder/master $` or just `>>`;
- `allow-arbitrary`(Boolean) - allow type any command in addition to basic ones, then `@command` will be called;
- `height`(String) - UI block height, eg. `500px`;

*event*

- `@command` - callback function to call with command; accepts text, and resolve/reject callbacks

## ToDo

- get rid of jQuery dependancy

## License

MIT
