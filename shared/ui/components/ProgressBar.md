# ProgressBar

A reusable progress bar component with optional star display.

## Props

| Prop | Type | Default | Description |
|---|---|---|---|
| `percent` | `number` | required | Progress percentage (0–100) |
| `stars` | `number` | `0` | Number of filled stars to show (0–3) |
| `className` | `string` | `''` | Additional classes for the outer wrapper |
| `height` | `string` | `'h-9'` | Tailwind height class for the track |
| `rounded` | `string` | `'rounded-2xl'` | Tailwind border-radius class for track & fill |

## Usage

```tsx
import ProgressBar from '@/shared/ui/components/ProgressBar';

// Basic
<ProgressBar percent={75} />

// With stars
<ProgressBar percent={50} stars={2} />

// Kana variant (smaller bar)
<ProgressBar percent={100} stars={3} height='h-7' rounded='rounded-[1rem]' />

// With custom wrapper classes
<ProgressBar
  percent={30}
  stars={1}
  className='mb-4 max-md:mx-4 max-md:w-[calc(100%-2rem)]'
/>
```

## Rendering

- **Track**: a rounded container using `bg-(--background-color)` CSS variable
- **Fill**: a `div` inside the track with width set to `percent`% and a linear gradient `var(--secondary-color)` → `var(--main-color)`
- **Stars**: when `stars > 0`, renders a row of 3 `Star` icons (lucide-react). Earned stars use `fill-(--main-color) text-(--main-color)`. Unearned stars use `fill-current text-(--border-color)` (filled with the border color). The stars row only appears when `stars > 0`.

## Variation Table

| Usage | height | rounded | className (extra) |
|---|---|---|---|
| LevelSetCards (Kanji/Vocab) | `h-9` (default) | `rounded-2xl` (default) | `mb-4 max-md:mx-4 max-md:w-[calc(100%-2rem)]` |
| SubsetNew (Kana) | `h-7` | `rounded-[1rem]` | (none) |
