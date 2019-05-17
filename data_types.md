# Data Types

There are many data types in YAML:


## Scalar

The scalar type is used to represent values like `numbers` and `strings`, and their different variants (i.e. Integers, Floats, Booleans...). For Scalar types we don't need to use quotes unless we want to define a string that uses special characters. We can either use single or double quotes for a string, but with double quotes we can represent escaped characters (for ASCII and Unicode).

```yaml
example:
  aString: hello
  aQuotedString: 'hello'
  doubleQuotedString: "hello\nfriend!"
```

The equivalent in JSON:
```json
{
  "example": {
    "aString": "hello",
    "aQuotedString": "hello",
    "doubleQuotedString": "hello\nfriend!"
  }
}
```
<br/>

### Representing numbers

It is possible to represent numbers in many different ways with yaml. The example below represents the number `123` as integer, hexadecimal (base 16) and octal notation (base 8).

```yaml
int: 123
hex: 0x7B
octal: 0173
```

We can also represent different types of numbers, from floats to exponential numbers, and also `nan` (Not A Number) and infinity (and negative infinity!).

```yaml
float: 3.1415926535
exponential: 1.23e+05
nan: NAN
infinity: .inf
negativeInfinity: -.inf
```
<br/>

## Sequences

We use sequences to represent `lists` or `arrays`. The elements of a list should have a dash in front of them. It is also possible to nest lists by using indentation.

__Note:__ Sequences can also be defined with `inline syntax` by using square brackets.

```yaml
myFavFoods:
  - Pizza
  - Ice cream
  - Avocado

products:
  -
    - Ice cream
    - 3
    - Sterling Pounds
  -
    - Helado
    - 4.5
    - Euros

inlineSequence: ["I", "love", "ice cream"]
```

The equivalent in JSON:
```json
{
  "myFavFoods": ["Pizza", "Ice cream", "Avocado"],
  "products": [
    ["Ice cream", 3, "Sterling Pounds"],
    ["Helado", 4.5, "Euros"]
  ],
  "inlineSequence": ["I", "love", "ice cream"]
}
```
<br/>

## Mappings

Mappings are key-value pairs, such as a `dictionary` or `object`, which are made of a keyword which is followed by a colon, and the value. These can be combined with scalar values or lists to represent data.

__Note:__ Mappings can also be defined with `inline syntax` by using curly braces.

```yaml
myPet: dog
myFavPets:
  - dog
  - cat

myDog:
  name: "Yoko"
  age: 11
  favThings:
    - Naps
    - Cuddles
    - Sticks
  dislikes:
    - horses: true
    - lemons: true
    - cats: false

  inlineMapping: {dog: true, cat: false}
```

The equivalent in JSON:
```json
{
  "myPet": "dog",
  "myFavPets": ["dog", "cat"],
  "myDog": {
    "name": "Yoko",
    "age": 11,
    "favThings": ["Naps", "Cuddles", "Sticks"],
    "dislikes": [
      {
        "horses": true
      },
      {
        "lemons": true
      },
      {
        "cats": false
      }
    ]
  },
  "inlineMapping": {
    "dog": true, 
    "cat": false
  }
}
```
<br/>

## Language Independent Scalar types

It is also possible to represent other scalar types such as `null` and `booleans`, which can be represented in many different ways.
Booleans are also _case-insensitive_ so we can use the same keyword in lowercase, propercase or uppercase and it doesn't make a difference.

```yaml
null:
  - ~
  - null

booleans:
  true:
    - [Y, y]
    - [Yes, YES, yes]
    - [True, TRUE, true]
    - [On, ON, on]
  false:
    - [N, n]
    - [No, NO, no]
    - [False, FALSE, false]
    - [Off, OFF, off]
```
