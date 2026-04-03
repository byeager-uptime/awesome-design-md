# Design System: Envelopd (Pocket Stack)

## 1. Visual Theme & Atmosphere

Envelopd is a personal finance app built around the envelope budgeting method -- each spending category is a "pocket" with its own card and balance. The design system, called Pocket Stack, creates a warm, tactile experience that makes managing money feel approachable rather than clinical. The page opens on a creamy off-white canvas (`#F7F3EF`) with deep warm-brown headings (`#2B1D15`) and a vibrant orange accent (`#F0920D`) that functions as the primary call-to-action and interactive anchor. This isn't the cold blue of traditional banking software; it's a rich, saturated warm orange that reads as energetic and inviting.

The typography pairing is the defining element of Pocket Stack's character. `Instrument Serif` serves as the display font -- used for hero headlines and prominent titles -- lending a personal, editorial quality that says "this is your money story." `DM Sans` handles body text with a warm, geometric friendliness, falling back to `Inter` for system compatibility. At the hero size (2.5rem / 40px), Instrument Serif runs with tight tracking (-0.02em), creating dense, confident headlines. For financial amounts, `DM Sans` at 1.5rem with bold weight (700) and `tabular-nums` ensures numbers align cleanly in the card stack.

What truly distinguishes Pocket Stack is its card-first architecture and warm shadow system. Every piece of content lives inside a rounded card (`rounded-2xl` / 16px radius), and elevation is communicated through layered, warm-tinted shadows using a brown shadow color (`hsl(30, 20%, 50%)`) instead of neutral gray. Cards lift on hover with a subtle -2px translate and shadow intensification, creating a tactile "pick up and look" interaction that reinforces the physical metaphor of stacked envelopes. The status system uses semantic colors -- green for active, blue for frozen, amber for needs-money -- applied at 15% opacity backgrounds with full-saturation text, ensuring status is communicated through color meaning rather than decoration.

**Key Characteristics:**
- Instrument Serif for display type -- editorial, personal, serif warmth
- DM Sans as the primary body font -- geometric, friendly, highly readable
- Warm earth-tone palette: hue range 16-38 degrees, saturation 20-45%, lightness 14-97%
- Vibrant orange accent (`#F0920D`) as the sole interactive color -- energetic, approachable
- Card-first architecture: everything is a `rounded-2xl` card with warm-tinted shadows
- Warm brown shadows using `hsl(30, 20%, 50%)` -- elevation that feels cozy, not corporate
- Mobile-first responsive design starting at 375px (`xs` breakpoint)
- Semantic status colors: green (active), blue (frozen), amber (needs money), gray (no card)
- `tabular-nums` and `tracking-tight` on all financial data for clean number alignment
- Gradient CTAs: orange-to-brown (`from-pocket-accent to-pocket-warm-500`) for primary actions

## 2. Color Palette & Roles

### Primary
- **Warm Off-White** (`#F7F3EF`): `--pocket-warm-50`. Primary page background. Not pure white -- a warm, creamy base that sets the earth-tone atmosphere.
- **Deep Warm Brown** (`#2B1D15`): `--pocket-card-foreground`. Primary text color for card content and headings. Warm, readable, never harsh.
- **Vibrant Orange** (`#F0920D`): `--pocket-accent`. Primary interactive color. CTA buttons, active nav, links, progress indicators.

### Card & Surface
- **Card White** (`#FEFBF8`): `--pocket-card`. Card background. Barely-tinted warm white for elevated surfaces.
- **Surface Warm** (`#F5F0EB`): `--pocket-surface`. Nested surface inside cards, secondary containers.
- **Light Beige** (`#EFEAE4`): `--pocket-warm-100`. Card footer borders, subtle dividers within cards.
- **Sand** (`#DDD2C7`): `--pocket-warm-200`. Default card borders, input borders, inactive elements.
- **Warm Tan** (`#C7B3A3`): `--pocket-warm-300`. Pull handle indicators, placeholder icons, tertiary text.

### Accent & Interactive
- **Vibrant Orange** (`#F0920D`): `--pocket-accent`. Primary CTA, active state, step progress bars.
- **Dark Brown** (`#1B0E06`): `--pocket-accent-foreground`. Text on accent backgrounds for maximum contrast.
- **Orange Hover** (`#E68A0C`): `--pocket-accent` at 90% opacity. Hover state for gradient buttons.

### Neutral Scale (Warm Browns)
- **Medium Brown** (`#9D7B63`): `--pocket-warm-400`. Inactive nav icons, tertiary labels, chevrons.
- **Dark Warm** (`#6F5344`): `--pocket-warm-500`. Secondary body text, descriptions, metadata captions.
- **Deep Warm** (`#583C27`): `--pocket-warm-600`. Form labels, strong secondary text.
- **Darker** (`#442A1A`): `--pocket-warm-700`. Emphasis text when needed.
- **Near Black** (`#2D1A0F`): `--pocket-warm-800`. Strongest text, rarely used directly.
- **Deepest** (`#1B0E06`): `--pocket-warm-900`. Maximum contrast text, accent-on-dark text.

### Status Colors
- **Active Green** (`#2DA66E`): `--pocket-status-active`. Healthy envelope, active card, success states. Badge bg at 15% opacity.
- **Frozen Blue** (`#4FA8FF`): `--pocket-status-frozen`. Frozen card, paused state. Gradient tint on frozen cards at 5% opacity.
- **Needs Money Amber** (`#F59E0B`): `--pocket-status-needs-money`. Low balance warning. Badge bg at 15%, border at 40%.
- **No Card Gray** (`#727B8C`): `--pocket-status-no-card`. Missing card, disabled state. Card opacity reduced to 90%.

### Semantic
- **Success** (`#10B981`): `--success`. Confirmation states, positive balance changes.
- **Warning** (`#F59E0B`): `--warning`. Caution states, approaching limits.
- **Danger** (`#EF4444`): `--danger`. Destructive actions, negative balances, errors.
- **Destructive Red** (`#DC2626`): Negative amounts in AmountDisplay, error icons.

### Shadow Colors
- **Warm Shadow** (`hsl(30, 20%, 50%)`): `--pocket-shadow-color`. The signature -- warm brown-tinted shadows for all elevation levels.
- **Dark Mode Shadow** (`hsl(0, 0%, 0%)`): Pure black shadow for dark mode, preserving depth without warmth artifacts on dark surfaces.

### Dark Mode Overrides
- Card background inverts to `hsl(25, 12%, 10%)` (`--pocket-card`)
- Warm scale inverts: light values become dark surfaces, dark values become light text
- Accent stays vibrant: `hsl(27, 90%, 55%)` (`--pocket-accent`) -- slightly desaturated for dark surface contrast
- Status colors desaturate slightly: active to `hsl(152, 55%, 38%)`, frozen to `hsl(210, 60%, 50%)`
- Borders use `--pocket-dark-border` at `hsl(40, 34%, 28%)` for visible separation on dark surfaces

## 3. Typography Rules

### Font Family
- **Display**: `Instrument Serif`, with fallback: `Georgia`, `serif`
- **Body**: `DM Sans`, with fallback: `Inter`, `system-ui`, `sans-serif`
- **System**: `Inter`, with fallback: `system-ui`, `sans-serif`
- **Financial Numbers**: Body font with `tabular-nums` and `tracking-tight` for aligned currency display

### Hierarchy

| Role | Font | Size | Weight | Line Height | Letter Spacing | Features | Notes |
|------|------|------|--------|-------------|----------------|----------|-------|
| Display Hero | Instrument Serif | 40px (2.50rem) | 400 | 1.1 (tight) | -0.02em | -- | Main screen titles, total balance display |
| Card Title | DM Sans | 18px (1.125rem) | 600 | 1.3 | normal | -- | Envelope name, card header title |
| Card Amount | DM Sans | 24px (1.50rem) | 700 | 1.2 | tight | tabular-nums | Envelope balance, transaction amount |
| Body Large | DM Sans | 18px (1.125rem) | 400 | 1.4 | normal | -- | Feature descriptions, dialog titles |
| Body | DM Sans | 16px (1.00rem) | 400 | 1.5 | normal | -- | Standard reading text, form content |
| Body Semibold | DM Sans | 16px (1.00rem) | 600 | 1.5 | normal | -- | Inline emphasis, selected states |
| Label | DM Sans | 14px (0.875rem) | 600 | 1.4 | normal | -- | Envelope name in list, CTA label text |
| Form Label | DM Sans | 14px (0.875rem) | 500 | 1.4 | normal | -- | Input labels, section sub-headers |
| Pocket Label | DM Sans | 13px (0.8125rem) | 500 | 1.4 | normal | -- | Metadata, balance label, source info |
| Caption | DM Sans | 12px (0.75rem) | 400 | 1.4 | normal | -- | Helper text, timestamps, secondary info |
| Status Badge | DM Sans | 12px (0.75rem) | 600 | 1.0 | normal | -- | Badge text: "Active", "Frozen", "Low" |
| Nav Label | DM Sans | 10px (0.625rem) | 500 | 1.0 | normal | -- | Bottom navigation labels |
| Amount Inline | DM Sans | 16px (1.00rem) | 600 | 1.5 | tight | tabular-nums | Inline currency in tables, summaries |
| Dialog Title | Instrument Serif | 18px (1.125rem) | 400 | 1.3 | normal | -- | Sheet and modal titles |

### Principles
- **Serif for story, sans for data**: Instrument Serif appears only at display/title level -- it sets the emotional tone. All data, labels, and interactive text use DM Sans for clarity and density.
- **Tabular numbers everywhere**: Any financial amount uses `tabular-nums` and `tracking-tight` to ensure dollar signs and digits align vertically in card stacks and lists.
- **Weight as hierarchy**: 400 for body, 500 for labels, 600 for card titles and emphasis, 700 exclusively for amounts. Weight increases correlate directly with financial importance.
- **Tight tracking at display size**: The hero font uses -0.02em letter-spacing to create dense, confident blocks. All other sizes use normal tracking.
- **Two-font simplicity**: Only two fonts in the entire system. No monospace, no third family. Instrument Serif for warmth, DM Sans for everything else.

## 4. Component Stylings

### Buttons

**Primary Gradient (CTA)**
- Background: `linear-gradient(to right, #F0920D, #6F5344)` (orange to warm brown)
- Text: `#ffffff`
- Height: 48px (h-12)
- Padding: implicit via full-width
- Radius: 16px (rounded-2xl)
- Font: 16px DM Sans weight 600
- Hover: opacity 90%
- Active: scale 95%
- Use: Primary action ("Continue", "Confirm Top Up", "Done")

**Primary Gradient (Pill)**
- Background: same gradient
- Text: `#ffffff`
- Radius: 9999px (rounded-full)
- Font: 14px DM Sans weight 600
- Use: Compact actions ("Done", "Try Again")

**Outlined**
- Background: transparent
- Text: `--pocket-card-foreground`
- Border: `1px solid --pocket-warm-200`
- Radius: 9999px (rounded-full)
- Font: 14px DM Sans weight 500
- Hover: background shifts to `--pocket-warm-50`
- Use: Secondary actions ("Close", "Cancel")

**Quick Amount**
- Background (default): `--pocket-card`
- Background (selected): `--pocket-accent` at 5% opacity
- Text (default): `--pocket-card-foreground`
- Text (selected): `--pocket-accent`
- Height: 56px (h-14)
- Border: 2px solid `--pocket-warm-150` (default), `--pocket-accent` (selected)
- Radius: 16px (rounded-2xl)
- Font: 18px DM Sans weight 600
- Active: scale 95%
- Use: Amount selection grid ($25, $50, $100, $200)

**Nav Circle (Top-Up)**
- Background: gradient from-pocket-accent to-pocket-warm-500
- Size: 48px x 48px (h-12 w-12)
- Radius: 9999px (circle)
- Offset: -16px top margin (-mt-4) to float above nav bar
- Use: Central navigation button

**Back Button**
- Background: transparent
- Size: 32px x 32px (h-8 w-8)
- Radius: 9999px (rounded-full)
- Text: `--pocket-warm-500`
- Hover: background `--pocket-warm-50`
- Use: Navigation back in multi-step flows

### Cards & Containers

**PocketCard (Primary)**
- Background: `--pocket-card` (`#FEFBF8`)
- Border: 1px solid `--pocket-warm-200`
- Radius: 16px (rounded-2xl)
- Shadow: `pocket` (0 2px 8px warm/0.1, 0 1px 3px warm/0.08)
- Padding: 16px (p-4)
- Text: `--pocket-card-foreground`
- Transition: all 200ms

**PocketCard (Pressable)**
- Inherits Primary
- Cursor: pointer
- Hover: shadow-pocket-md, translateY(-2px)
- Active: shadow-pocket-sm, translateY(0)
- Use: Tappable envelope cards, list items

**PocketCard Variants**
- `active`: border `--pocket-status-active` at 30% opacity
- `frozen`: gradient bg from card to frozen/5, border frozen/30
- `needs-money`: border `--pocket-status-needs-money` at 40%
- `no-card`: bg `--pocket-warm-50`, border warm-200, opacity 90%

**Card Footer Divider**
- Border-top: 1px solid `--pocket-warm-100`
- Margin-top: 12px (mt-3)
- Padding-top: 12px (pt-3)

**Dialog / Bottom Sheet**
- Background: `--pocket-card`
- Border: `--pocket-warm-100`
- Radius: 16px (rounded-2xl)
- Shadow: pocket-lg
- Max width: 92vw mobile, 448px (sm:max-w-md) desktop
- Max height: 85vh
- Pull handle: 4px x 40px rounded-full, `--pocket-warm-300`

### Badges / Status Pills

**StatusBadge**
- Shape: pill (rounded-full)
- Padding: 10px horizontal, 4px vertical (px-2.5 py-1)
- Font: 12px DM Sans weight 600
- Dot: 6px x 6px circle, full saturation status color
- Background: status color at 15% opacity
- Text: full saturation status color
- Dark mode: status color at 20% opacity background

**Low Balance Indicator**
- Background: `--pocket-status-needs-money` at 10% opacity
- Text: `--pocket-status-needs-money`
- Padding: 8px horizontal, 2px vertical (px-2 py-0.5)
- Font: 12px DM Sans weight 500
- Radius: 9999px (rounded-full)

### Inputs & Forms
- Height: 56px (h-14) for primary inputs
- Border: 2px solid `--pocket-warm-150`
- Radius: 16px (rounded-2xl)
- Focus: border color changes to `--pocket-accent`
- Label: `--pocket-warm-600`, 14px DM Sans weight 500
- Text: 18px DM Sans weight 600
- Placeholder: `--pocket-warm-400`
- Currency prefix: absolute positioned "$" in `--pocket-warm-400`, 18px weight 600

### Spendable Banner (CTA Card)
- Background: gradient `from-pocket-accent/10 via-pocket-warm-100/60 to-pocket-warm-50`
- Border: 1px solid `--pocket-accent` at 20% opacity
- Radius: 16px (rounded-2xl)
- Shadow: pocket-sm
- Padding: 16px (p-4)
- Icon container: 44px x 44px, rounded-xl, `--pocket-accent` at 15% bg
- Hover: shadow-pocket, translateY(-2px)
- Dark mode: gradient from-pocket-accent/15 via-pocket-warm-900/40 to-pocket-warm-900/20

### Navigation (Mobile Bottom)
- Position: fixed bottom, z-50
- Background: `--pocket-card` at 95% opacity
- Backdrop: blur-lg (frosted glass)
- Height: 64px + safe-area-inset-bottom
- Items: 5 (Home, Envelopes, Top-Up, Family, Settings)
- Icon size: 20px x 20px (h-5 w-5)
- Label: 10px DM Sans weight 500
- Active: `--pocket-accent` color
- Inactive: `--pocket-warm-400` color
- Top-Up button: elevated gradient circle, -16px offset above nav

### Step Progress Indicator
- Bars: 4 segments, 24px x 6px each (w-6 h-1.5)
- Shape: rounded-full
- Active: `--pocket-accent` (filled orange)
- Inactive: `--pocket-warm-200` (muted sand)
- Gap: 4px (gap-1)
- Transition: colors

## 5. Layout Principles

### Spacing System
- Base unit: 4px
- Scale: 2px (0.5), 4px (1), 6px (1.5), 8px (2), 10px (2.5), 12px (3), 16px (4), 20px (5), 24px (6)
- Notable: The 4px base creates a tight, mobile-optimized rhythm. Most internal card spacing uses 8-16px, while section gaps use 12px.

### Grid & Container
- Max content width: 512px (max-w-lg) on mobile, 672px (max-w-2xl) on tablet+
- Primary layout: single column, vertically stacked cards
- Card stacking: gap-3 (12px) between envelope cards
- Amount grid: 2 columns for quick-select buttons
- Container: centered with px-4 (16px) mobile, px-6 (24px) desktop

### Whitespace Philosophy
- **Card-first density**: Content is organized within cards, and whitespace exists primarily between cards (12px gaps) rather than within them (compact 16px padding). This creates a "stack of physical envelopes" visual metaphor.
- **Generous touch chrome**: Interactive elements (buttons at 48-56px, inputs at 56px) are generously sized for touch, but informational elements (labels at 13px, captions at 12px) are compact. Touch targets are large, data display is dense.
- **Section rhythm**: The envelope list uses consistent 12px card gaps with no section headers breaking the vertical flow -- the cards ARE the sections.

### Border Radius Scale
- Small (4px): Fine UI elements (progress dots, dividers)
- Standard (8px): Form labels, icon containers (rounded-lg)
- Comfortable (12px): Nested elements, icon backgrounds (rounded-xl)
- Primary (16px): Cards, buttons, inputs, modals, banners (rounded-2xl)
- Full (9999px): Pills, badges, circular buttons, nav icons (rounded-full)
- Note: `rounded-2xl` (16px) is the workhorse -- it appears on virtually every container. This large radius is intentional: it creates the soft, approachable feel that distinguishes Pocket Stack from sharp-cornered financial tools.

## 6. Depth & Elevation

| Level | Treatment | Use |
|-------|-----------|-----|
| Flat (Level 0) | No shadow | Page background, inline text, nested elements |
| Subtle (Level 1) | `0 1px 3px warm/0.08, 0 1px 2px warm/0.06` | Baseline card rest state, banner shadow |
| Standard (Level 2) | `0 2px 8px warm/0.1, 0 1px 3px warm/0.08` | Default PocketCard, resting interactive elements |
| Elevated (Level 3) | `0 4px 16px warm/0.12, 0 2px 6px warm/0.08` | Hovered cards, focused elements, popovers |
| Deep (Level 4) | `0 8px 24px warm/0.14, 0 4px 10px warm/0.1` | Modals, bottom sheets, top-level floating panels |

**Shadow Philosophy**: Pocket Stack's shadow system uses warm-tinted shadows (`hsl(30, 20%, 50%)`) at very low opacity (6-14%) to create depth that feels cozy rather than technical. Where Stripe uses blue-tinted shadows for corporate atmosphere, and Linear uses border-based elevation, Pocket Stack uses brown-tinted shadows that echo the warm palette. The dual-layer approach pairs a far shadow (higher blur, lower opacity) with a near shadow (tighter blur, even lower opacity) creating a naturalistic depth -- like sunlight casting soft shadows on stacked paper. The warm shadow color ensures elevated elements feel like they belong to the surface below them.

### Decorative Depth
- Gradient CTAs create a color-based depth: `from-pocket-accent to-pocket-warm-500` (bright orange fading to dark brown) implies directionality and energy
- Frosted glass navigation: `bg-pocket-card/95 backdrop-blur-lg` creates a translucent surface that layers over content without hard edges
- Status card variants use gradient backgrounds (frozen: `from-pocket-card to-pocket-status-frozen/5`) for subtle atmospheric tinting rather than border-only status indication

## 7. Do's and Don'ts

### Do
- Use Instrument Serif only for hero/display headlines and dialog titles -- it's the emotional anchor, not a workhorse
- Use DM Sans with weight 600-700 for financial amounts -- bold numbers communicate monetary confidence
- Apply warm-tinted shadows (`hsl(30, 20%, 50%)`) for all elevated elements
- Use `#2B1D15` (deep warm brown) for heading/body text instead of `#000000` -- warmth matters
- Keep border-radius at 16px (`rounded-2xl`) for all cards, buttons, and inputs -- generous rounding is the brand
- Use `tabular-nums` and `tracking-tight` for any financial number display
- Layer shadows: warm far + warm near for naturalistic depth
- Use the orange accent (`#F0920D`) as the primary interactive/CTA color
- Apply status colors at 15% opacity for backgrounds, full saturation for text and dots
- Use gradient buttons (`from-pocket-accent to-pocket-warm-500`) for primary CTAs
- Include the card lift interaction: hover translateY(-2px) + shadow increase for pressable cards

### Don't
- Don't use Instrument Serif for body text, labels, or amounts -- it's display-only
- Don't use small border-radius (4px-8px) on cards or buttons -- Pocket Stack is generously rounded
- Don't use neutral gray shadows -- always use warm-tinted (`hsl(30, 20%, 50%)`)
- Don't use pure black (`#000000`) for any text -- always warm browns from the `--pocket-warm-*` scale
- Don't use blue or purple as the primary interactive color -- orange is the sole accent
- Don't put status information only in text -- always include the colored dot indicator in badges
- Don't use flat, no-shadow cards -- every card needs at minimum `shadow-pocket-sm` for the stacked metaphor
- Don't use weight 300 for headlines -- unlike Stripe's whisper-light approach, Pocket Stack uses standard weight (400) for serif and semi-bold (600) for sans
- Don't apply shadows in dark mode with the warm shadow color -- switch to pure black (`hsl(0, 0%, 0%)`)
- Don't skip the gradient on primary CTA buttons -- solid orange looks flat; the orange-to-brown gradient adds dimensionality

## 8. Responsive Behavior

### Breakpoints
| Name | Width | Key Changes |
|------|-------|-------------|
| Tiny | <375px | Font size reduction, padding collapse (p-4 -> p-3), 2-col grids -> 1-col |
| Mobile (xs) | 375px+ | Default design: single column, bottom nav, full-width cards, px-4 |
| Tablet (md) | 768px+ | max-w-2xl container, px-6, bottom nav hidden, top nav revealed |
| Desktop (lg) | 1024px+ | Generous margins, centered content, multi-column where applicable |

### Touch Targets
- Primary buttons: 48px height (h-12), full width on mobile
- Amount selection buttons: 56px height (h-14) for easy thumb tapping
- Input fields: 56px height (h-14) for comfortable text entry
- Back button: 32px circular target
- Nav icons: 20px icon with 10px label below, adequate touch spacing
- List items: full-width 64px+ rows with 16px padding

### Collapsing Strategy
- Hero: 2.5rem (40px) display maintained across breakpoints -- already mobile-optimized
- Navigation: bottom bar on mobile (fixed, 64px) -> top navigation on tablet+
- Envelope cards: single column stack at all breakpoints -- never multi-column
- Amount grid: 2 columns -> 1 column on tiny devices (<375px)
- Dialog/sheets: 92vw on mobile -> 448px max on desktop
- Section spacing: p-6 -> p-4 on tiny devices
- Gaps: gap-4 -> gap-3 on tiny devices
- Non-essential elements hidden at <375px via `.hide-on-tiny`

### Image Behavior
- Icon containers maintain rounded-xl (12px) border-radius at all sizes
- Status badge dots maintain 6px size regardless of viewport
- Category icons scale proportionally within their containers (10px-20px icon in 32px-44px container)

## 9. Agent Prompt Guide

### Quick Color Reference
- Primary CTA: Vibrant Orange (`#F0920D`)
- CTA Gradient End: Dark Warm Brown (`#6F5344`)
- Background: Warm Off-White (`#F7F3EF`)
- Card background: Card White (`#FEFBF8`)
- Heading text: Deep Warm Brown (`#2B1D15`)
- Body text: Dark Warm (`#6F5344`)
- Label text: Deep Warm (`#583C27`)
- Border: Sand (`#DDD2C7`)
- Card footer border: Light Beige (`#EFEAE4`)
- Active/success: Green (`#2DA66E`)
- Warning/low: Amber (`#F59E0B`)
- Frozen: Blue (`#4FA8FF`)
- Muted/disabled: Gray (`#727B8C`)
- Negative amounts: Red (`#DC2626`)

### Example Component Prompts
- "Create an envelope card on `#FEFBF8` background. 1px solid `#DDD2C7` border, 16px radius. Shadow: `0 2px 8px hsl(30 20% 50% / 0.1), 0 1px 3px hsl(30 20% 50% / 0.08)`. Title at 18px DM Sans weight 600, color `#2B1D15`. Amount at 24px DM Sans weight 700, `tabular-nums tracking-tight`, color `#2B1D15`. Subtitle at 13px weight 500, color `#6F5344`. On hover: shadow increases to `0 4px 16px warm/0.12`, translateY(-2px), 200ms transition."
- "Build a status badge: rounded-full pill. Background `#2DA66E` at 15% opacity, text `#2DA66E`, 12px DM Sans weight 600. 6px solid green dot before label. Padding 10px horizontal, 4px vertical."
- "Design a primary CTA button: full width, 48px height, 16px radius. Background gradient left-to-right from `#F0920D` to `#6F5344`. White text at 16px DM Sans weight 600. On hover: 90% opacity. On press: scale to 95%."
- "Create a bottom sheet: `#FEFBF8` background, 16px radius, shadow `0 8px 24px hsl(30 20% 50% / 0.14), 0 4px 10px hsl(30 20% 50% / 0.1)`. Pull handle at top: 4px x 40px rounded-full, color `#C7B3A3`. Header with Instrument Serif 18px title. Step progress: 4 bars, 24px x 6px each, rounded-full, active `#F0920D`, inactive `#DDD2C7`."
- "Design a spendable banner: gradient background `from #F0920D/10 via #EFEAE4/60 to #F7F3EF`. 1px border `#F0920D` at 20% opacity. 16px radius. 44px icon container with rounded-xl, accent at 15% bg. 14px semibold title in `#2B1D15`, 12px description in `#6F5344`. Chevron-right in accent color. On hover: shadow increases, lift 2px."

### Iteration Guide
1. Every container uses `rounded-2xl` (16px radius) -- this is non-negotiable. Cards, buttons, inputs, modals, banners all share this radius.
2. Instrument Serif is reserved for display and dialog titles only. All other text is DM Sans.
3. Shadow formula: `0 Ypx Bpx hsl(30 20% 50% / Apct), 0 Ypx Bpx hsl(30 20% 50% / Apct)` -- always two layers, always warm-tinted.
4. Heading/body color is `#2B1D15` (deep warm brown), secondary text is `#6F5344`, labels are `#583C27` -- never use black.
5. Financial amounts always get `tabular-nums` + `tracking-tight` + DM Sans weight 700.
6. Status is communicated through the 4-color system: green (active), blue (frozen), amber (needs money), gray (no card). Badge backgrounds always at 15% opacity.
7. Primary CTA is always a gradient button: `from-pocket-accent to-pocket-warm-500`. Never use solid orange.
8. Interactive cards lift on hover: `-translate-y-0.5` (2px up) + shadow increase from `pocket` to `pocket-md`. Settle on press: `translate-y-0` + shadow decrease to `pocket-sm`.
9. Mobile-first: design at 375px first. The `xs` breakpoint is the baseline, not a fallback.
10. The warm palette ranges from hue 16 to hue 38 -- stay within this band. No cool grays, no blue-grays.
