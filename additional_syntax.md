# Additional Syntax

## Multi-document YAML files

It is possible to define many different YAML docs in the same file by using the triple-dash separator `---`.

```yaml
title: This is the first document
first: true
---
title: This is the second document
docNumber: 2
```
<br/>

## Comments

We can comment content of the document by adding a `#` at any point. Everything after the # will be ignored as a comment.

```yaml
# This is a comment
foodType: "lunch" # This is also a comment!
```
<br/>

## Block strings

When we need to write long text inside a string, we can use the fold `>` and block `|` characters to determine which characters are included in a multiline string.

* __Fold character `>`:__ It will define a multiline string where the new line characters are ignored.
* __Literal character `|`:__ It will define a multiline string where new line characters are included for every separate line of text.

```yaml
fold: >
  This text will
  be all in one line

literal: |
  This text will
  be in two lines!
```
<br/>

## Chomp operators

Is is possible to modify the behaviour of the `fold` and `literal` characters by using the `chomp` operators:

* __Strip operator `-`:__ Strips new lines where added automatically.
* __Preserve operator `+`:__ Preserves new lines added automatically.

```yaml
preserve: >+
  This text will
  be in two lines now

strip: |-
  This text will now
  be in a single line
```
