compare-strings
=================

Finds degree of similarity between two strings, based on [Dice's Coefficient](http://en.wikipedia.org/wiki/S%C3%B8rensen%E2%80%93Dice_coefficient) and [Levenshtein Distance](http://en.wikipedia.org/wiki/Levenshtein_distance).

## Table of Contents

* [Usage](#usage)
* [API](#api)
    * [compareTwoStrings(string1, string2)](#comparetwostringsstring1-string2)
        * [Arguments](#arguments)
        * [Returns](#returns)
        * [Examples](#examples)


## Usage
Install using:

```shell
npm install compare-strings --save
```

In your code:

```javascript
var compareStrings = require('compare-strings');

var similarity = compareStrings('healed', 'sealed');
```
## API

### compareStrings(string1, string2)

Returns a fraction between 0 and 1, which indicates the degree of similarity between the two strings. 0 indicates completely different strings, 1 indicates identical strings. The comparison is case-insensitive.

##### Arguments
  
1. string1 (string): The first string
2. string2 (string): The second string
  
Order does not make a difference.
  
##### Returns
  
(number): A fraction from 0 to 1, both inclusive. Higher number indicates more similarity.

##### Examples
  
```javascript
stringSimilarity.compareTwoStrings('healed', 'sealed');
// → 0.8166666666666667

stringSimilarity.compareTwoStrings('Olive-green table for sale, in extremely good condition.', 
  'For sale: table in very good  condition, olive green in colour.');
// → 0.4774114774114774

stringSimilarity.compareTwoStrings('Olive-green table for sale, in extremely good condition.', 
  'For sale: green Subaru Impreza, 210,000 miles');
// → 0.27886002886002886

stringSimilarity.compareTwoStrings('Olive-green table for sale, in extremely good condition.', 
  'Wanted: mountain bike with at least 21 gears.');
// → 0.159992784992785
```