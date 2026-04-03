# Design System: Envelopd (Pocket Stack)

## 1. Visual Theme & Atmosphere

Envelopd is a personal finance app built around the envelope budgeting method -- each spending category is a "pocket" with its own card and balance. The design system, called Pocket Stack, pairs a fresh, approachable light mode with a confident, dark-first night mode -- unified by a signature mint-green accent that reads as modern, money-adjacent, and unmistakably fintech without the coldness of traditional banking blue.

Light mode opens on a soft warm-gray canvas (`#F4F4EE`) with near-black text (`#141414`) and clean white card surfaces (`#FEFEFE`). Dark mode inverts to a deep void (`#08080D`) with ghostly off-white text (`#EDEDF2`) and charcoal card surfaces (`#101018`). Both modes share the same mint accent family: `#00D492` (light) brightening to `#00E5A0` (dark/neon) -- a single hue band that adapts to its surface for optimal contrast.

The typography pairing is the defining element of Pocket Stack's character. `Instrument Serif` serves as the display font -- used for hero headlines and prominent titles -- lending a personal, editorial quality that says "this is your money story." `DM Sans` handles body text with a geometric friendliness, falling back to `Inter` for system compatibility. At the hero size (2.5rem / 40px), Instrument Serif runs with tight tracking (-0.02em), creating dense, confident headlines. For financial amounts, `DM Sans` at 1.5rem with bold weight (700) and `tabular-nums` ensures numbers align cleanly in the card stack.

What truly distinguishes Pocket Stack is its card-first architecture. Every piece of content lives inside a rounded card (`rounded-2xl` / 16px radius), and elevation is communicated through layered shadows -- neutral in light mode, pure black in dark mode. Cards lift on hover with a subtle -2px translate and shadow intensification, creating a tactile "pick up and look" interaction that reinforces the physical metaphor of stacked envelopes. The status system uses semantic colors -- mint-green for active, blue for frozen, amber for needs-money -- applied at 12% opacity backgrounds with full-saturation text, ensuring status is communicated through color meaning rather than decoration.

**Key Characteristics:**
- Instrument Serif for display type -- editorial, personal, serif warmth
- DM Sans as the primary body font -- geometric, friendly, highly readable
- Dual-mode palette: warm gray light (`#F4F4EE`) / void dark (`#08080D`)
- Mint-green accent (`#00D492` light, `#00E5A0` dark) as the sole interactive color
- Card-first architecture: everything is a `rounded-2xl` card with layered shadows
- Neutral shadows in light mode, pure black shadows in dark mode
- Mobile-first responsive design starting at 375px (`xs` breakpoint)
- Semantic status colors: mint (active), blue (frozen), amber (needs money), gray (no card)
- `tabular-nums` and `tracking-tight` on all financial data for clean number alignment
- Solid mint CTA buttons -- clean, confident, no gradients needed
- Budget progress bars on cards for at-a-glance envelope health

## 2. Color Palette & Roles

### Light Mode

#### Primary
- **Warm Gray** (`#F4F4EE`): `--pocket-bg`. Primary page background. Soft, warm neutral -- not sterile white, not tinted beige.
- **Near Black** (`#141414`): `--pocket-text`. Primary text color for headings and card content. Deep, clean, maximum readability.
- **Mint** (`#00D492`): `--pocket-accent`. Primary interactive color. CTA buttons, active nav, links, progress indicators.

#### Card & Surface
- **Clean White** (`#FEFEFE`): `--pocket-card`. Card background. Pure white for elevated surfaces against the warm-gray page.
- **Warm Gray** (`#F4F4EE`): `--pocket-surface`. Nested surface inside cards, secondary containers.
- **Soft Border** (`#E6E6DC`): `--pocket-border`. Default card borders, dividers, input borders.

#### Accent & Interactive
- **Mint** (`#00D492`): `--pocket-accent`. Primary CTA, active state, step progress bars.
- **Deep Mint** (`#00A872`): `--pocket-accent-deep`. Status badge text, hover emphasis.
- **White** (`#FFFFFF`): `--pocket-accent-foreground` (alias: `--pocket-accent-fg`). Text on accent backgrounds.

#### Neutral Scale
- **Muted** (`#7A7A72`): `--pocket-muted`. Secondary body text, descriptions, metadata, inactive nav.
- **Border** (`#E6E6DC`): `--pocket-border`. Card borders, dividers, progress bar tracks.
- **Surface** (`#F4F4EE`): `--pocket-surface`. Nested backgrounds, back button hover.

#### Status Colors
- **Active Mint** (`#00A872`): `--pocket-status-active`. Healthy envelope, active card. Badge bg at `rgba(0,212,146,0.12)`.
- **Frozen Blue** (`#4A7AFF`): `--pocket-status-frozen`. Frozen card, paused state. Card gradient tint at 4% opacity, border at 25%.
- **Low Amber** (`#C68000`): `--pocket-status-needs-money`. Low balance warning. Badge bg at `rgba(230,150,0,0.12)`, border at 30%.
- **No Card Gray** (`#7A7A72`): `--pocket-status-no-card`. Missing card, disabled state. Badge bg at `rgba(120,120,114,0.1)`.

#### Semantic
- **Success** (`#10B981`): `--success`. Confirmation states, positive balance changes.
- **Warning** (`#E09600`): `--warning`. Caution states, approaching limits.
- **Danger** (`#EF4444`): `--danger`. Destructive actions, negative balances, errors.

#### Shadow Colors
- **Light Shadow** (`rgba(0,0,0,0.04)`): Near shadow layer.
- **Light Shadow Far** (`rgba(0,0,0,0.03)`): Far shadow layer. Clean and neutral -- no color tint.

### Dark Mode

#### Primary
- **Void** (`#08080D`): `--pocket-bg`. Primary page background. Near-black with a subtle cool undertone.
- **Off White** (`#EDEDF2`): `--pocket-text`. Primary text color. Soft white that avoids pure-white glare.
- **Neon Mint** (`#00E5A0`): `--pocket-accent`. Primary interactive color. Brighter than light mode for dark surface contrast.

#### Card & Surface
- **Charcoal** (`#101018`): `--pocket-card`. Card background. Dark surface with faint cool undertone.
- **Deep Void** (`#08080D`): `--pocket-surface`. Nested surfaces, page background.
- **Dark Border** (`#1C1C28`): `--pocket-border`. Card borders, dividers.

#### Accent & Interactive
- **Neon Mint** (`#00E5A0`): `--pocket-accent`. Primary CTA. Vivid on dark surfaces.
- **Deep Mint** (`#00B880`): `--pocket-accent-deep`. Hover states, status text.
- **Void** (`#08080D`): `--pocket-accent-foreground` (alias: `--pocket-accent-fg`). Text on accent backgrounds.

#### Neutral Scale
- **Muted** (`#5E5E72`): `--pocket-muted`. Secondary text, descriptions, inactive nav.
- **Card Text** (`#D4D4DE`): `--pocket-card-text`. Card titles, labels slightly softer than primary.
- **Border** (`#1C1C28`): `--pocket-border`. Card borders, dividers.

#### Status Colors
- **Active Neon** (`#00E5A0`): `--pocket-status-active`. Badge bg at `rgba(0,229,160,0.12)`.
- **Frozen Blue** (`#648CFF`): `--pocket-status-frozen`. Badge bg at `rgba(100,140,255,0.12)`. Card gradient at 6%.
- **Low Amber** (`#FFB74D`): `--pocket-status-needs-money`. Badge bg at `rgba(255,183,77,0.12)`, border at 25%.
- **No Card Gray** (`#5E5E72`): `--pocket-status-no-card`. Badge bg at `rgba(94,94,114,0.15)`.

#### Shadow Colors
- **Dark Shadow** (`rgba(0,0,0,0.3)`): Near shadow layer.
- **Dark Shadow Far** (`rgba(0,0,0,0.2)`): Far shadow layer. Pure black for clean depth on dark surfaces.

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

**Primary Solid (CTA)**
- Background: `--pocket-accent` (`#00D492` light, `#00E5A0` dark)
- Text: `--pocket-accent-foreground` (`#FFFFFF` light, `#08080D` dark)
- Height: 48px (h-12)
- Padding: implicit via full-width
- Radius: 16px (rounded-2xl)
- Font: 16px DM Sans weight 600
- Hover: opacity 90%
- Active: scale 95%
- Shadow: `0 4px 14px rgba(0,212,146,0.35)` (light), `0 4px 14px rgba(0,229,160,0.3)` (dark)
- Use: Primary action ("Continue", "Confirm Top Up", "Done")

**Primary Solid (Pill)**
- Background: same as CTA
- Text: same as CTA
- Radius: 9999px (rounded-full)
- Font: 14px DM Sans weight 600
- Use: Compact actions ("Done", "Try Again")

**Outlined**
- Background: transparent
- Text: `--pocket-text`
- Border: `1px solid --pocket-border`
- Radius: 9999px (rounded-full)
- Font: 14px DM Sans weight 500
- Hover: background shifts to `--pocket-surface`
- Use: Secondary actions ("Close", "Cancel")

**Quick Amount**
- Background (default): `--pocket-card`
- Background (selected): `--pocket-accent` at 8% opacity
- Text (default): `--pocket-text`
- Text (selected): `--pocket-accent`
- Height: 56px (h-14)
- Border: 2px solid `--pocket-border` (default), `--pocket-accent` (selected)
- Radius: 16px (rounded-2xl)
- Font: 18px DM Sans weight 600
- Active: scale 95%
- Use: Amount selection grid ($25, $50, $100, $200)

**Nav Circle (Top-Up)**
- Background: `--pocket-accent`
- Size: 44px x 44px
- Radius: 9999px (circle)
- Offset: -16px top margin to float above nav bar
- Shadow: `0 4px 14px` accent at 35% opacity
- Use: Central navigation button

**Back Button**
- Background: transparent
- Size: 32px x 32px (h-8 w-8)
- Radius: 9999px (rounded-full)
- Text: `--pocket-muted`
- Hover: background `--pocket-surface`
- Use: Navigation back in multi-step flows

### Cards & Containers

**PocketCard (Primary)**
- Background: `--pocket-card` (`#FEFEFE` light, `#101018` dark)
- Border: 1px solid `--pocket-border`
- Radius: 16px (rounded-2xl)
- Shadow (light): `0 2px 8px rgba(0,0,0,0.04), 0 1px 3px rgba(0,0,0,0.03)`
- Shadow (dark): `0 2px 8px rgba(0,0,0,0.3), 0 1px 3px rgba(0,0,0,0.2)`
- Padding: 16px (p-4)
- Text: `--pocket-text`
- Transition: all 200ms

**PocketCard (Pressable)**
- Inherits Primary
- Cursor: pointer
- Hover: shadow increases, translateY(-2px)
- Active: shadow decreases, translateY(0)
- Use: Tappable envelope cards, list items

**PocketCard Variants**
- `active`: border `--pocket-status-active` at 30% opacity
- `frozen`: gradient bg from card to frozen at 4-6%, border frozen at 20-25%
- `needs-money`: border `--pocket-status-needs-money` at 30%
- `no-card`: bg `--pocket-surface`, border default, opacity 90%

**Budget Progress Bar**
- Track: `--pocket-border` (`#E6E6DC` light, `#1C1C28` dark)
- Fill: matches card status color (active=mint, frozen=blue, low=amber)
- Height: 4px
- Radius: 9999px (rounded-full)
- Margin-top: 8px

**Card Footer Divider**
- Border-top: 1px solid `--pocket-border`
- Margin-top: 12px (mt-3)
- Padding-top: 12px (pt-3)

**Dialog / Bottom Sheet**
- Background: `--pocket-card`
- Border: `--pocket-border`
- Radius: 16px (rounded-2xl)
- Shadow: pocket-lg
- Max width: 92vw mobile, 448px (sm:max-w-md) desktop
- Max height: 85vh
- Pull handle: 4px x 40px rounded-full, `--pocket-muted` at 40% opacity

### Badges / Status Pills

**StatusBadge**
- Shape: pill (rounded-full)
- Padding: 10px horizontal, 4px vertical (px-2.5 py-1)
- Font: 12px DM Sans weight 600
- Dot: 5px x 5px circle, full saturation status color
- Background: status color at 12% opacity
- Text: full saturation status color (use deep variant in light mode for WCAG)

**Low Balance Indicator**
- Background: `--pocket-status-needs-money` at 12% opacity
- Text: `--pocket-status-needs-money`
- Padding: 8px horizontal, 2px vertical (px-2 py-0.5)
- Font: 12px DM Sans weight 500
- Radius: 9999px (rounded-full)

### Inputs & Forms
- Height: 56px (h-14) for primary inputs
- Border: 2px solid `--pocket-border`
- Radius: 16px (rounded-2xl)
- Focus: border color changes to `--pocket-accent`
- Label: `--pocket-muted`, 14px DM Sans weight 500
- Text: 18px DM Sans weight 600, `--pocket-text`
- Placeholder: `--pocket-muted` at 60% opacity
- Currency prefix: absolute positioned "$" in `--pocket-muted`, 18px weight 600

### Spendable Banner (CTA Card)
- Background: gradient `from accent/8% to accent/2%`
- Border: 1px solid `--pocket-accent` at 18% opacity (light), 15% (dark)
- Radius: 16px (rounded-2xl)
- Shadow: pocket-sm
- Padding: 12px 14px
- Icon container: 38px x 38px, rounded-xl (10px), accent at 12% bg
- Hover: shadow increases, translateY(-1px)
- Title: 13px DM Sans weight 600, `--pocket-text`
- Description: 11px DM Sans weight 400, `--pocket-muted`
- Arrow: `--pocket-accent`, font-weight 600

### Navigation (Mobile Bottom)
- Position: fixed bottom, z-50
- Background: `--pocket-card` at 92% opacity
- Backdrop: blur-lg (16px frosted glass)
- Border-top: 1px solid `--pocket-border`
- Height: 64px + safe-area-inset-bottom
- Items: 5 (Home, Cards, Top-Up, Family, More)
- Icon size: 22px x 22px, 7px radius
- Label: 9px DM Sans weight 500
- Active: `--pocket-accent` color for both icon and label
- Inactive: `--pocket-muted` color
- Top-Up button: solid accent circle, -16px offset above nav, accent shadow glow

### Step Progress Indicator
- Bars: 4 segments, 24px x 6px each (w-6 h-1.5)
- Shape: rounded-full
- Active: `--pocket-accent`
- Inactive: `--pocket-border`
- Gap: 4px (gap-1)
- Transition: colors

## 5. Layout Principles

### Spacing System
- Base unit: 4px
- Scale: 2px (0.5), 4px (1), 6px (1.5), 8px (2), 10px (2.5), 12px (3), 16px (4), 20px (5), 24px (6)
- Notable: The 4px base creates a tight, mobile-optimized rhythm. Most internal card spacing uses 8-16px, while section gaps use 10-12px.

### Grid & Container
- Max content width: 512px (max-w-lg) on mobile, 672px (max-w-2xl) on tablet+
- Primary layout: single column, vertically stacked cards
- Card stacking: gap-3 (12px) between envelope cards
- Amount grid: 2 columns for quick-select buttons
- Container: centered with px-4 (16px) mobile, px-6 (24px) desktop

### Whitespace Philosophy
- **Card-first density**: Content is organized within cards, and whitespace exists primarily between cards (10-12px gaps) rather than within them (compact 14-16px padding). This creates a "stack of physical envelopes" visual metaphor.
- **Generous touch chrome**: Interactive elements (buttons at 48-56px, inputs at 56px) are generously sized for touch, but informational elements (labels at 13px, captions at 12px) are compact. Touch targets are large, data display is dense.
- **Section rhythm**: The envelope list uses consistent card gaps with no section headers breaking the vertical flow -- the cards ARE the sections.

### Border Radius Scale
- Small (4px): Fine UI elements (progress dots, dividers)
- Standard (8px): Form labels, icon containers (rounded-lg)
- Comfortable (10-12px): Nested elements, icon backgrounds, banner icons (rounded-xl)
- Primary (16px): Cards, buttons, inputs, modals, banners (rounded-2xl)
- Full (9999px): Pills, badges, circular buttons, nav icons (rounded-full)
- Note: `rounded-2xl` (16px) is the workhorse -- it appears on virtually every container. This large radius is intentional: it creates the soft, approachable feel that distinguishes Pocket Stack from sharp-cornered financial tools.

## 6. Depth & Elevation

### Light Mode

| Level | Treatment | Use |
|-------|-----------|-----|
| Flat (Level 0) | No shadow | Page background, inline text, nested elements |
| Subtle (Level 1) | `0 1px 3px rgba(0,0,0,0.04), 0 1px 2px rgba(0,0,0,0.03)` | Baseline card, banner shadow |
| Standard (Level 2) | `0 2px 8px rgba(0,0,0,0.04), 0 1px 3px rgba(0,0,0,0.03)` | Default PocketCard, resting interactive elements |
| Elevated (Level 3) | `0 6px 20px rgba(0,0,0,0.08), 0 2px 6px rgba(0,0,0,0.04)` | Hovered cards, focused elements, popovers |
| Deep (Level 4) | `0 8px 24px rgba(0,0,0,0.12), 0 4px 10px rgba(0,0,0,0.06)` | Modals, bottom sheets |
| Glow | `0 4px 14px rgba(0,212,146,0.35)` | CTA buttons, Top-Up nav circle |

### Dark Mode

| Level | Treatment | Use |
|-------|-----------|-----|
| Flat (Level 0) | No shadow | Page background, inline text, nested elements |
| Subtle (Level 1) | `0 1px 3px rgba(0,0,0,0.2), 0 1px 2px rgba(0,0,0,0.15)` | Baseline card |
| Standard (Level 2) | `0 2px 8px rgba(0,0,0,0.3), 0 1px 3px rgba(0,0,0,0.2)` | Default PocketCard |
| Elevated (Level 3) | `0 6px 20px rgba(0,0,0,0.45), 0 2px 6px rgba(0,0,0,0.25)` | Hovered cards, popovers |
| Deep (Level 4) | `0 8px 24px rgba(0,0,0,0.5), 0 4px 10px rgba(0,0,0,0.3)` | Modals, bottom sheets |
| Glow | `0 4px 14px rgba(0,229,160,0.3)` | CTA buttons, Top-Up nav circle |

**Shadow Philosophy**: Pocket Stack uses clean, neutral shadows -- no color tinting. In light mode, `rgba(0,0,0)` at very low opacity (3-12%) creates subtle depth that lets the card content speak. In dark mode, the same black shadows at higher opacity (15-50%) create visible separation between surfaces. The addition of an accent "glow" shadow on CTA buttons gives them a floating, neon quality -- especially striking in dark mode where the mint glow bleeds onto the void background.

### Decorative Depth
- CTA glow: accent-colored shadow creates a soft halo around primary buttons
- Frosted glass navigation: `bg-pocket-card/92 backdrop-blur-lg` creates a translucent surface
- Status card variants use gradient backgrounds (frozen: card to frozen at 4-6%) for subtle atmospheric tinting
- Progress bars create visual "fill" depth within cards without needing shadows

## 7. Do's and Don'ts

### Do
- Use Instrument Serif only for hero/display headlines and dialog titles -- it's the emotional anchor, not a workhorse
- Use DM Sans with weight 600-700 for financial amounts -- bold numbers communicate monetary confidence
- Use neutral `rgba(0,0,0)` shadows -- no warm/cool tinting
- Use `#141414` (near-black) for light mode text and `#EDEDF2` (off-white) for dark mode text -- never pure black or white
- Keep border-radius at 16px (`rounded-2xl`) for all cards, buttons, and inputs -- generous rounding is the brand
- Use `tabular-nums` and `tracking-tight` for any financial number display
- Use mint (`#00D492` / `#00E5A0`) as the sole interactive/CTA color
- Apply status colors at 12% opacity for backgrounds, full saturation for text and dots
- Include the card lift interaction: hover translateY(-2px) + shadow increase for pressable cards
- Add budget progress bars to envelope cards for at-a-glance health
- Use accent glow shadow on CTA buttons for the signature floating effect
- Ship light and dark mode together -- they are one system, not separate features

### Don't
- Don't use Instrument Serif for body text, labels, or amounts -- it's display-only
- Don't use small border-radius (4px-8px) on cards or buttons -- Pocket Stack is generously rounded
- Don't use warm-tinted or brown shadows -- the old palette is gone; shadows are neutral black
- Don't use pure black (`#000000`) for light mode text or pure white (`#FFFFFF`) for dark mode text
- Don't use orange, purple, or blue as the primary interactive color -- mint green is the sole accent
- Don't put status information only in text -- always include the colored dot indicator in badges
- Don't use flat, no-shadow cards -- every card needs at minimum Level 1 shadow for the stacked metaphor
- Don't use gradient CTAs -- solid mint with accent glow shadow replaces the old orange-to-brown gradient
- Don't use warm browns anywhere -- the neutral scale is cool gray (`#7A7A72` light, `#5E5E72` dark)
- Don't brighten the neon mint for light mode or dim it for dark mode -- each mode has its own calibrated accent value

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
- Nav icons: 22px icon with 9px label below, adequate touch spacing
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
- Status badge dots maintain 5px size regardless of viewport
- Category icons scale proportionally within their containers (10px-20px icon in 32px-44px container)

## 9. Agent Prompt Guide

### Quick Color Reference (Light Mode)
- Primary CTA: Mint (`#00D492`)
- CTA glow: `rgba(0,212,146,0.35)`
- Background: Warm Gray (`#F4F4EE`)
- Card background: Clean White (`#FEFEFE`)
- Heading text: Near Black (`#141414`)
- Body/secondary text: Muted (`#7A7A72`)
- Border: Soft Border (`#E6E6DC`)
- Active/success: Deep Mint (`#00A872`)
- Warning/low: Amber (`#C68000`)
- Frozen: Blue (`#4A7AFF`)
- Muted/disabled: Gray (`#7A7A72`)
- Negative amounts: Red (`#EF4444`)

### Quick Color Reference (Dark Mode)
- Primary CTA: Neon Mint (`#00E5A0`)
- CTA glow: `rgba(0,229,160,0.3)`
- Background: Void (`#08080D`)
- Card background: Charcoal (`#101018`)
- Heading text: Off White (`#EDEDF2`)
- Body/secondary text: Muted (`#5E5E72`)
- Border: Dark Border (`#1C1C28`)
- Active/success: Neon Mint (`#00E5A0`)
- Warning/low: Amber (`#FFB74D`)
- Frozen: Blue (`#648CFF`)
- Muted/disabled: Gray (`#5E5E72`)
- Negative amounts: Red (`#EF4444`)

### Example Component Prompts
- "Create an envelope card on `#FEFEFE` background. 1px solid `#E6E6DC` border, 16px radius. Shadow: `0 2px 8px rgba(0,0,0,0.04), 0 1px 3px rgba(0,0,0,0.03)`. Title at 18px DM Sans weight 600, color `#141414`. Amount at 24px DM Sans weight 700, `tabular-nums tracking-tight`, color `#141414`. Budget text at 11px weight 400, color `#7A7A72`. Progress bar: 4px height, `#E6E6DC` track, `#00D492` fill, rounded-full. On hover: shadow increases to `0 6px 20px rgba(0,0,0,0.08)`, translateY(-2px), 200ms transition."
- "Build a status badge: rounded-full pill. Background `rgba(0,212,146,0.12)`, text `#00A872`, 12px DM Sans weight 600. 5px solid mint dot before label. Padding 10px horizontal, 4px vertical."
- "Design a primary CTA button: full width, 48px height, 16px radius. Background `#00D492`, white text at 16px DM Sans weight 600. Shadow: `0 4px 14px rgba(0,212,146,0.35)`. On hover: 90% opacity. On press: scale to 95%."
- "Create a bottom sheet: `#FEFEFE` background, 16px radius, shadow `0 8px 24px rgba(0,0,0,0.12), 0 4px 10px rgba(0,0,0,0.06)`. Pull handle at top: 4px x 40px rounded-full, `#7A7A72` at 40%. Header with Instrument Serif 18px title. Step progress: 4 bars, 24px x 6px each, rounded-full, active `#00D492`, inactive `#E6E6DC`."
- "Design a spendable banner: gradient background from `rgba(0,212,146,0.08)` to `rgba(0,212,146,0.02)`. 1px border `#00D492` at 18% opacity. 16px radius. 38px icon container with 10px radius, accent at 12% bg. 13px semibold title in `#141414`, 11px description in `#7A7A72`. Chevron-right in `#00D492`. On hover: shadow increases, lift 1px."

### Iteration Guide
1. Every container uses `rounded-2xl` (16px radius) -- this is non-negotiable. Cards, buttons, inputs, modals, banners all share this radius.
2. Instrument Serif is reserved for display and dialog titles only. All other text is DM Sans.
3. Shadow formula (light): `0 Ypx Bpx rgba(0,0,0, 0.03-0.12)` -- always two layers, always neutral.
4. Shadow formula (dark): `0 Ypx Bpx rgba(0,0,0, 0.15-0.50)` -- same structure, higher opacity.
5. CTA buttons get the accent glow: `0 4px 14px accent/35%` -- this is the signature.
6. Light mode text is `#141414`, secondary is `#7A7A72`. Dark mode text is `#EDEDF2`, secondary is `#5E5E72`. Never pure black or white.
7. Financial amounts always get `tabular-nums` + `tracking-tight` + DM Sans weight 700.
8. Status is communicated through the 4-color system: mint (active), blue (frozen), amber (needs money), gray (no card). Badge backgrounds always at 12% opacity.
9. Primary CTA is always solid `--pocket-accent` with glow shadow. No gradients.
10. Interactive cards lift on hover: translateY(-2px) + shadow increase. Settle on press: translateY(0) + shadow decrease.
11. Mobile-first: design at 375px first. The `xs` breakpoint is the baseline, not a fallback.
12. Light mode accent is `#00D492`, dark mode accent is `#00E5A0`. Do not swap them -- each is calibrated for its surface.
