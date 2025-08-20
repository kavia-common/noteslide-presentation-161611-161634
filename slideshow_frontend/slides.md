---
# Project-level configuration and theme
title: NoteSlide Presentation
theme: seriph
background: https://cover.sli.dev
info: |
  ## NoteSlide Presentation
  A Slidev presentation experience for your notes.

  Learn more at [Sli.dev](https://sli.dev)
class: text-center
drawings:
  persist: false

# Branding colors and CSS variables
css: unocss
layout: cover
highlighter: shiki
routerMode: history

# Default slide transition
transition: fade-out

# Enable MDC
mdc: true

# Color overrides and theme variables via CSS
style: |
  :root {
    --brand-primary: #1976D2;
    --brand-secondary: #424242;
    --brand-accent: #FFC107;
  }
  html, body {
    font-family: Inter, ui-sans-serif, system-ui, -apple-system, Segoe UI, Roboto, Helvetica, Arial, "Apple Color Emoji", "Segoe UI Emoji";
  }
  .brand-gradient {
    background-image: linear-gradient(45deg, var(--brand-primary), var(--brand-accent));
    -webkit-background-clip: text;
    background-clip: text;
    color: transparent;
  }
  .slidev-layout {
    /* modern minimal spacing */
    padding-top: 64px; /* leave room for fixed header */
  }
  .brand-header {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    height: 56px;
    display: flex;
    align-items: center;
    gap: 12px;
    padding: 0 16px;
    background: rgba(255,255,255,0.75);
    backdrop-filter: blur(8px);
    border-bottom: 1px solid rgba(0,0,0,0.06);
    z-index: 30;
  }
  .dark .brand-header {
    background: rgba(33,33,33,0.65);
    border-bottom-color: rgba(255,255,255,0.06);
  }
  .brand-logo {
    width: 28px; height: 28px; border-radius: 6px;
    background: var(--brand-primary);
    position: relative;
  }
  .brand-logo::after {
    content: "";
    position: absolute; inset: 6px;
    border-radius: 4px;
    background: var(--brand-accent);
  }
  .brand-title {
    font-weight: 600;
    letter-spacing: 0.2px;
  }
  .brand-controls {
    margin-left: auto;
    display: flex; gap: 8px;
  }
  .control-btn {
    border: 1px solid rgba(0,0,0,0.08);
    padding: 6px 10px; border-radius: 8px;
    background: white;
  }
  .dark .control-btn {
    background: #111214;
    border-color: rgba(255,255,255,0.08);
    color: #eaeaea;
  }

# Config: navigation bar always visible and toc sidebar
configs:
  themeConfig:
    colors:
      primary: "#1976D2"
      secondary: "#424242"
      accent: "#FFC107"
  canvasWidth: 1200
  aspectRatio: 16/9
  transition: slide-left
  controls: true
  port: 3000
  host: "0.0.0.0"
  # enable presenter style controls for next/prev
  shortcuts: true
  remote: true

---

# Welcome to NoteSlide

A modern, minimal Slidev deck styled for your notes.

<!-- Global Header -->
<div class="brand-header">
  <div class="brand-logo" aria-hidden="true" />
  <div class="brand-title">NoteSlide</div>
  <div class="brand-controls">
    <button class="control-btn" title="Previous" @click="$slidev.nav.prev()">
      <carbon:chevron-left /> Prev
    </button>
    <button class="control-btn" title="Next" @click="$slidev.nav.next()">
      Next <carbon:chevron-right />
    </button>
    <button class="control-btn" title="Toggle Dark" @click="$page.toggleDark()">
      <carbon:moon /> / <carbon:sun />
    </button>
    <button class="control-btn" title="Open in Editor" @click="$slidev.nav.openInEditor">
      <carbon:edit />
    </button>
  </div>
</div>

<!-- Slide Overview Sidebar (collapsible on mobile) -->
<div class="fixed left-0 top-16 bottom-0 w-52 md:w-64 p-3 overflow-auto hidden sm:block" style="border-right: 1px solid rgba(0,0,0,0.06);">
  <div class="text-xs uppercase opacity-60 mb-2">Slides</div>
  <Toc minDepth="1" maxDepth="2" />
</div>

<!-- Main content area with responsive padding to account for sidebar -->
<div class="sm:pl-64 pl-0">
  <div class="mt-6 text-sm opacity-70">
    Press Space or click Next for the next slide <carbon:arrow-right />
  </div>
</div>

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
transition: fade-out
---

transition: slide-up
---

# NoteSlide Features

<div v-motion :initial="{y: 20, opacity: 0}" :enter="{y:0, opacity:1, transition:{duration: 600}}">
  - 🗒️ <b>Display notes as individual slides</b> — write in Markdown with rich text (bold, italic, code).
  - ⌨️ <b>Next/Previous navigation</b> — keyboard arrows, space, or UI buttons.
  - 📱 <b>Responsive</b> — adaptive layout for desktop and mobile.
  - ✨ <b>Custom transitions</b> — slide, fade, and motion animations.
  - 🔤 <b>Rich text formatting</b> — lists, quotes, code, callouts.
  - 🌗 <b>Dark / Light</b> — quick toggle with brand-aware styling.
</div>

<div class="mt-6 text-4xl brand-gradient font-800">Focus on content. Present with style.</div>

> Tip: Use the sidebar to jump to any slide or the controls to step through.

<!--
You can have `style` tag in markdown to override the style for the current page.
Learn more: https://sli.dev/features/slide-scope-style
-->

<style>
h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
}
</style>

<!--
Here is another comment.
-->

---
transition: slide-up
level: 2
---

# Navigation

Hover on the bottom-left corner to see the navigation's controls panel, [learn more](https://sli.dev/guide/ui#navigation-bar)

On mobile:
- The sidebar is hidden to maximize stage space.
- Use on-screen Prev/Next controls in the header.

## Keyboard Shortcuts

|                                                     |                             |
| --------------------------------------------------- | --------------------------- |
| <kbd>right</kbd> / <kbd>space</kbd>                 | next animation or slide     |
| <kbd>left</kbd>  / <kbd>shift</kbd><kbd>space</kbd> | previous animation or slide |
| <kbd>up</kbd>                                       | previous slide              |
| <kbd>down</kbd>                                     | next slide                  |

<!-- https://sli.dev/guide/animations.html#click-animation -->
<img
  v-click
  class="absolute -bottom-9 -left-7 w-80 opacity-50"
  src="https://sli.dev/assets/arrow-bottom-left.svg"
  alt=""
/>
<p v-after class="absolute bottom-23 left-45 opacity-30 transform -rotate-10">Here!</p>

---
layout: two-cols
layoutClass: gap-16
---

# Table of contents

You can use the `Toc` component to generate a table of contents for your slides:

```html
<Toc minDepth="1" maxDepth="1" />
```

The title will be inferred from your slide content, or you can override it with `title` and `level` in your frontmatter.

::right::

<Toc text-sm minDepth="1" maxDepth="2" />

---
layout: image-right
image: https://cover.sli.dev
---

# Code and Rich Text

Use code snippets with highlighting and motion.

```ts {all|3|4-6|all} twoslash
import { computed, ref } from 'vue'
const count = ref(0)
const doubled = computed(() => count.value * 2)
console.log(doubled.value)
```

- List items support <i>italic</i>, <b>bold</b>, and <code>inline code</code>.
- Links: [Slidev Docs](https://sli.dev)
- Callout:
  > Minimal UI. Brand colors. Smooth transitions.

<arrow v-click="[3]" x1="350" y1="310" x2="195" y2="334" color="#1976D2" width="2" arrowSize="1" />

<<< @/snippets/external.ts#snippet

<!--
Notes can also sync with clicks

[click] This will be highlighted after the first click

[click] Highlighted with `count = ref(0)`

[click:3] Last click (skip two clicks)
-->

---
level: 2
---

# Shiki Magic Move

Powered by [shiki-magic-move](https://shiki-magic-move.netlify.app/), Slidev supports animations across multiple code snippets.

Add multiple code blocks and wrap them with <code>````md magic-move</code> (four backticks) to enable the magic move. For example:

````md magic-move {lines: true}
```ts {*|2|*}
// step 1
const author = reactive({
  name: 'John Doe',
  books: [
    'Vue 2 - Advanced Guide',
    'Vue 3 - Basic Guide',
    'Vue 4 - The Mystery'
  ]
})
```

```ts {*|1-2|3-4|3-4,8}
// step 2
export default {
  data() {
    return {
      author: {
        name: 'John Doe',
        books: [
          'Vue 2 - Advanced Guide',
          'Vue 3 - Basic Guide',
          'Vue 4 - The Mystery'
        ]
      }
    }
  }
}
```

```ts
// step 3
export default {
  data: () => ({
    author: {
      name: 'John Doe',
      books: [
        'Vue 2 - Advanced Guide',
        'Vue 3 - Basic Guide',
        'Vue 4 - The Mystery'
      ]
    }
  })
}
```

Non-code blocks are ignored.

```vue
<!-- step 4 -->
<script setup>
const author = {
  name: 'John Doe',
  books: [
    'Vue 2 - Advanced Guide',
    'Vue 3 - Basic Guide',
    'Vue 4 - The Mystery'
  ]
}
</script>
```
````

---

# Components

<div grid="~ cols-2 gap-4">
<div>

You can use Vue components directly inside your slides.

We have provided a few built-in components like `<Tweet/>` and `<Youtube/>` that you can use directly. And adding your custom components is also super easy.

```html
<Counter :count="10" />
```

<!-- ./components/Counter.vue -->
<Counter :count="10" m="t-4" />

Check out [the guides](https://sli.dev/builtin/components.html) for more.

</div>
<div>

```html
<Tweet id="1390115482657726468" />
```

<Tweet id="1390115482657726468" scale="0.65" />

</div>
</div>

<!--
Presenter note with **bold**, *italic*, and ~~striked~~ text.

Also, HTML elements are valid:
<div class="flex w-full">
  <span style="flex-grow: 1;">Left content</span>
  <span>Right content</span>
</div>
-->

---
class: px-20
---

# Themes

Slidev comes with powerful theming support. Themes can provide styles, layouts, components, or even configurations for tools. Switching between themes by just **one edit** in your frontmatter:

<div grid="~ cols-2 gap-2" m="t-2">

```yaml
---
theme: default
---
```

```yaml
---
theme: seriph
---
```

<img border="rounded" src="https://github.com/slidevjs/themes/blob/main/screenshots/theme-default/01.png?raw=true" alt="">

<img border="rounded" src="https://github.com/slidevjs/themes/blob/main/screenshots/theme-seriph/01.png?raw=true" alt="">

</div>

Read more about [How to use a theme](https://sli.dev/guide/theme-addon#use-theme) and
check out the [Awesome Themes Gallery](https://sli.dev/resources/theme-gallery).

---

# Clicks Animations

You can add `v-click` to elements to add a click animation.

<div v-click>

This shows up when you click the slide:

```html
<div v-click>This shows up when you click the slide.</div>
```

</div>

<br>

<v-click>

The <span v-mark.red="3"><code>v-mark</code> directive</span>
also allows you to add
<span v-mark.circle.orange="4">inline marks</span>
, powered by [Rough Notation](https://roughnotation.com/):

```html
<span v-mark.underline.orange>inline markers</span>
```

</v-click>

<div mt-20 v-click>

[Learn more](https://sli.dev/guide/animations#click-animation)

</div>

---

# Motions

Motion animations are powered by [@vueuse/motion](https://motion.vueuse.org/), triggered by `v-motion` directive.

```html
<div
  v-motion
  :initial="{ x: -80 }"
  :enter="{ x: 0 }"
  :click-3="{ x: 80 }"
  :leave="{ x: 1000 }"
>
  Slidev
</div>
```

<div class="w-60 relative">
  <div class="relative w-40 h-40">
    <img
      v-motion
      :initial="{ x: 800, y: -100, scale: 1.5, rotate: -50 }"
      :enter="final"
      class="absolute inset-0"
      src="https://sli.dev/logo-square.png"
      alt=""
    />
    <img
      v-motion
      :initial="{ y: 500, x: -100, scale: 2 }"
      :enter="final"
      class="absolute inset-0"
      src="https://sli.dev/logo-circle.png"
      alt=""
    />
    <img
      v-motion
      :initial="{ x: 600, y: 400, scale: 2, rotate: 100 }"
      :enter="final"
      class="absolute inset-0"
      src="https://sli.dev/logo-triangle.png"
      alt=""
    />
  </div>

  <div
    class="text-5xl absolute top-14 left-40 text-[#2B90B6] -z-1"
    v-motion
    :initial="{ x: -80, opacity: 0}"
    :enter="{ x: 0, opacity: 1, transition: { delay: 2000, duration: 1000 } }">
    Slidev
  </div>
</div>

<!-- vue script setup scripts can be directly used in markdown, and will only affects current page -->
<script setup lang="ts">
const final = {
  x: 0,
  y: 0,
  rotate: 0,
  scale: 1,
  transition: {
    type: 'spring',
    damping: 10,
    stiffness: 20,
    mass: 2
  }
}
</script>

<div
  v-motion
  :initial="{ x:35, y: 30, opacity: 0}"
  :enter="{ y: 0, opacity: 1, transition: { delay: 3500 } }">

[Learn more](https://sli.dev/guide/animations.html#motion)

</div>

---

# LaTeX

LaTeX is supported out-of-box. Powered by [KaTeX](https://katex.org/).

<div h-3 />

Inline $\sqrt{3x-1}+(1+x)^2$

Block
$$ {1|3|all}
\begin{aligned}
\nabla \cdot \vec{E} &= \frac{\rho}{\varepsilon_0} \\
\nabla \cdot \vec{B} &= 0 \\
\nabla \times \vec{E} &= -\frac{\partial\vec{B}}{\partial t} \\
\nabla \times \vec{B} &= \mu_0\vec{J} + \mu_0\varepsilon_0\frac{\partial\vec{E}}{\partial t}
\end{aligned}
$$

[Learn more](https://sli.dev/features/latex)

---

# Diagrams

You can create diagrams / graphs from textual descriptions, directly in your Markdown.

<div class="grid grid-cols-4 gap-5 pt-4 -mb-6">

```mermaid {scale: 0.5, alt: 'A simple sequence diagram'}
sequenceDiagram
    Alice->John: Hello John, how are you?
    Note over Alice,John: A typical interaction
```

```mermaid {theme: 'neutral', scale: 0.8}
graph TD
B[Text] --> C{Decision}
C -->|One| D[Result 1]
C -->|Two| E[Result 2]
```

```mermaid
mindmap
  root((mindmap))
    Origins
      Long history
      ::icon(fa fa-book)
      Popularisation
        British popular psychology author Tony Buzan
    Research
      On effectiveness<br/>and features
      On Automatic creation
        Uses
            Creative techniques
            Strategic planning
            Argument mapping
    Tools
      Pen and paper
      Mermaid
```

```plantuml {scale: 0.7}
@startuml

package "Some Group" {
  HTTP - [First Component]
  [Another Component]
}

node "Other Groups" {
  FTP - [Second Component]
  [First Component] --> FTP
}

cloud {
  [Example 1]
}

database "MySql" {
  folder "This is my folder" {
    [Folder 3]
  }
  frame "Foo" {
    [Frame 4]
  }
}

[Another Component] --> [Example 1]
[Example 1] --> [Folder 3]
[Folder 3] --> [Frame 4]

@enduml
```

</div>

Learn more: [Mermaid Diagrams](https://sli.dev/features/mermaid) and [PlantUML Diagrams](https://sli.dev/features/plantuml)

---
foo: bar
dragPos:
  square: 691,32,167,_,-16
---

# Draggable Elements

Double-click on the draggable elements to edit their positions.

<br>

###### Directive Usage

```md
<img v-drag="'square'" src="https://sli.dev/logo.png">
```

<br>

###### Component Usage

```md
<v-drag text-3xl>
  <div class="i-carbon:arrow-up" />
  Use the `v-drag` component to have a draggable container!
</v-drag>
```

<v-drag pos="663,206,261,_,-15">
  <div text-center text-3xl border border-main rounded>
    Double-click me!
  </div>
</v-drag>

<img v-drag="'square'" src="https://sli.dev/logo.png">

###### Draggable Arrow

```md
<v-drag-arrow two-way />
```

<v-drag-arrow pos="67,452,253,46" two-way op70 />

---
src: ./pages/imported-slides.md
hide: false
---

---

# Monaco Editor

Slidev provides built-in Monaco Editor support.

Add `{monaco}` to the code block to turn it into an editor:

```ts {monaco}
import { ref } from 'vue'
import { emptyArray } from './external'

const arr = ref(emptyArray(10))
```

Use `{monaco-run}` to create an editor that can execute the code directly in the slide:

```ts {monaco-run}
import { version } from 'vue'
import { emptyArray, sayHello } from './external'

sayHello()
console.log(`vue ${version}`)
console.log(emptyArray<number>(10).reduce(fib => [...fib, fib.at(-1)! + fib.at(-2)!], [1, 1]))
```

---
layout: center
class: text-center
---

# Learn More

[Documentation](https://sli.dev) · [GitHub](https://github.com/slidevjs/slidev) · [Showcases](https://sli.dev/resources/showcases)

<PoweredBySlidev mt-10 />
