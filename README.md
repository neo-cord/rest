<img alt="banner" src="https://repository-images.githubusercontent.com/291619880/8b583d80-eb6d-11ea-8300-3206ef4d5136" />

---

> Simple REST library used within [neocord](https://npmjs.com/neo-cord/neocord)

- [Discord Server](https://discord.gg/5WD9KhF)
- [GitHub Repository](https://github.com/neo-cord/rest)

**node.js v14** or newer is required.

```shell script
yarn add @neocord/rest
```

## Basic Usage

```ts
import { REST } from "@neocord/rest";
import fetch from "petitio";

const api = new REST();

// You must set the token if you want to use the RestHandler, cdn doesn't require a authorization.
api.token = "your token here"

// All (iirc) REST routes return JSON, the CDN does not.
api.queue("/users/@me").then(console.log);
...

// If you wanna use the CDN you need to use petitio, or another http client of your choice.
const defaultAvatar = await fetch(api.cdn.defaultAvatar("5773"));
console.log(defaultAvatar.body) // => <Buffer 89 50 4e 47...>
```

#### Typescript Users

Because we make use of [petitio](https://npmjs.com/petitio) you may have to install [undici](https://npmjs.com/undici) as a development dependency.

---

<p align="center">Licensed under the <strong>Apache 2.0</strong> License</p>
