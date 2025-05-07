# bun-plugin-zon

A Bun plugin for loading ZON (Zig Object Notation) files in your Bun projects. This plugin allows you to seamlessly import and use ZON files as if they were regular JavaScript/TypeScript modules.

## Features

- 🔌 Seamless integration with Bun
- 📦 Import ZON files directly in your code
- 🚀 Zero configuration required
- ⚡️ Fast and efficient parsing

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

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

MIT