# @bluwy/usb

Utilities for building userscripts.

## Usage

It's recommended to setup your own build script, for example:

```ts
import { build, getUserscriptManagerOutDir } from '@bluwy/usb'

await build({
  input: 'src/index.ts',
  outDir: 'dist',
  // Optional: copy the built userscript to the userscript manager's directory
  copyOutDir: [getUserscriptManagerOutDir('Userscripts')],
  // Optional: enable watch mode by passing "dev" as a positional argument
  watch: process.argv[2] === 'dev',
  // Custom userscript metadata, you may want to configure `namespace`, `match`,
  // `icon`, `grant`, etc.
  userscriptMeta: {
    grant: 'none',
  },
})
```

package.json:

```json
{
  "scripts": {
    "dev": "node scripts/build.js dev",
    "build": "node scripts/build.js build"
  }
}
```

Then run `npm run build` to build the userscript, or `npm run dev` to enable watch mode.

## Sponsors

<p align="center">
  <a href="https://bjornlu.com/sponsors">
    <img src="https://bjornlu.com/sponsors.svg" alt="Sponsors" />
  </a>
</p>

## License

MIT
