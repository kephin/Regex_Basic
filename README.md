# Regular Expression

Regular Expression is used in programming language to **match** parts of strings. You create **patterns** to help you do the matching.

## Using Test method: `test` method returns true or false

```js
const sentence = 'hello world'
const regex = /hello/
regex.test(sentence) // returns true
```

## Or operator: `|`

```js
const sentence = 'I love dogs'
const regex = /dog|cat/
```

## Case insensitive: `i` flag

```js
const sentence = 'I love Dogs'
const regex = /dog|cat/i
```

## Extract matches: `match` method

```js
const sentence = 'I love JavaScript!'
const regex = /javascript/i
sentence.match(regex) // returns ['JavaScript']
```

## Find more than the first match: `g` flag

```js
const sentence = 'Twinkle, twinkle, little start'
const regex = /twinkle/ig
sentence.match(regex) // returns ['Twinkle', 'twinkle']
```

## Match anything with wildcard period: `.` is a wildcard character, it can stands for everything

```js
const humStr = "I'll hum a song"
const hugStr = 'Bear hug'
const regex = /hu./
humStr.match(regex) // returns ['hum']
hugStr.match(regex) // returns ['hug']
```

## Match single character with multiple possibilities: `[]`

```js
const regex = /b[aiu]g/ // matches bag, big, bug
```

## Match range of letters or numbers of the alphabet

```js
const regex = /[a-z0-9]/ig // matches letters a~z and numbers 0~9
```

## Match everything except, which is negated character set: `^`

```js
const regex = /[^0-9aeiou]/ig // matches everything except 0~9 and a, e, i, o, u
```

## Match characters that occur one or more times: `+`

```js
const string = 'Mississippi'
const regex = /s+/g // matches ['ss', 'ss']
```

## Match characters that occur zero or more times: `*`

```js
const goal = 'goooooal!'
const gut = 'gut feeling'
const non = 'over the moon'
const regex = /go*/
goal.match(regex) // returns ['googooooo']
gut.match(regex) // returns ['g']
non.match(regex) // returns null
```

## :bulb: Find characters with lazy matching

Greedy match(default): Find the **longest** possible part of the string that fits the regex pattern
Lazy match: Find the **shortest** possible part of the string that fits the regex pattern

```js
const titanic = 'titanic'
const regex = /t[a-z]*i/ // returns ['titani']
const lazyRegex = /t[a-z]*?i/ // returns ['ti']

const text = <hi>Hello</hi>
const regex = /<.*>/ // returns ['<hi>Hello</hi>']
const lazyRegex = /<.*?>/ // returns ['<hi>']
```

## Basic regex challenge: Find one or more criminals in a hunt

```js
const hunt = 'P1P2P3P4CCCP5P6CCCCP7P8'
const regex = /C+/g // returns ['CCC', 'CCCC']
```
