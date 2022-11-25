# pinst [![Node.js CI](https://github.com/typicode/pinst/workflows/Node.js%20CI/badge.svg)](https://github.com/typicode/pinst/actions) [![npm](https://img.shields.io/npm/v/pinst.svg)](https://www.npmjs.com/package/pinst)

> `pinst` lets you have the `preinstall` and `postinstall` hooks running only in dev 🍺

__Important__ if your project is using npm or pnpm, you can achieve the desired effect by setting a `prepare` hook instead. `pinst` is mainly useful for Yarn 2+ since it doesn't support `prepare` hook. See https://yarnpkg.com/advanced/lifecycle-scripts

## Usage

```js
// package.json
{
  "scripts": {
    "preinstall": "<some dev only command>",
    "postinstall": "<some dev only command>",
    "prepack": "pinst --disable",
    "postpack": "pinst --enable"
  }
}
```

_On `prepack`, `preinstall` and `postinstall` will be renamed to `_preinstall` and `_postinstall` (disabled)_

_On `postpack`, it will be renamed back to `preinstall` and `postinstall` (enabled)_

## CLI

`pinst` accepts the following flags:

```
--enable, -e   Enable preinstall & postinstall hook
--disable, -d  Disable preinstall & postinstall hook
--silent, -s
```

## Tips

By inverting commands, you can also use `pinst` to enable `preinstall` or `postinstall` for your users only and not yourself.

`pinst` also supports `install` alias.

## License

MIT - [Typicode :cactus:](https://github.com/typicode)
