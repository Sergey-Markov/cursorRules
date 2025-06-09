# Accessibility-First Development Guidelines for Cursor AI

This document outlines the principles and best practices for developing accessible web and mobile applications,
adhering to WCAG 2.1 (AA level). This rule is intended to guide Cursor AI in generating code that is
inclusive and usable by all users, including people with disabilities, with minimal post-generation rework.

## Core Principles (WCAG 2.1 AA)

### 1. Perceivable (Сприйнятливість)
- **Text Alternatives:** Provide text alternatives for all non-text content (images, audio, video).
  - HTML: `alt` attribute for `<img>`.
  - Mobile (iOS): `accessibilityLabel`, `accessibilityHint`.
  - Mobile (Android): `contentDescription`.
- **Adaptability:** Content should be presentable in various ways (e.g., resizable text, screen reader compatible).
- **Contrast:** Ensure sufficient color contrast (4.5:1 for normal text, 3:1 for large text).
- **No Color-Only Information:** Do not rely solely on color to convey information.
- **Audio Control:** Allow users to control automatically playing audio.

### 2. Operable (Керованість)
- **Keyboard Navigation:** All functionality must be accessible via keyboard alone.
- **Visible Focus:** Provide a clear visual indicator for keyboard focus (`:focus` CSS).
- **Sufficient Time:** Give users enough time to interact (e.g., control over timers).
- **No Seizures:** Avoid content that can cause seizures (e.g., rapid flashing).
- **Navigation Aids:** Implement "Skip to content" links, clear headings, consistent navigation.

### 3. Understandable (Зрозумілість)
- **Readability:** Make text content readable and understandable.
- **Predictability:** Ensure interface and navigation are predictable and consistent.
- **Input Assistance:** Help users avoid and correct mistakes (clear error messages, labels).

### 4. Robust (Надійність)
- **Compatibility:** Content must be robust enough to be interpreted by various user agents, including assistive technologies.
- **Valid Code:** Generate valid HTML, CSS, etc.
- **ARIA Attributes:** Use WAI-ARIA roles and attributes for custom or complex UI components to enhance semantic meaning for assistive technologies.

## Platform-Specific Considerations

### Web (Websites, Web Applications, PWAs)
- **HTML Semantics:** Use `<header>`, `<nav>`, `<main>`, `<footer>`, `<button>`, `<label>` for appropriate content.
    - **Headings (`<h1>` - `<h6>`):** Use a single `<h1>` for the main page title. Use subsequent heading levels (`<h2>`, `<h3>`, etc.) in a logical, hierarchical order to structure content. Do not skip heading levels for styling purposes.
    - **Links (`<a>`):** Ensure link text is descriptive and meaningful out of context. Visually differentiate links from surrounding text (not just by color). For links that open new windows or download files, provide clear indication (e.g., visual icon, `aria-label`).
- **CSS:** Ensure logical document order, focus styles, flexible font sizing (em, rem).
- **JavaScript:** Manage focus, use ARIA for dynamic content and complex widgets (modals, tabs).

### Mobile Applications (iOS & Android)
- **Labels & Descriptions:** Provide clear `accessibilityLabel`/`contentDescription` for all UI elements.
- **Navigation Order:** Ensure logical focus order for screen readers.
- **Dynamic Text & Touch Targets:** Support dynamic font sizes and ensure touch targets are sufficiently large (e.g., 44x44 dp/pt).
- **Platform-Specific APIs:** Utilize native accessibility APIs (e.g., `UIAccessibility` for iOS, `AccessibilityService` for Android).

## Testing and Validation
- Encourage testing with screen readers (VoiceOver, TalkBack, NVDA).
- Recommend using automated accessibility checkers (Lighthouse, axe DevTools).

## Relevant Documentation
- **WCAG 2.1 Official:** [https://www.w3.org/WAI/WCAG21/](https://www.w3.org/WAI/WCAG21/)
- **WCAG 2.1 Quick Reference:** [https://www.w3.org/WAI/WCAG21/quickref/](https://www.w3.org/WAI/WCAG21/quickref/)
- **ARIA Authoring Practices Guide (APG):** [https://www.w3.org/WAI/ARIA/apg/](https://www.w3.org/WAI/ARIA/apg/)
- **MDN Web Docs - Accessibility:** [https://developer.mozilla.org/en-US/docs/Web/Accessibility](https://developer.mozilla.com/en-US/docs/Web/Accessibility)
- **Apple Human Interface Guidelines - Accessibility:** [https://developer.apple.com/design/human-interface-guidelines/accessibility](https://developer.apple.com/design/human-interface-guidelines/accessibility)
- **Android Developers - Accessibility:** [https://developer.android.com/guide/topics/ui/accessibility](https://developer.android.com/guide/topics/ui/accessibility)
- **European Accessibility Act (EAA):** [https://ec.europa.eu/social/main.jsp?catId=1202&langId=en](https://ec.europa.eu/social/main.jsp?catId=1202&langId=en)
