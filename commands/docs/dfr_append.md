---
title: dfr append
categories: |
  dataframe
version: 0.78.0
dataframe: |
  Appends a new dataframe.
usage: |
  Appends a new dataframe.
---

# <code>{{ $frontmatter.title }}</code> for dataframe

<div class='command-title'>{{ $frontmatter.dataframe }}</div>

## Signature

```> dfr append ```

## Examples

Appends a dataframe as new columns
```shell
> let a = ([[a b]; [1 2] [3 4]] | dfr into-df);
    $a | dfr append $a
╭───┬───┬───┬─────┬─────╮
│ # │ a │ b │ a_x │ b_x │
├───┼───┼───┼─────┼─────┤
│ 0 │ 1 │ 2 │   1 │   2 │
│ 1 │ 3 │ 4 │   3 │   4 │
╰───┴───┴───┴─────┴─────╯

```

Appends a dataframe merging at the end of columns
```shell
> let a = ([[a b]; [1 2] [3 4]] | dfr into-df);
    $a | dfr append $a --col
╭───┬───┬───╮
│ # │ a │ b │
├───┼───┼───┤
│ 0 │ 1 │ 2 │
│ 1 │ 3 │ 4 │
│ 2 │ 1 │ 2 │
│ 3 │ 3 │ 4 │
╰───┴───┴───╯

```
