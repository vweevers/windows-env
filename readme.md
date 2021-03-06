# windows-env

**Normalized environment variables for Windows XP and up.**

[![npm status](http://img.shields.io/npm/v/windows-env.svg?style=flat-square)](https://www.npmjs.org/package/windows-env) [![Build status](https://img.shields.io/appveyor/ci/vweevers/windows-env.svg?style=flat-square)](https://ci.appveyor.com/project/vweevers/windows-env) [![Dependency status](https://img.shields.io/david/vweevers/windows-env.svg?style=flat-square)](https://david-dm.org/vweevers/windows-env)

## example

```js
const env = require('windows-env')

console.log('32-bit Program Files: %s', env.PROGRAMFILES_X86)

// This is true even if you run it with 32-bit Node.js
if (env.X64) {
  console.log('64-bit Program Files: %s', env.PROGRAMFILES_X64)
}
```

## exports

All of `process.env` uppercased, and:

- `PROGRAMFILES_X86`: `C:\Program Files (x86)` on 64 bit Windows, else `C:\Program Files`
- `PROGRAMFILES_X64`: `C:\Program Files` on 64 bit Windows, else undefined
- `USERPROFILE`: `USERPROFILE` or `HOMEDRIVE` + `HOMEPATH`
- `LOCALAPPDATA`: this is usually `USERPROFILE\AppData\Local`, falls back to `USERPROFILE\Local Settings\Application Data` for Windows XP
- `X64`: true on 64 bit Windows, regardless of node's bitness

## install

With [npm](https://npmjs.org) do:

```
npm install windows-env
```

## license

[MIT](http://opensource.org/licenses/MIT) © Vincent Weevers
