# ps-list [![Build Status](https://travis-ci.org/sindresorhus/ps-list.svg?branch=master)](https://travis-ci.org/sindresorhus/ps-list)

> Get running processes

Works on macOS, Linux, and Windows.

Main difference from [sindresorhus/ps-list](https://www.npmjs.com/package/ps-list/v/6.3.0) is that on Windows, we are able to add a path for the fastlist.exe. If the path is missing, the package works as the original one from verision v6.3.0.

## Install

```
$ npm install ps-list
```

## Usage

```js
const psList = require("ps-list");

(async () => {
	console.log(await psList());
	//=> [{pid: 3213, name: 'node', cmd: 'node test.js', ppid: 1, uid: 501, cpu: 0.1, memory: 1.5}, …]
})();
```

> The `cmd`, `cpu`, `memory`, and `uid` properties are not supported on Windows.

## API

### psList([options])

Returns a `Promise<Array>` with the running processes.

#### options

Type: `Object`

##### all

Type: `boolean`<br>
Default: `true`

Include other users' processes as well as your own.

On Windows this has no effect and will always be the users' own processes.

##### path

Type: `string`<br>
Default: `undefined`

Path for the fastlist.exe (Windows).

If path is not set, it works as the original package [sindresorhus/ps-list](https://github.com/sindresorhus/ps-list).

## License

MIT © [Sindre Sorhus](https://sindresorhus.com)
