---
tags:
  - nodejs
  - stream
---
# Node.js stream

## Ways to generate readable stream
- from other Node.js APIs that support streams(zlib, fs, http request/response, etc)
- `Readable.from(string or Buffer | async function *)`
- using `readable.push`:
```js
const stream = require('node:stream');
const readable = new stream.Readable({ read() { } });

readable.push('First');
readable.push('Second');
readable.push(null); // null means end of stream
```

## Ways to read from stream
> [!warning]
> Don't mix them up. Stick to one way that suits your codebase

- `readable.on('data')` - read chunk one by one
- `readable.on('readable'` - could be several chunks at once(null if the stream is ended)
- `readable.pipe(writable)`
- `pipeline`(for several streams):
```js
const { pipeline } = require('node:stream/promises');
const fs = require('node:fs');
const zlib = require('node:zlib');

async function run() {
  const ac = new AbortController();
  const signal = ac.signal;

  setImmediate(() => ac.abort());
  await pipeline(
    fs.createReadStream('archive.tar'),
    zlib.createGzip(),
    fs.createWriteStream('archive.tar.gz'),
    { signal },
  );
}

run().catch(console.error); // AbortError
```
- `AsyncIterable`:
```js
for await (const chunk of readable) {
	console.log({ chunk });
}
```

## Advanced topics
- back-pressure(`writable.cork()`, `readable.pause()`)
- `stream` supports `AbortController` and `AbortSignal`
- `stream` supports `object-mode`. Configures with `readableObjectMode`, `writableObjectMode`.
## Code samples
https://github.com/HowProgrammingWorks/Streams/tree/master/JavaScript\
