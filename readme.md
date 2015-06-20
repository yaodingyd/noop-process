# noop-process [![Build Status](https://travis-ci.org/sindresorhus/noop-process.svg?branch=master)](https://travis-ci.org/sindresorhus/noop-process)

> Create a noop process and get the PID

Useful for testing purposes.


## Install

```
$ npm install --save noop-process
```


## Usage

```js
var noopProcess = require('noop-process');

noopProcess(function (err, pid) {
	console.log(pid);
	//=> 1337
});
```


## API

### noopProcess([options], [callback])

Creates a [noop](https://en.wikipedia.org/wiki/NOP) process.

#### options

##### title

Type: `string`

Give the process a [title](https://nodejs.org/api/process.html#process_process_title) to make it easier to see in `ps` or kill it with `killall`.

Maximum 15 characters as anything longer will be truncated by the system.

##### persistent

Type: `boolean`  
Default: `false`

Let the process continue to live after the main process exits.

#### callback(error, pid)

##### pid

Type: `number`

Process ID of the created process.

### noopProcess.cleanup()

All the processes are cleaned up when the main process exits, but you can use this if you need them cleaned up earlier.


## License

MIT © [Sindre Sorhus](http://sindresorhus.com)
