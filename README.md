# @tweakit - shadcn/ui Registry

A collection of beautiful, ready-to-use components for your shadcn/ui projects.

## Installation

### 1. Add the registry to your project

```bash
npx shadcn@latest registry add @tweakit=https://raw.githubusercontent.com/aliy321/tweakit/main/{name}.json
```

Or manually add to your `components.json`:

```json
{
  "registries": {
    "@tweakit": "https://raw.githubusercontent.com/aliy321/tweakit/main/{name}.json"
  }
}
```

### 2. Install components

```bash
npx shadcn@latest add @tweakit/color-scheme-switcher
```

## Components

### Color Scheme Switcher

A theme switcher component with **42 built-in themes**, dark/light mode toggle, search functionality, and custom CSS support.

```bash
npx shadcn@latest add @tweakit/color-scheme-switcher
```

**Features:**
- 42 pre-configured themes (Violet Bloom, Catppuccin, Cyberpunk, Vercel, etc.)
- Dark/light mode toggle
- Search and filter themes
- Custom CSS input for your own themes
- Clear selected theme button
- Zero configuration required

**Usage:**

```tsx
import { ColorSchemeSwitcher } from "@/components/color-scheme-switcher";

export default function Page() {
  return (
    <div>
      <ColorSchemeSwitcher />
      {/* Your app content */}
    </div>
  );
}
```

**Props:**

| Prop | Type | Default | Description |
|------|------|---------|-------------|
| `defaultScheme` | `string` | `undefined` | Initial theme ID (e.g., `"violet-bloom"`) |
| `defaultMode` | `"light" \| "dark"` | `"light"` | Initial color mode |
| `onSchemeChange` | `(scheme: ColorScheme \| null) => void` | - | Callback when theme changes |

**Example with callbacks:**

```tsx
<ColorSchemeSwitcher
  defaultScheme="catppuccin"
  defaultMode="dark"
  onSchemeChange={(scheme) => {
    if (scheme) {
      console.log(`Applied theme: ${scheme.name}`);
    } else {
      console.log("Theme cleared");
    }
  }}
/>
```

**Dependencies:**

Automatically installed:
- `lucide-react`
- `@shadcn/popover`
- `@shadcn/button`
- `@shadcn/scroll-area`

## Available Themes

| Theme | Description |
|-------|-------------|
| modern-minimal | Clean blue/white minimal |
| violet-bloom | Purple-accented with large radius |
| t3-chat | Purple/pink chat-style |
| twitter | Twitter/X-inspired blue |
| mocha-mousse | Warm brown/coffee tones |
| bubblegum | Pink/teal playful |
| amethyst-haze | Soft purple amethyst |
| notebook | Handwritten/architect style |
| doom-64 | Retro gaming, zero radius |
| catppuccin | Catppuccin latte/mocha |
| graphite | Monochrome gray |
| perpetuity | Teal/cyan monospace |
| kodama-grove | Earthy green/nature |
| cosmic-night | Deep purple space |
| tangerine | Orange/coral accent |
| quantum-rose | Hot pink/magenta |
| nature | Green forest |
| bold-tech | Violet/indigo tech |
| elegant-luxury | Red/gold luxury |
| amber-minimal | Amber/yellow minimal |
| supabase | Supabase green branding |
| neo-brutalism | Bold primaries, zero radius |
| solar-dusk | Warm amber/sunset |
| claymorphism | Soft indigo, large corners |
| cyberpunk | Neon pink/cyan |
| pastel-dreams | Soft purple pastels |
| clean-slate | Indigo clean professional |
| caffeine | Warm coffee/cream |
| ocean-breeze | Green/ocean fresh |
| retro-arcade | Solarized-inspired retro |
| midnight-bloom | Purple/indigo night |
| candyland | Pink/blue playful |
| northern-lights | Green/blue aurora |
| vintage-paper | Sepia/brown vintage |
| sunset-horizon | Orange/coral sunset |
| starry-night | Deep blue/yellow |
| claude | Warm terracotta AI-inspired |
| vercel | Black/white Vercel branding |
| darkmatter | Dark with orange/teal |
| mono | Pure monochrome |
| soft-pop | Colorful pop with black borders |
| sage-garden | Sage green garden |

## Project Structure

```
tweakit/
├── color-scheme-switcher.json    # Registry item metadata + component content
├── color-scheme-switcher.tsx     # Source component file
└── registry.json                 # Registry index (for {name}.json format)
```

## Registry Format

This registry uses the **flat file format** (`{name}.json`). Each component is a self-contained JSON file that includes:

- Component metadata (name, type, description)
- File content (embedded as a string)
- Dependencies and registry dependencies
- Target path for installation

## License

MIT
