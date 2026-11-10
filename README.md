# CSS Tools — Visual CSS Playground

A responsive, utility-first CSS playground for experimenting with a sample component and inspecting the CSS output. The interface is built with semantic HTML and Tailwind CSS v4, with a small amount of custom CSS reserved for theme tokens, range sliders, and the CSS-only mobile drawer.

## Features

- Responsive workspace for narrow mobile screens through desktop layouts
- Five application themes: Classic Purple, Dark, Green, Red, and Orange
- Component preview with controls for border radius, padding, background color, and opacity
- Generated CSS panel with syntax-color hooks
- Mobile navigation drawer that opens and closes without JavaScript
- Stable element IDs and `data-*` attributes intended for your JavaScript implementation
- Keyboard-visible focus styles and reduced-motion support

> **JavaScript is intentionally not implemented.** `js/app.js` is a starter file so you can implement the interaction logic yourself. Theme switching and the mobile drawer use CSS only.

## Requirements

- Node.js 20 or later
- npm

## Getting started

```bash
npm install
npm run watch:css
```

The watcher rebuilds `css/style.css` whenever `index.html` or `css/input.css` changes. Open `index.html` in a browser to preview the interface. To create a one-time optimized stylesheet, run:

```bash
npm run build:css
```

The compiled `css/style.css` is committed so the static interface can render without running the build step first. Run the build whenever you add or change Tailwind utility classes in the HTML.

## Project structure

```text
css-tools/
├── index.html          # Accessible page structure and Tailwind utility classes
├── css/
│   ├── input.css       # Tailwind entry point, design tokens, and minimal custom CSS
│   └── style.css       # Compiled stylesheet loaded by the page
├── js/
│   └── app.js          # Empty starter for your JavaScript implementation
├── package.json
└── README.md
```

## JavaScript integration points

Use the stable IDs and `data-*` attributes in `index.html` to wire up the controls. Important hooks include `#preview-card`, `#border-radius-control`, `#padding-control`, `#opacity-control`, `#background-color-control`, `#generated-css-lines`, `#copy-css-button`, `#reset-controls-button`, and the `data-tab`, `data-panel`, `data-color`, and `data-viewport` attributes.

## License

MIT. See [LICENSE](LICENSE).
