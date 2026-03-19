<p align="left">
    <img width="1280" height="192" alt="wordmark-color-transparent-1280x192" src="https://github.com/user-attachments/assets/d51c038f-7822-4ee4-beb8-f438894f7736" />
    <img width="1280" height="192" alt="wordmark-color-transparent-1280x192" src="https://github.com/user-attachments/assets/d51c038f-7822-4ee4-beb8-f438894f7736" />
</p>

# @declareui/tailwind-plugin

Tailwind CSS integration for DeclareUI — build-time class extraction, Shadow DOM support, and design tokens bridge.

---

## What it does

This plugin ensures Tailwind CSS works seamlessly with DeclareUI components:

- **Build-time extraction** — scans `.ui.yaml` files for Tailwind classes so they're included in your CSS bundle
- **Shadow DOM support** — injects styles into Shadow DOM for Web Components targets
- **Design tokens bridge** — maps Tailwind's theme config to DeclareUI's token system

## Installation

```bash
pnpm add -D @declareui/tailwind-plugin
```

## Setup

```javascript
// tailwind.config.js
import declareui from '@declareui/tailwind-plugin';

export default {
  plugins: [
    declareui({
      components: './src/components/**/*.ui.yaml',
    }),
  ],
};
```

## Features

### Class extraction

The plugin automatically scans your `.ui.yaml` component files and registers all Tailwind classes with the JIT compiler — no manual safelist needed.

### Shadow DOM

When targeting Web Components, the plugin generates `<style>` tags with only the used Tailwind utilities, embedded directly into each component's Shadow DOM.

### Design tokens

Map Tailwind theme values to DeclareUI tokens:

```yaml
# button.ui.yaml
template:
  tag: button
  classes:
    base: "px-4 py-2 rounded-lg"
    variants:
      variant:
        primary: "bg-primary text-primary-foreground"
```

## Related packages

| Package | Description |
|:--------|:------------|
| [`@declareui/core`](https://github.com/declare-ui/core) | Parser, AST, and code generators |
| [`@declareui/components`](https://github.com/declare-ui/components) | Pre-built component library |
| [`@declareui/cli`](https://github.com/declare-ui/cli) | CLI tool |

## Contributing

See [CONTRIBUTING.md](https://github.com/declare-ui/.github/blob/main/CONTRIBUTING.md) for guidelines.

## License

MIT
