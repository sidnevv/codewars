Task:

You need to return a string that looks like a diamond shape when printed on the screen, using asterisk (```*```) characters. Trailing spaces should be removed, and every line must be terminated with a newline character (```\n```).

Return ```null/nil/None/...``` if the input is an even number or negative, as it is not possible to print a diamond of even or negative size.

Examples:

A size 3 diamond:

```
 *
***
 *
```
...which would appear as a string of ```" *\n***\n *\n"```

A size 5 diamond:

```
  *
 ***
*****
 ***
  *
```
...that is:

```"  *\n ***\n*****\n ***\n  *\n"```

Solution:

```js
const diamond = (n) => {
  if (n < 0 || n % 2 === 0) return null
  let middle = Math.floor(n / 2)
  return Array.apply(null, {length: n}).map((item, index) => {
    const space = Math.abs(index - middle)
    const asterisks = n - space * 2
    return Array(space + 1).join(' ') + Array(asterisks + 1).join('*')
  }).join('\n') + '\n'
}
```
