- [GET](#get)
- [POST](#post)
- [POST form](#post-form)

# GET

```js
const { body } = await request('http://localhost:1380/get', {
  headers: { 'User-Agent': 'undici' },
  query: { foo: 'bar' },
});

console.log('data', await body.json());
```

# POST

```js
const { body } = await request('http://localhost:1380/post', {
  method: 'POST',
  headers: {
    'content-type': 'application/json',
  },
  body: JSON.stringify({ foo: 'bar' }),
});

console.log('data', await body.json());
```

# POST form

```js
import { URLSearchParams } from 'url';

const formData = new URLSearchParams();

formData.append('foo', 'bar');

const { body } = await request('http://localhost:1380/post', {
  method: 'POST',
  headers: { 'Content-Type': 'application/x-www-form-urlencoded' },
  body: formData.toString(),
});

console.log('data', await body.json());
```
