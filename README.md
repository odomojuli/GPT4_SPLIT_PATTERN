# GPT4_SPLIT_PATTERN
Regex Patterns

```
GPT4_SPLIT_PATTERN = r"""'(?i:[sdmt]|ll|ve|re)|[^\r\n\p{L}\p{N}]?+\p{L}+|\p{N}{1,3}| ?[^\s\p{L}\p{N}]++[\r\n]*|\s*[\r\n]|\s+(?!\S)|\s+"""
```
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
