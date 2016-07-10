[![Build Status](https://travis-ci.org/ENikS/LINQ.svg?branch=master)](https://travis-ci.org/ENikS/LINQ) 
[![Coverage Status](https://coveralls.io/repos/github/ENikS/LINQ/badge.svg?branch=master)](https://coveralls.io/github/ENikS/LINQ?branch=master)
[![npm version](https://badge.fury.io/js/linq-es2015.svg)](https://badge.fury.io/js/linq-es2015)
[![Downloads](https://img.shields.io/npm/dm/linq-es2015.svg)](https://www.npmjs.com/package/linq-es2015)
## Language-Integrated Query (LINQ) 

This library is a set of features that extends powerful query capabilities to any JavaScript based language. It is a complete implementation of LINQ (Language-Integrated Query) pattern.

The library is a continuous effort to implement LINQ using latest features of TypeScript and JavaScript languages (For [ES5](http://www.ecma-international.org/ecma-262/5.1/) compatible library look at [linq-es5](https://github.com/ENikS/LINQ/tree/linq-es5) branch). The library is implemented in TypeScript and transpiled into JavaScript. It is distributed as a native node module. 
Browserified and minified standalone UMD modules are located in ./dist directory and could be used directly in compatible browsers.
This library uses latest [ECMAScript 2015](http://www.ecma-international.org/ecma-262/6.0/) language specification and utilizes [Iterables](http://www.ecma-international.org/ecma-262/6.0/#sec-iterable-interface): ([ [System.iterator] ](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Iteration_protocols)), JavaScript generators ([function*](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function*)), and [for of](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...of) loops. All relevant methods are implemented with deferred execution so no unnecessary iterations are performed. 
The code is backwards compatible with [linq-es5](https://github.com/ENikS/LINQ/tree/linq-es5) and [C#](https://msdn.microsoft.com/en-us/library/system.linq.enumerable.aspx) implementations.

### Installation
```
npm install linq-es2015
```

### Using 
```javascript
import {asEnumerable, Range} from "linq-es2015";


var count =  asEnumerable( [1, 2, 3, 4, 5, 6, 7, 8, 9, 10] ).Where(a => a % 2 == 1)
                                                            .Count()

var iterable = asEnumerable(people)
               .GroupJoin(pets,
                          person => person, 
                          pet => pet.Owner,
                          (person, petCollection) => {
                              return {
                                  Owner: person.Name,
                                  Pets: asEnumerable(petCollection)
                                       .Select(pet=> pet.Name)
                                       .ToArray()
                              };
                          });

```
For live example you could play with please follow these links to ([Node](https://tonicdev.com/eniks/using-linq)) or ([Browser](https://jsfiddle.net/ENikS/pyvjcfa0)) 

### Naming Convention
Method names follow original C# convention (Name starts with capital letter) for compatibility reasons. It is done so that code could be cut/pasted from C# to JavaScritp with just minor reformatting.

### Implemented methods
For list of implemented methods and for help on individual methods please follow this link:
https://github.com/ENikS/LINQ/wiki

