# CLI Usages

Poi CLI is built into the main package `poi`. While you can install it globally and run it, it is much better to install it locally into your project as a dev dependency.

```bash
yarn add poi --dev
```

You should also add some npm scripts to your `package.json` to run it easier.

```json
{
  "name": "my-project",
  "scripts": {
    "build": "poi --prod",
    "dev": "poi --serve"
  },
  "devDependencies": {
    "poi": "^12.0.0"
  }
}
```

Now you can run `yarn build` to create a production build and `yarn dev` to start a dev server for your project.

## Modes

By default Poi bundles your app in `development` mode, so running `poi` alone doesn't really do much but generates an unminified bundle.

But you can combine it with `--serve` flag which starts a dev server to serve the development bundle with hot reloading support.

There's also `--prod, --production` flags which set the mode to `production` so that Poi will generate an optimized bundle for production use. And `--test` flag which sets the mode to `test`, for convenience we also set the mode to `test` for `test` and `test:*` commands, for example the [Karma](./plugin-karma.md) plugin injected the `poi test:unit` command that you can use to run unit tests.

## CLI Args & Flags

Here's a list of major CLI flags.

To get the extra CLI flags for each of following flags, append `--help` flag. You can also go to the [config](../config.md) page to check out available CLI flags for config options.

### `poi [...entries]`

Bundle the entry files in development mode, so you will an unminified bundle __with__ sourcemaps.

### `--prod, --production`

Bundle the entry files in production mode, so you will a minified bundle __without__ sourcemaps.

Alias for `--mode production`.

### `--watch`

Bundle entry files and watch file changes.

### `--serve`

Serve entry files with a dev server, with hot reloading support.

### `--test`

Bundle entry files in test mode. In general you need to combine this flag with a plugin like [Karma](./plugin-karma.md) to run tests.

Alias for `--mode test`.

### `--debug`

Show debug logs.

### `--inspect-webpack`

Open the internal webpack config in your default editor.
