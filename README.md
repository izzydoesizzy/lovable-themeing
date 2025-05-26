**Core Design Philosophy**  
The design follows a modern, clean, professional aesthetic with subtle purple branding, excellent spacing, and sophisticated interactions. It uses a design-system approach with consistent tokens and components.

---

## Color Palette

### Primary Brand Colors
- **Primary Purple**: `hsl(260, 84%, 58%)`  
  Main brand color used for CTAs and highlights  
- **Primary Purple (Dark Mode)**: `hsl(260, 84%, 70%)`  
  Slightly lighter for dark backgrounds  

### Extended Brand Palette
```css
:root {
  --brand-50:  #f5f3ff;  /* Very light purple background */
  --brand-100: #ede8ff;  /* Light purple background */
  --brand-200: #d9d0fc;  /* Subtle purple tint */
  --brand-300: #beb0f9;  /* Light purple accent */
  --brand-400: #9d85f3;  /* Medium purple */
  --brand-500: #7c55eb;  /* Core brand purple */
  --brand-600: #6c3de0;  /* Primary purple (main) */
  --brand-700: #5a2dcb;  /* Darker purple */
  --brand-800: #4c26a7;  /* Deep purple */
  --brand-900: #412286;  /* Very dark purple */
  --brand-950: #281352;  /* Almost black purple */
}
```

### Semantic Colors (Light Mode)
- **Background**: `hsl(250, 50%, 99%)` – Very light lavender-white  
- **Foreground**: `hsl(250, 10%, 15%)` – Dark gray with purple undertone  
- **Card Background**: `hsl(0, 0%, 100%)` – Pure white  
- **Border**: `hsl(250, 10%, 90%)` – Light gray with purple tint  
- **Muted Text**: `hsl(250, 10%, 50%)` – Medium gray  
- **Secondary Background**: `hsl(260, 30%, 96%)` – Very light purple  

### Dark Mode Colors
- **Background**: `hsl(250, 10%, 10%)` – Very dark purple-gray  
- **Foreground**: `hsl(0, 0%, 95%)` – Off-white  
- **Card Background**: `hsl(250, 10%, 13%)` – Dark purple-gray  
- **Border**: `hsl(250, 20%, 25%)` – Medium dark gray  

---

## Typography

- **Font Stack**:  
  `-apple-system`, `BlinkMacSystemFont`, `Segoe UI`, `Roboto`, `sans-serif`
- **Headings**: Semibold weight, clear size hierarchy  
- **Body Text**: Regular weight, generous line-height  

### Text Sizes & Hierarchy
| Role               | Class           | Size  | Weight      |
|--------------------|-----------------|-------|-------------|
| Large Headings     | `text-2xl`      | 32px  | `font-semibold` |
| Section Headings   | `text-xl`       | 24px  | `font-semibold` |
| Card Titles        | `text-lg`       | 20px  | `font-medium`   |
| Body Text          | `text-sm`       | 14px  | regular        |
| Small Text (Meta)  | `text-xs`       | 12px  | regular        |

---

## Spacing & Layout

- **Container**: Centered with `2rem` padding, max-width `1400px` (`2xl` screens)  
- **Card Padding**:  
  - Headers/content: `p-6` (24px)  
  - Compact cards: `p-4` (16px)  
- **Component Spacing**: `space-y-4` (16px) between related elements  
- **Grid Gaps**:  
  - Default: `gap-4` (16px)  
  - Larger layouts: `gap-6` (24px)  

---

## Border Radius

- **Base Radius**: `0.75rem` (12px)  
- **Large**: `0.75rem` (12px)  
- **Medium**: `calc(0.75rem - 2px)` (10px)  
- **Small**: `calc(0.75rem - 4px)` (8px)  
- **Logo/Icons**: `rounded-lg` (8px)  

---

## Interactive Components

### Buttons
- **Primary**: `bg-primary` (purple), white text  
- **Secondary**: Light gray background, darker text  
- **Ghost**: Transparent background, hover accent  
- **Outline**: Border with transparent background  
- **Sizes**:  
  - Default: `h-10`  
  - Small: `h-9`  
  - Large: `h-11`  
  - Icon: `h-10 w-10`  

### Cards
- Base: White background, subtle `shadow-sm`, rounded borders  
- Hover Effects:  
  - Increased elevation  
  - Border color change  
  - Subtle upward translation  
- **Special Class**: `.card-highlight` for enhanced hover state  

---

## Animations & Transitions

```css
@keyframes fadeIn {
  0%   { opacity: 0; transform: translateY(10px); }
  100% { opacity: 1; transform: translateY(0); }
}

@keyframes slideIn {
  0%   { transform: translateX(20px); opacity: 0; }
  100% { transform: translateX(0);  opacity: 1; }
}

.fade-in {
  animation: fadeIn 0.3s ease-out both;
}

.slide-in {
  animation: slideIn 0.4s ease-out both;
}

.transition-all {
  transition: all 0.3s ease-out;
}
```

- **Duration**: `0.3–0.4s` for most interactions  
- **Easing**: `ease-out` for natural feel  
- **Hover**: `transition-all` for multi-property smoothness  

---

## Component Patterns

### Header
- Fixed height: `h-16`  
- Backdrop blur (glass-morphism)  
- Logo: purple circle with "O"  
- Navigation: ghost-style buttons  
- Responsive mobile menu  

### Layout Structure
- Full viewport height, flex column  
- **Header** at top, **main** content `flex-1`, **footer** at bottom  
- Container-based centering  

### Wizard/Step Patterns
- Sequential fade-in animations with stagger  
- Progress indicators with active states  
- Smooth transitions between steps  

---

## Visual Effects

- **Backdrop Blur**: Header glass-morphism  
- **Shadows**: `shadow-sm` default, `hover:shadow-md` on interaction  
- **Gradients**: Minimal use—mostly solid colors  
- **Opacity**: Disabled states & overlays  

---

## Key Design Principles

1. **Subtle Branding**: Purple accent without overwhelming  
2. **Generous Spacing**: Ample whitespace for clarity  
3. **Consistent Interactions**: Hover states on all controls  
4. **Progressive Enhancement**: Full dark-mode support  
5. **Accessibility**: Proper contrast & focus outlines  
6. **Performance**: Lightweight animations & efficient CSS  

---

## Implementation Notes

- CSS custom properties for theming  
- Tailwind CSS utility-first approach  
- Component variants via class-variance-authority  
- Consistent naming for design tokens  
- Automatic dark-mode switching  

> This design system creates a professional, modern feel ideal for SaaS applications—balancing personality through purple accents with a premium, spacious layout and smooth, subtle interactions.
