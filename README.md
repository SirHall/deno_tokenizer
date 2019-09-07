# Tokenizer
[![Actions Status](https://github.com/eliassjogreen/deno_tokenizer/workflows/Tests/badge.svg)](https://github.com/eliassjogreen/deno_tokenizer/actions)
[![GitHub license](https://img.shields.io/github/license/eliassjogreen/deno_tokenizer)](https://github.com/eliassjogreen/deno_tokenizer)

A simple tokenizer for deno.

## Example
```TypeScript
import { Tokenizer } from "./mod.ts";

const tokenizer = new Tokenizer("abc 123 HELLO", [
    { name: "HELLO",  pattern: "HELLO" },
    { name: "WORD",   pattern: /[a-zA-Z]+/ },
    { name: "DIGITS", pattern: /\d+/ },
    { name: "SPACE",  pattern: / /, ignore: true }, // Or leave name blank and remove "ignore: true"
]);

// Either the following:
console.log([...tokenizer]);
// Or the following while loop:
// while (!tokenizer.done) {
//     console.log(tokenizer.next().value);
// }

// => { name: "HELLO", value: "HELLO" }
// => { name: "WORD", value: "abc" }
// => { name: "DIGITS", value: "123" }
```
