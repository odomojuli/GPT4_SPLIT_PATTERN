# GPT4_SPLIT_PATTERN
Regex Patterns

```
GPT4_SPLIT_PATTERN = r"""'(?i:[sdmt]|ll|ve|re)|[^\r\n\p{L}\p{N}]?+\p{L}+|\p{N}{1,3}| ?[^\s\p{L}\p{N}]++[\r\n]*|\s*[\r\n]|\s+(?!\S)|\s+"""
```

Sub-patterns:
* `'(?i:[sdmt]|ll|ve|re)`
* `[^\r\n\p{L}\p{N}]?+\p{L}+`
* `\p{N}{1,3}`
* ` ?[^\s\p{L}\p{N}]++[\r\n]*`
* `\s*[\r\n]`
* `\s+(?!\S)`
* `\s+`

---

## Common English Contractions
```
'(?i:[sdmt]|ll|ve|re)
```
* 's
* 'd
* 'm
* 't
* 'll
* 've
* 're
  
---

## Formatting
```
[^\r\n\p{L}\p{N}]?+\p{L}+
```
* A character class negation: matches any single character that is NOT a carriage return (\r), newline (\n), any Unicode letter (\p{L}), or any Unicode number (\p{N}).
* Possessive quantifier (?+) matches zero or one character from negated set, without backtracking.
* (\p{L}+) matches one or more Unicode letters.

---

## Small numbers:
```
\p{N}{1,3}
```
* Matches any numeric script
* Matches previous token between 1 to 3 times, as many times as possible (greedy).

---

## Whitespace

```
 ?[^\s\p{L}\p{N}]++[\r\n]*
```
* Space followed by `?` quantifier, (zero or one instances of space)
* Negation `^` of set:
  * `\s` (whitespace characters)
  * `p{L} (any Unicode letter)
  * `p{N} (any Unicode number)
* `++`, one or more, no backracking
* `[\r\n]*`, matches zero or more carriage returns (`\r`) or newline (`\n`).

---

## Whitespace sub-cases

```
\s*[\r\n]
```
* Matches optional whitespace followed by a line break.

```
\s+(?!\S)
```
* Matches whitespace only if not followed by a non-whitespace character (trailing spaces).

```
\s+
```
* Matches one or more whitespace characters.
