---
title: url decode
categories: |
  strings
version: 0.87.0
strings: |
  Converts a percent-encoded web safe string to a string.
usage: |
  Converts a percent-encoded web safe string to a string.
---
<!-- This file is automatically generated. Please edit the command in https://github.com/nushell/nushell instead. -->

# <code>{{ $frontmatter.title }}</code> for strings

<div class='command-title'>{{ $frontmatter.strings }}</div>

## Signature

```> url decode {flags} ...rest```

## Parameters

 -  `...rest`: For a data structure input, url decode strings at the given cell paths


## Input/output types:

| input        | output       |
| ------------ | ------------ |
| list\<string\> | list\<string\> |
| record       | record       |
| string       | string       |
| table        | table        |
## Examples

Decode a url with escape characters
```nu
> 'https://example.com/foo%20bar' | url decode
https://example.com/foo bar
```

Decode multiple urls with escape characters in list
```nu
> ['https://example.com/foo%20bar' 'https://example.com/a%3Eb' '%E4%B8%AD%E6%96%87%E5%AD%97/eng/12%2034'] | url decode
╭───┬─────────────────────────────╮
│ 0 │ https://example.com/foo bar │
│ 1 │ https://example.com/a>b     │
│ 2 │ 中文字/eng/12 34            │
╰───┴─────────────────────────────╯

```