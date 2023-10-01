---
tags:
  - nodejs
  - stream
  - issue
---
The `read` method is a way for the stream to fetch next piece of data. This method will be called when stream is ready to process new data.

According to [documentation](https://nodejs.org/api/stream.html#readable_readsize), all `Readable` stream implementations must provide `_read` method. Otherwise you will get `The _read() method is not implemented` error
