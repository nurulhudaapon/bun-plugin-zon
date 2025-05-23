# bun-plugin-zon

A Bun plugin for loading ZON (Zig Object Notation) files in your Bun projects. This plugin allows you to seamlessly import and use ZON files as if they were regular JavaScript/TypeScript modules.

## Use Case
I had a Zig project where I had large ZON files, and another Bun project where I needed the same files, so this plugin was born to import ZON files in Bun.

## Installation

```bash
bun install bun-plugin-zon
```

## Usage

1. Add the plugin to your `bunfig.toml`:

```toml
preload = ["bun-plugin-zon"]
```

2. Import and use ZON files in your code:

```ts
// Import a ZON file
import data from './data.zon';

// Use the imported data
console.log(data);
```

## Example

Here's a complete example of how to use the plugin:

1. Create a `data.zon` file:
```zon
{
    name = "example",
    version = "1.0.0",
    dependencies = {
        "bun" = "latest"
    }
}
```

2. Import and use it in your code:
```ts
import config from './data.zon';

console.log(config.name); // "example"
console.log(config.version); // "1.0.0"
```



3. Fixing type errors

If you're using TypeScript, you may get an error like this:

```
// TypeScript error
// Cannot find module './data.zon' or its corresponding type declarations.
This can be fixed by creating *.d.ts file anywhere in your project (any name will work) with the following contents:
```

```ts
declare module '*.zon' {
  const content: string | number | boolean | null | JSON[] | { [key: string]: JSON };
  export default content;
}
```
This tells TypeScript that any default imports from .zon should be treated as all possible JSON values.


## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

MIT