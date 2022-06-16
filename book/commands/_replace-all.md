---
title: replace-all
version: 0.64.0
usage: |
  Replace all (sub)strings by a regex pattern
---

<script>
  import { usePageFrontmatter } from '@vuepress/client';
  export default { computed: { frontmatter() { return usePageFrontmatter().value; } } }
</script>

# <code>{{ frontmatter.title }}</code>

<div style='white-space: pre-wrap;'>{{ frontmatter.usage }}</div>

## Signature

```> replace-all --pattern --replace```

## Parameters

 -  `--pattern {string}`: Regex pattern to be matched
 -  `--replace {string}`: replacing string

## Examples

Replaces string
```shell
> [abac abac abac] | to-df | replace-all -p a -r A
```