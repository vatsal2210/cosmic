# 🌌 Cosmic

Find and load configuration for your app, based on [cosmiconfig](https://github.com/davidtheclark/cosmiconfig#explorersearch), with fallback to environment variables.

## ⭐ Features

Cosmic, like [cosmiconfig](https://github.com/davidtheclark/cosmiconfig#explorersearch), will look for a configuration file:

- a `package.json` property
- a JSON or YAML, extensionless "rc file"
- an "rc file" with the extensions .json, .yaml, .yml, or .js.
- a .config.js CommonJS module

For example, if the app name is "cosmic", these files will be searched:

- a cosmic property in `package.json`
- a `.cosmicrc` file in JSON or YAML format
- a `.cosmicrc.json` file
- a `.cosmicrc.yaml`, `.cosmicrc.yml`, or `.cosmicrc.js` file
- a `cosmic.config.js` file exporting a JS object

Apart from these, it also looks for:

- a `cosmic.yaml`, `cosmic.yml`, or `cosmic.js` file without "rc"
- Environment variables

## 💡 Usage

Install the package from [npm](https://www.npmjs.com/package/@vatsal2210/cosmic):

```bash
npm install @vatsal2210/cosmic
```

Import and use:

```ts
import { cosmic } from '@vatsal2210/cosmic';

const config = await cosmic('project'); // {}
```

Use the `config` function to fetch a value:

```ts
import { cosmic, config } from '@vatsal2210/cosmic';

await cosmic('project');
const environment = config('nodeEnv');
```

Clear the cache and fetch configuration available:

```ts
import { clearCosmicCache } from '@vatsal2210/cosmic';

clearCosmicCache();
```

Sync functions are also available:

```ts
import { cosmicSync } from '@vatsal2210/cosmic';

const config = cosmicSync('project'); // {}
```

## 👩‍💻 Development

Build TypeScript:

```bash
npm run build
```

Run unit tests and view coverage:

```bash
npm run test-without-reporting
```
