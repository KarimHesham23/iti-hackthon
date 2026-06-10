---
name: Library Nexus
colors:
  surface: '#f7f9fb'
  surface-dim: '#d8dadc'
  surface-bright: '#f7f9fb'
  surface-container-lowest: '#ffffff'
  surface-container-low: '#f2f4f6'
  surface-container: '#eceef0'
  surface-container-high: '#e6e8ea'
  surface-container-highest: '#e0e3e5'
  on-surface: '#191c1e'
  on-surface-variant: '#554336'
  inverse-surface: '#2d3133'
  inverse-on-surface: '#eff1f3'
  outline: '#887364'
  outline-variant: '#dbc2b0'
  surface-tint: '#914d00'
  primary: '#914d00'
  on-primary: '#ffffff'
  primary-container: '#f28c28'
  on-primary-container: '#5d2f00'
  inverse-primary: '#ffb77d'
  secondary: '#545f73'
  on-secondary: '#ffffff'
  secondary-container: '#d5e0f8'
  on-secondary-container: '#586377'
  tertiary: '#505f76'
  on-tertiary: '#ffffff'
  tertiary-container: '#97a7c0'
  on-tertiary-container: '#2c3c51'
  error: '#ba1a1a'
  on-error: '#ffffff'
  error-container: '#ffdad6'
  on-error-container: '#93000a'
  primary-fixed: '#ffdcc3'
  primary-fixed-dim: '#ffb77d'
  on-primary-fixed: '#2f1500'
  on-primary-fixed-variant: '#6e3900'
  secondary-fixed: '#d8e3fb'
  secondary-fixed-dim: '#bcc7de'
  on-secondary-fixed: '#111c2d'
  on-secondary-fixed-variant: '#3c475a'
  tertiary-fixed: '#d3e4fe'
  tertiary-fixed-dim: '#b7c8e1'
  on-tertiary-fixed: '#0b1c30'
  on-tertiary-fixed-variant: '#38485d'
  background: '#f7f9fb'
  on-background: '#191c1e'
  surface-variant: '#e0e3e5'
typography:
  display-lg:
    fontFamily: Hanken Grotesk
    fontSize: 48px
    fontWeight: '700'
    lineHeight: 56px
    letterSpacing: -0.02em
  headline-lg:
    fontFamily: Hanken Grotesk
    fontSize: 32px
    fontWeight: '600'
    lineHeight: 40px
    letterSpacing: -0.01em
  headline-lg-mobile:
    fontFamily: Hanken Grotesk
    fontSize: 24px
    fontWeight: '600'
    lineHeight: 32px
  headline-md:
    fontFamily: Hanken Grotesk
    fontSize: 24px
    fontWeight: '600'
    lineHeight: 32px
  body-lg:
    fontFamily: Hanken Grotesk
    fontSize: 18px
    fontWeight: '400'
    lineHeight: 28px
  body-md:
    fontFamily: Hanken Grotesk
    fontSize: 16px
    fontWeight: '400'
    lineHeight: 24px
  body-sm:
    fontFamily: Hanken Grotesk
    fontSize: 14px
    fontWeight: '400'
    lineHeight: 20px
  label-md:
    fontFamily: JetBrains Mono
    fontSize: 13px
    fontWeight: '500'
    lineHeight: 16px
    letterSpacing: 0.02em
  label-sm:
    fontFamily: JetBrains Mono
    fontSize: 11px
    fontWeight: '500'
    lineHeight: 14px
    letterSpacing: 0.05em
rounded:
  sm: 0.25rem
  DEFAULT: 0.5rem
  md: 0.75rem
  lg: 1rem
  xl: 1.5rem
  full: 9999px
spacing:
  base: 8px
  container-max: 1440px
  gutter: 24px
  margin-desktop: 40px
  margin-mobile: 16px
---

## Brand & Style

The design system is built on a foundation of **Warm Minimalism**. It balances the functional efficiency required for data-heavy management tasks with the inviting atmosphere of a modern physical library. The target audience spans from casual guests to high-velocity administrative staff, necessitating a UI that is both approachable and highly organized.

The aesthetic leans into a **Modern Corporate** style with subtle **Glassmorphism** accents. It utilizes ample whitespace to reduce cognitive load and focuses on high-quality typography to ensure the extensive metadata associated with library catalogs remains legible and structured. The emotional response should be one of "Clarity and Warmth"—where the technology feels sophisticated but the primary brand color ensures it never feels clinical.

## Colors

This design system utilizes a palette centered around "Tangerine Energy" (#F28C28). This primary color is used strategically for calls to action, active states, and brand-identifying accents to avoid overwhelming the user.

- **Primary:** #F28C28 (Used for primary buttons, progress indicators, and active navigation highlights).
- **Secondary:** #1E293B (A deep Slate used for text and high-contrast structural elements).
- **Tertiary:** #64748B (A muted Slate for metadata, labels, and secondary information).
- **Neutral:** #F8FAFC (The base canvas color, providing a crisp, clean background).

The background system employs a "Soft Layering" approach, using slight shifts in neutral tones (Slate 50 to Slate 100) to differentiate content sections without the need for heavy borders.

## Typography

The system uses **Hanken Grotesk** as the primary typeface. Its clean, sharp geometry offers the precision of a tech-focused tool while maintaining high legibility for long book titles and descriptions. 

For technical data, ISBNs, and role-based badges (Guest/Librarian/Admin), **JetBrains Mono** is introduced. This monospaced font provides a subtle "cataloging" feel that differentiates system metadata from editorial content. 

- **Headlines:** Should use tight letter-spacing and semi-bold weights to establish a clear hierarchy.
- **Body:** Standardized on a 16px base for optimal readability.
- **Labels:** Always uppercase when using the monospaced font for badges or small UI hints.

## Layout & Spacing

The design system follows an **8px linear scale** for all spacing tokens. The layout is based on a **12-column fluid grid** for desktop, transitioning to a **4-column grid** for mobile devices.

- **Desktop:** 12 columns, 24px gutters, 40px external margins.
- **Tablet:** 8 columns, 20px gutters, 24px external margins.
- **Mobile:** 4 columns, 16px gutters, 16px external margins.

Role-specific views (Librarian/Admin) should utilize a "Dashboard Layout" with a fixed 280px left-hand navigation rail. Guest views utilize a centered "Search-First" layout with wide margins to focus on discovery.

## Elevation & Depth

Hierarchy is established through **Ambient Shadows** and **Tonal Layers**. Instead of harsh borders, surfaces use elevation to indicate interactivity and importance.

- **Level 0 (Base):** #F8FAFC (The background).
- **Level 1 (Cards/Surface):** White (#FFFFFF) with a very soft, diffused shadow (0px 4px 20px rgba(30, 41, 59, 0.05)).
- **Level 2 (Modals/Popovers):** White (#FFFFFF) with a more pronounced shadow (0px 12px 32px rgba(30, 41, 59, 0.12)).
- **Interactive Depth:** On hover, cards should subtly lift (shadow deepens, Y-offset increases) and buttons should use a slight scale-down effect (0.98x) to mimic physical tactile feedback.

## Shapes

The shape language is **Rounded**, reflecting the "inviting" brand pillar. This softens the professional structure of the system.

- **Standard Elements:** 0.5rem (8px) corner radius for buttons and input fields.
- **Large Elements:** 1rem (16px) corner radius for cards, modals, and container surfaces.
- **Badges/Chips:** Full pill-shape (999px) to distinguish them from actionable buttons.
- **Avatars:** Circular (50%) for user profiles and librarian identities.

## Components

### Buttons
- **Primary:** Filled orange (#F28C28) with white text. 8px radius.
- **Secondary:** Ghost style with an orange outline or light gray fill for less emphasis.
- **Tertiary:** Text-only with a subtle background hover state.

### Input Fields
- Use a light gray background (#F1F5F9) instead of a white background to make the "white" cards pop. 
- Focus state: 2px orange border with a soft orange outer glow.

### Cards (Book/Resource)
- White background, 16px radius, soft ambient shadow.
- Imagery (Book Covers) should have a 4px internal radius.
- Typography within cards should prioritize the title in Hanken Grotesk SemiBold.

### Status Badges (Role-based)
- **Guest:** Slate background, Slate-700 text (Monospaced).
- **Librarian:** Light orange tint background, Orange-700 text (Monospaced).
- **Admin:** Deep slate background, White text (Monospaced).

### Lists & Tables
- Used heavily in Librarian/Admin views. 
- Rows should have a subtle hover state (#F8FAFC) and use "border-less" design, relying on 1px Slate-100 horizontal dividers only.