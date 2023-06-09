---
title: "Markdown Extension Examples"
create: 2023-03-25T05:54:10Z
update: 2022-02-24T05:54:10Z
labels: ["github","markdown"]
reactions: ["EYES/1"]
---

[api](api-examples.md)
This page demonstrates some of the built-in markdown extensions provided by VitePress.
## Focused

```js
export default {
  data () {
    return {
      msg: 'Focused!' // [!code focus]
    }
  }
}
```

## Syntax Highlighting

VitePress provides Syntax Highlighting powered by [Shiki](https://github.com/shikijs/shiki), with additional features like line-highlighting:

**Input**

````
```js{4}
export default {
  data () {
    return {
      msg: 'Highlighted!'
    }
  }
}
```
````

**Output**

```js{4}
export default {
  data () {
    return {
      msg: 'Highlighted!'
    }
  }
}
```

## Colored Diffs in Code Blocks

Adding the `// [!code --]` or `// [!code ++]` comments on a line will create a diff of that line, while keeping the colors of the codeblock.

**Input**

Note that only one space is required after `!code`, here are two to prevent processing.

````
```js
export default {
  data () {
    return {
      msg: 'Removed' // [!code  --]
      msg: 'Added' // [!code  ++]
    }
  }
}
```
````

**Output**

```js
export default {
  data () {
    return {
      msg: 'Removed' // [!code --]
      msg: 'Added' // [!code ++]
    }
  }
}
```

## Errors and Warnings in Code Blocks

Adding the `// [!code warning]` or `// [!code error]` comments on a line will color it accordingly.

**Input**

Note that only one space is required after `!code`, here are two to prevent processing.

````
```js
export default {
  data () {
    return {
      msg: 'Error', // [!code  error]
      msg: 'Warning' // [!code  warning]
    }
  }
}
```
````

**Output**

```js
export default {
  data() {
    return {
      msg: 'Error', // [!code error]
      msg: 'Warning' // [!code warning]
    }
  }
}
```

## Line Numbers

You can enable line numbers for each code blocks via config:

```js
export default {
  markdown: {
    lineNumbers: true
  }
}
```

<!-- Please see [`markdown` options](/reference/site-config#markdown) for more details. -->

You can add `:line-numbers` / `:no-line-numbers` mark in your fenced code blocks to override the value set in config.

**Input**

````md
```ts {1}
// line-numbers is disabled by default
const line2 = 'This is line 2'
const line3 = 'This is line 3'
```

```ts:line-numbers {1}
// line-numbers is enabled
const line2 = 'This is line 2'
const line3 = 'This is line 3'
```
````

**Output**

```ts {1}
// line-numbers is disabled by default
const line2 = 'This is line 2'
const line3 = 'This is line 3'
```

```ts:line-numbers {1}
// line-numbers is enabled
const line2 = 'This is line 2'
const line3 = 'This is line 3'
```

## Custom Containers

**Input**

```md
::: info
This is an info box.
:::

::: tip
This is a tip.
:::

::: warning
This is a warning.
:::

::: danger
This is a dangerous warning.
:::

::: details
This is a details block.
:::
```

**Output**

::: info
This is an info box.
:::

::: tip
This is a tip.
:::

::: warning
This is a warning.
:::

::: danger
This is a dangerous warning.
:::

::: details
This is a details block.
:::

## Images

![example](https://ts1.cn.mm.bing.net/th/id/R-C.909139736b8bee17b50707506f7f803c?rik=PPGA9Jzj8BtLiQ&riu=http%3a%2f%2fuploadfile.bizhizu.cn%2f2015%2f1221%2f20151221022310156.jpg&ehk=jYE8M%2fmDiA4z%2bHbJs1crsA5i%2f7L577w2ZcPor%2bs0AqI%3d&risl=&pid=ImgRaw&r=0)

## More

Check out the documentation for the [full list of markdown extensions](https://vitepress.dev/guide/markdown).
