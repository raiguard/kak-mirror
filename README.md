# kak-mirror

A [kakoune](http://kakoune.org) plugin to grow / shrink selections in both directions or surround them.

A fork of [kakoune-mirror by Delapouite](https://github.com/Delapouite/kakoune-mirror) with several
compatibility fixes.

## Installation

Source `mirror.kak` in your `kakrc`, or use a plugin manager.

## Usage

This plugin provides a `mirror` user-mode. Recommended usage is to bind this user mode to `'` in normal mode:
```
map global normal "'" ': enter-user-mode -lock mirror<ret>'
```

### Grow / shrink

If you type `l` it grows the selections one char to their right, but also one char to their left.
To shrink it one char, use `h`.
When the cursor is before the anchor, it does the opposite.

**Example**: the current selection is the middle `l`. Typing `'llhh` would produce these visual steps:
```
he[l]lo
h[ell]o
[hello]
h[ell]o
he[l]lo
```

You can also use `w` to grow one word to the right and it automatically do a `b` on the left.

It works vertically with `j` and `k`. Or `J` and `K` for full lines.
Hitting `c` will expand by columns above and below.

Finally you can also do it for paragraphs or sentences with `p` and `s`.

### Surround

Pairwise characters like braces, brackets or quotes can be added, replaced or removed.

**Example**: starting from the world `hello` selected.

First, let's surround it with double quotes and parentheses `'"(`

```
[hello]
["hello"]
[("hello")]
```

Oops, you meant to surround the double quotes with spaced-braces! Press `d` to remove the parens, then `}`

```
["hello"]
[{ "hello" }]
```

## See Also

- [kakoune-expand](https://github.com/occivink/kakoune-expand)
- [kakoune-text-objects](https://github.com/Delapouite/kakoune-text-objects)
- [kakoune-surround](https://github.com/h-youhei/kakoune-surround)
- [move-line.kak](https://github.com/alexherbo2/move-line.kak)
- [auto-pairs.kak](https://github.com/alexherbo2/auto-pairs.kak)
- [surround.kak](https://github.com/alexherbo2/surround.kak)

## Contributing

Please send questions, requests, bug reports, and patches to the
[mailing list](https://lists.sr.ht/~raiguard/public-inbox).
