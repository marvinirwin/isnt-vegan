# isnt-vegan

Isnt-Vegan helps you to find out which food ingredients are vegan / non-vegan. It can answer that on 1 ingredient or on a list of ingredients. It uses a 850+ entries list of non-vegan ingredients.


## Why?

We are aware that 'non-veganism' and the definition of it can be a hot topic. We created the vegan list keeping in mind that non-veganism in dietary terms, it denotes the practice of dispensing with all products not derived wholly or partly from animals.

Our first step is the approach to help people understand, which products, and where applicable its ingredients, involve, or have involved, the use of any animal product, by-product or derivative. It is not driven about any non-vegan lifestyle choice or stereotype.
We welcome and appreciate any help and concerence regarding the vegan/cantbevegan list.

Currently we are unfortunatly not adressing any other forms of exploitation of, and cruelty to, animals for clothing, cosmetics or any other purpose.

**Thank you all for your comments, we appreciate the discussion, as we grow and learn from your input.**

## Sources

We want to make sure that you understand how isnt-vegan is implemented. We analyzed as many good information websites for non-vegan / vegan ingredients as we found to get a very accurate list of ingredients. **However, feel free to send a pull request with an updated version of the list.**

**and we added also a few ourselves...**

## Usage

### Add

```bash
yarn add isnt-vegan
```

or

```bash
npm install isnt-vegan --save
```

### example

```javascript
const isVegan = require('isnt-vegan');

// or

import * as isVegan from 'isnt-vegan';

// example for single ingredient
isntVegan.isntVeganIngredient('soy'); // false
isntVegan.isntVeganIngredient('milk'); // true

// example for list of ingredients
isntVegan.isntVeganIngredientList(['aspic', 'albumin']); // true
isntVegan.isntVeganIngredientList(['soy', 'cacao butter']); // false

// example for list of ingredients
isntVegan.containsVeganIngredients(['aspic', 'albumin', 'soy']); // ['soy']
isntVegan.containsVeganIngredients(['soy', 'cacao butter']); // ['soy', 'cacao butter']

// example for list of ingredients wich contain flagged and non-vegan ingredients
isVegan.checkIngredients(['soy', 'cacao butter', 'pork', 'beef', 'glycine']);
// returns
// {
//   nonvegan: ['pork', 'beef'],
//   flagged: ['glycine']
// }

// or

import { checkIngredients } from 'isnt-vegan';

// example for list of ingredients wich contain flagged and non-vegan ingredients
checkIngredients(['soy', 'cacao butter', 'pork', 'beef', 'glycine']);

// returns
// {
//   nonvegan: ['cacao butter', 'soy'],
//   flagged: ['glycine']
// }
```

### real world example

[Products searched on USDA Food Composition Databases](https://ndb.nal.usda.gov/ndb/search/list)

```javascript
const isVegan = require('isnt-vegan');

// MOSER ROTH, DARK CHOCOLATE
isntVegan.isntVeganIngredientList([
  'COCOA LIQUOR',
  'SUGAR',
  'COCOA BUTTER',
  'ALKALIZED REDUCED FAT COCOA POWDER',
  'SOY LECITHIN EMULSIFIER',
  'GROUND VANILLA'
]); // returns false
```

Checkout: [RunKit "is-vegan-playground" for more examples](https://runkit.com/hmontazeri/isnt-vegan-playground)



## Test

```bash
yarn test
```


## TODO

- extend list

