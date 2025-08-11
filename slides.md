---
theme: apple-basic
background: https://cover.sli.dev
title: Diving into the Toplayer; Where Dialogs, Popovers, and Modals Live
info: |
  ## Diving into the Toplayer: Where Dialogs, Popovers, and Modals Live
  A presentation about the top layer of the web, focusing on dialogs, popovers, and modals. Learn how to effectively use these components to enhance user experience and accessibility.
drawings:
  persist: false
transition: fade-out
mdc: true
---

<div class="particles">
    <div class="particle"></div>
    <div class="particle"></div>
    <div class="particle"></div>
    <div class="particle"></div>
</div>

<div class="floating-elements">
    <div class="layer-element layer-1"></div>
    <div class="layer-element layer-2"></div>
    <div class="layer-element layer-3"></div>
    <div class="layer-element toplayer-element"></div>
</div>

<div class="mountains"></div>

<div class="code-snippet">
&lt;dialog&gt;<br>
&nbsp;&nbsp;/* I live in the toplayer 👋🏼 */<br>
&lt;/dialog&gt;
    </div>

<div class="slide-container mt-30!"><h1 class="main-title">Diving into the <span class="highlight">Toplayer</span></h1><p class="subtitle">Where <span class="code">
&lt;dialog&gt;
    </span>s, <span class="code">
&lbrack;popover&rbrack;
    </span>s, and Modals Live</p>
    <div class="conference-info">UtahJS Conference</div>
    <time class="date">September 12, 2025</time>
    <div class="location">Tim Damen</div>
</div>

<style>
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
    }

    body {
        font-family: 'SF Pro Display', -apple-system, BlinkMacSystemFont, 'Segoe UI', system-ui, sans-serif;
        height: 100vh;
        overflow: hidden;
        background: linear-gradient(135deg,
            #2d3e2f 0%,
            #4a5d3a 25%,
            #6b4423 50%,
            #8b5a3c 75%,
            #5a4a3a 100%);
        display: flex;
        align-items: center;
        justify-content: center;
        position: relative;
    }

    .slide-container {
        text-align: center;
        color: white;
        z-index: 10;
        position: relative;
    }

    .main-title {
        font-size: 4.5rem;
        font-weight: 800;
        margin-bottom: 1rem;
        text-shadow: 0 4px 20px rgba(0,0,0,0.3);
        line-height: 1.1;
        letter-spacing: -0.02em;
    }

    .highlight {
        background: linear-gradient(45deg, #ffd700, #ffed4a);
        -webkit-background-clip: text;
        background-clip: text;
        -webkit-text-fill-color: transparent;
        display: inline-block;
        animation: glow 2s ease-in-out infinite alternate;
    }

    @keyframes glow {
        from {
            filter: drop-shadow(0 0 10px rgba(255, 215, 0, 0.5));
        }
        to {
            filter: drop-shadow(0 0 20px rgba(255, 215, 0, 0.8));
        }
    }

    .subtitle {
        font-size: 1.8rem;
        font-weight: 400;
        margin-bottom: 3rem;
        opacity: 0.9;
        text-shadow: 0 2px 10px rgba(0,0,0,0.2);
    }

    .conference-info {
        font-size: 1.3rem;
        opacity: 0.8;
    }

    .location {
        font-size: 1.1rem;
        opacity: 0.8;
    }

    .date {
        font-size: 1.1rem;
        opacity: 0.8;
    }

    /* Floating layer elements to represent the toplayer concept */
    .floating-elements {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        pointer-events: none;
        overflow: hidden;
    }

    .layer-element {
        position: absolute;
        border-radius: 12px;
        backdrop-filter: blur(10px);
        border: 1px solid rgba(255,255,255,0.2);
        animation: float 6s ease-in-out infinite;
    }

    .layer-1 {
        width: 200px;
        height: 120px;
        background: rgba(255,255,255,0.1);
        top: 10%;
        left: 15%;
        animation-delay: 0s;
        z-index: 1;
    }

    .layer-2 {
        width: 180px;
        height: 100px;
        background: rgba(255,255,255,0.15);
        top: 10%;
        right: 20%;
        animation-delay: 1s;
        z-index: 2;
    }

    .layer-3 {
        width: 150px;
        height: 90px;
        background: rgba(255,255,255,0.2);
        bottom: 10%;
        left: 20%;
        animation-delay: 2s;
        z-index: 3;
    }

    .toplayer-element {
        width: 160px;
        height: 100px;
        background: rgba(255, 215, 0, 0.3);
        border: 2px solid rgba(255, 215, 0, 0.5);
        top: 2%;
        right: 15%;
        animation: floatTop 4s ease-in-out infinite;
        box-shadow: 0 0 30px rgba(255, 215, 0, 0.3);
        z-index: 999999; /* Toplayer! */
    }

    @keyframes float {
        0%, 100% {
            transform: translateY(0) rotate(0deg);
            opacity: 0.3;
        }
        50% {
            transform: translateY(-20px) rotate(2deg);
            opacity: 0.7;
        }
    }

    @keyframes floatTop {
        0%, 100% {
            transform: translateY(0) scale(1);
            box-shadow: 0 0 30px rgba(255, 215, 0, 0.3);
        }
        50% {
            transform: translateY(-30px) scale(1.1);
            box-shadow: 0 0 50px rgba(255, 215, 0, 0.6);
        }
    }

    /* Mountain silhouette for Utah theming */
    .mountains {
        position: absolute;
        bottom: 0;
        left: 0;
        width: 100%;
        height: 200px;
        background: linear-gradient(to top,
            rgba(0,0,0,0.4) 0%,
            rgba(0,0,0,0.7) 50%,
            transparent 100%);
        clip-path: polygon(
            0% 100%,
            15% 60%,
            25% 80%,
            35% 40%,
            45% 70%,
            55% 30%,
            65% 65%,
            75% 45%,
            85% 75%,
            100% 50%,
            100% 100%
        );
        z-index: 1;
    }

    /* Code snippet decoration */
    .code {
        display: inline-block;
        background: rgba(0,0,0,0.4);
        color:rgb(247, 242, 242);
        padding: 0.5rem;
        border-radius: 8px;
        font-family: 'SF Mono', Monaco, monospace;
        backdrop-filter: blur(10px);
        border: 1px solid rgba(255,255,255,0.1);
        opacity: 1;
    }
    .code-snippet {
        position: absolute;
        top: 60%;
        left: 8%;
        background: rgba(0,0,0,0.4);
        color: #00ff88;
        padding: 1rem;
        border-radius: 8px;
        font-family: 'SF Mono', Monaco, monospace;
        font-size: 0.9rem;
        backdrop-filter: blur(10px);
        border: 1px solid rgba(255,255,255,0.1);
        opacity: 1;
    }

    @keyframes fadeInOut {
        0%, 20%, 80%, 100% { opacity: 0.3; }
        40%, 60% { opacity: 0.8; }
    }

    /* Responsive design */
    @media (max-width: 768px) {
        .main-title {
            font-size: 3rem;
        }

        .subtitle {
            font-size: 1.4rem;
        }

        .layer-element {
            display: none;
        }
    }

    /* Subtle particle effect */
    .particles {
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        pointer-events: none;
    }

    .particle {
        position: absolute;
        width: 4px;
        height: 4px;
        background: rgba(255,255,255,0.6);
        border-radius: 50%;
        animation: particleFloat 10s linear infinite;
    }

    .particle:nth-child(1) { left: 20%; animation-delay: 0s; }
    .particle:nth-child(2) { left: 40%; animation-delay: 2s; }
    .particle:nth-child(3) { left: 60%; animation-delay: 4s; }
    .particle:nth-child(4) { left: 80%; animation-delay: 6s; }

    @keyframes particleFloat {
        0% {
            transform: translateY(100vh) scale(0);
            opacity: 0;
        }
        10% {
            opacity: 1;
            transform: scale(1);
        }
        90% {
            opacity: 1;
        }
        100% {
            transform: translateY(-100px) scale(0);
            opacity: 0;
        }
    }
</style>

---

<FirstOverlayIntro />

<style>
.slidev-layout{
padding: 0px;
}
</style>

---

<OverlayIntro />

<style>
.slidev-layout{
padding: 0px;
}
</style>

---

<Tweet id="1435827240286109702" scale="0.9" />


<BarBottom title="Diving into the Toplayer: Where Dialogs, Popovers, and Modals Live">
  <Item text="timdamen.io">
    <carbon:link />
  </Item>
  <Item text="Tim Damen">
    <carbon:logo-linkedin />
  </Item>
    <Item text="timdamen">
    <carbon:logo-github />
  </Item>
</BarBottom>

---

<SlidevVideo autoplay autoreset="slide" loop>
  <!-- Anything that can go in an HTML video element. -->
  <source src="/images/modalz.mov" type="video/mp4" />
  <p>
    Your browser does not support videos. You may download it
    <a href="/images/modalz.mov">here</a>.
  </p>
</SlidevVideo>

<BarBottom title="modalzmodalzmodalz.com">
  <Item text="timdamen.io">
    <carbon:link />
  </Item>
  <Item text="Tim Damen">
    <carbon:logo-linkedin />
  </Item>
    <Item text="timdamen">
    <carbon:logo-github />
  </Item>
</BarBottom>

---

<Youtube id="UMLgenmD2aY?start=133" width="100%" height="450px"/>

<BarBottom title="Diving into the Toplayer: Where Dialogs, Popovers, and Modals Live">
  <Item text="timdamen.io">
    <carbon:link />
  </Item>
  <Item text="Tim Damen">
    <carbon:logo-linkedin />
  </Item>
    <Item text="timdamen">
    <carbon:logo-github />
  </Item>
</BarBottom>

---
layout: image-right
image: /images/Tim-2.jpeg
---

# Tim Damen

<br>
<span class="text-2xl">🧑‍💻</span> Front-end Developer @ ABN ARMO

<span class="text-2xl">♿️</span> Accessibility Lead & Advocate

<span class="text-2xl">🎙️</span> Podcaster @ focustrap

<span class="text-2xl">🌸</span> Husband and proud father of a daughter

<span class="text-2xl">🏔️</span> Passionate about sports and outdoor adventures

<BarBottom title="keyboard accessibility & focus">
  <Item text="timdamen.io">
    <carbon:link />
  </Item>
  <Item text="Tim Damen">
    <carbon:logo-linkedin />
  </Item>
    <Item text="timdamen">
    <carbon:logo-github />
  </Item>
</BarBottom>

---
layout: image
image: /images/Tim-2.jpeg
---

---
layout: image
image: /images/lowlands.jpeg
---

---
layout: center
---

# We'll focus on the <span class="font-italic" v-mark.underline>What</span>, <span class="font-italic" v-mark.underline>Why</span> and <span class="font-italic" v-mark.underline>How</span> of content that overlaps content

<br>

With the `<dialog>` element and the `[popover]` attribute

<style>
.slidev-layout{
width: 800px;
margin: auto;
text-align: center;
}
</style>

---
layout: center
---

# `<dialog>`

HTML element - a native dialog element that can be used to create a <span class="font-italic" v-mark.underline>modal</span> dialog or a <span class="font-italic" v-mark.underline>non-modal</span> dialog.

<v-click>

- Supported by all major browsers
    - 2014: Chrome v37
    - 2022: Firefox 98
    - 2022: Safari 15.4

</v-click>

<v-click>

- Good accessibility support
    - 2014-2021: "[The a11y community says nope](https://www.tpgi.com/the-current-state-of-modal-dialog-accessibility/)"
    - 2022: "Universal browser support... but still wait"
    - 2023: "[Use the dialog element (reasonably) by Scott ohara](https://www.scottohara.me/blog/2023/01/26/use-the-dialog-element.html)"

</v-click>

<BarBottom title="developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/dialog">
  <Item text="timdamen.io">
    <carbon:link />
  </Item>
  <Item text="Tim Damen">
    <carbon:logo-linkedin />
  </Item>
    <Item text="timdamen">
    <carbon:logo-github />
  </Item>
</BarBottom>

---
layout: center
---

# `[popover]`

HTML attribute - API in HTML that allows you to create popovers, tooltips, and other overlay content.

<v-click>

- Supported by all major browsers
  - May 2023: Chrome v114
  - Sep 2023: Safari v17
  - Apr 2024: Firefox v125

</v-click>

<v-click>

- Accessibility was baked in from the start
- [Proposed by the Open UI group](https://open-ui.org/components/popover.research.explainer/)

</v-click>

<BarBottom title="developer.mozilla.org/en-US/docs/Web/API/Popover_API">
  <Item text="timdamen.io">
    <carbon:link />
  </Item>
  <Item text="Tim Damen">
    <carbon:logo-linkedin />
  </Item>
    <Item text="timdamen">
    <carbon:logo-github />
  </Item>
</BarBottom>

---
layout: center
---

# Non-modal dialog

<img src="/images/non-modal-dialog.png" alt="example of a non modal dialog">

<style>
.slidev-layout{
width: 700px;
margin: auto;
text-align: center;
}
</style>

---
layout: center
---

# Popover

<img src="/images/popover.png" alt="example of a popover">

<style>
.slidev-layout{
width: 700px;
margin: auto;
text-align: center;
}
</style>

---
layout: center
---

# Modal + Popover

<img src="/images/modal-popover.png" alt="example of a popover">

<style>
.slidev-layout{
width: 700px;
margin: auto;
text-align: center;
}
</style>

---
layout: center
---

# With `z-index` you can stack elements

<SlidevVideo autoplay autoreset="slide" loop>
  <!-- Anything that can go in an HTML video element. -->
  <source src="/images/zindex.mov" type="video/mp4" />
  <p>
    Your browser does not support videos. You may download it
    <a href="/images/zindex.mov">here</a>.
  </p>
</SlidevVideo>

<BarBottom title="developer.mozilla.org/en-US/docs/Web/CSS/z-index">
  <Item text="timdamen.io">
    <carbon:link />
  </Item>
  <Item text="Tim Damen">
    <carbon:logo-linkedin />
  </Item>
    <Item text="timdamen">
    <carbon:logo-github />
  </Item>
</BarBottom>

---
layout: center
---

# What is the maximum `z-index` value?

<div v-click.hide>

```css
z-index: ???;
```
</div>
<div v-after>

```css
z-index: 2147483647; /* 2^31 - 1 */
```

</div>
<div v-click>

<SpeakButton />

</div>

<div v-click>

`2147483647`, the largest number that can be stored in a `32-bit` signed integer 🤓

</div>

<BarBottom title="stackoverflow.com/questions/491052/minimum-and-maximum-value-of-z-index/25461690">
  <Item text="timdamen.io">
    <carbon:link />
  </Item>
  <Item text="Tim Damen">
    <carbon:logo-linkedin />
  </Item>
    <Item text="timdamen">
    <carbon:logo-github />
  </Item>
</BarBottom>

---
layout: image-right
image: /images/toplayer.png
---

# The `#top-layer` is above everything else, it has his own layer above the main document 

<BarBottom title="drafts.csswg.org./css-position-4/#top-layer">
  <Item text="timdamen.io">
    <carbon:link />
  </Item>
  <Item text="Tim Damen">
    <carbon:logo-linkedin />
  </Item>
    <Item text="timdamen">
    <carbon:logo-github />
  </Item>
</BarBottom>

---

<BrowserStackVisualization />

<style>
.slidev-layout{
padding: 0px;
}
</style>

---
layout: center
---

# <span v-mark.underline>`<dialog>`</span> vs `[popover]`

<style>
.slidev-layout{
width: 700px;
margin: auto;
text-align: center;
}
</style>

---
layout: two-cols
---

# What a `<dialog>` is

::right::

# An additional window that (temporarily) overlaps the main content of a web page

<BarBottom title="developer.mozilla.org/en-US/docs/Web/HTML/Reference/Elements/dialog">
  <Item text="timdamen.io">
    <carbon:link />
  </Item>
  <Item text="Tim Damen">
    <carbon:logo-linkedin />
  </Item>
    <Item text="timdamen">
    <carbon:logo-github />
  </Item>
</BarBottom>

---
layout: center
---

# Dialogs
<br>

Typically contain:
- Information
- Task
- Action

---

# `<dialog>`

## `show()` vs `showModal()`

<br>

```js
// Opens the dialog as a non-modal
Element.show(); 
```

```js
// Opens the dialog as a modal
Element.showModal(); 
```

<style>
code {
  font-size: 1.4rem;
}
</style>

<BarBottom title="https://www.erikkroes.nl/blog/the-universal-focus-state/">
  <Item text="timdamen.io">
    <carbon:link />
  </Item>
  <Item text="Tim Damen">
    <carbon:logo-linkedin />
  </Item>
    <Item text="timdamen">
    <carbon:logo-github />
  </Item>
</BarBottom>

---

# 

```html
<!-- dialog element -->
<dialog>
  ...
</dialog>
```

<br>

- `role="dialog"` is added automatically
- <kbd>Esc</kbd> to close
- Option to show as modal or non-modal
- Focus is trapped when opened as modal (`showModal()`)

<style>
code {
  font-size: 1.4rem;
}
</style>

<BarBottom title="https://www.erikkroes.nl/blog/the-universal-focus-state/">
  <Item text="timdamen.io">
    <carbon:link />
  </Item>
  <Item text="Tim Damen">
    <carbon:logo-linkedin />
  </Item>
    <Item text="timdamen">
    <carbon:logo-github />
  </Item>
</BarBottom>

---

# modal vs non-modal

<DialogDemo />

---
layout: center
---

# `<dialog>` vs <span v-mark.underline>`[popover]`</span>

<style>
.slidev-layout{
width: 700px;
margin: auto;
text-align: center;
}
</style>

---
layout: two-cols
---

# What a `[popover]` is

::right::

# A floating overlay that provides information or actions when triggered, appearing above the main content without blocking the user's workflow.

<br>

<v-click>

## "a popover 'pops'" - Tim Damen

</v-click>
---

# `[popover]`

## HTML attribute that can be applied to any element, it ads a set of behaviors to the element

```html
<div popover>...</div>
```

```html
<dialog popover>...</dialog>
```

<v-click>

Popover does not add a `role`. It addepts the role of the element it is applied to.

</v-click>

<v-click>

Depending on the popover type (default is `popover="auto"` ), it will add:

- light dismiss
- keyboard behavior (<kbd>Esc</kbd> to close)
- added to toplayer
- Closes other popovers when opened
    - (Usaually) displayed one at a time
    - (Usaually) displayed on hover or click

</v-click>

<style>
code {
  font-size: 1.4rem;
}
</style>

---

# `[popover]` positioning

<PopoverDemoPosition />

---
layout: image
image: /images/margin.png
---

---

# `[popover]` still has some positioning flaws
 
<br>

## But there is hope! You have got two options:

- Use a JS library for positioning like `floating-ui`
- Use CSS anchor()

<v-click>
CSS anchor() is not supported by all browsers yet 😒
</v-click>


---

<iframe height="500" style="width: 100%;" scrolling="no" title="position-try with flip keyword" src="https://codepen.io/una/embed/QWPvGRZ?default-tab=html%2Cresult" frameborder="no" loading="lazy" allowtransparency="true" allowfullscreen="true">
</iframe>

---

# popover="auto"

<PopoverDemo />

---

# "hint" and "manual"

<PopoverDemoHint />

---

<ToastDemo />

---

<ToplayerTimeline />

<style>
.slidev-page {
  overflow-y: auto !important;
}

.slidev-layout {
  padding: 0px;
}
</style>

---

# People who don't use a mouse, use focus styles to see where they are

Lorem Ipsum is simply dummy text of the printing and typesetting industry. [Lorem Ipsum](#) has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged.
<button>Submit</button>

<style>
.slidev-layout{
width: 800px;
margin: auto;
}

button {
  all: revert;
  display: block;
  background-color: black;
  color: white;
  margin-top:10px;
}

button {
    background-color: darkblue ;
  color: white;
border-style: solid;
border-color: orange;
  font-size: 120%;
  margin: 0.4rem;
}

input[type="checkbox"] {
  border: 3px solid white;
}

button:focus {
  outline: webkit-focus-ring-color auto 5px;
  outline-offset: 5px;
}

p {
  margin-top: 50px;
  max-width: 28rem;
}
</style>

<BarBottom title="keyboard accessibility & focus">
  <Item text="timdamen.io">
    <carbon:link />
  </Item>
  <Item text="Tim Damen">
    <carbon:logo-linkedin />
  </Item>
    <Item text="timdamen">
    <carbon:logo-github />
  </Item>
</BarBottom>

---

## layout: center

# Ask your self: is the tab order sensible?

(not to many tab stops)

<style>
.slidev-layout{
width: 800px;
margin: auto;
text-align: center;
}
</style>

---

layout: image
image: /images/sidewalk.jpg

---

<BarBottom title="keyboard accessibility & focus" class="bg-black">
  <Item text="timdamen.io">
    <carbon:link />
  </Item>
  <Item text="Tim Damen">
    <carbon:logo-linkedin />
  </Item>
    <Item text="timdamen">
    <carbon:logo-github />
  </Item>
</BarBottom>

---

layout: image
image: /images/remote.jpg

---

<BarBottom title="keyboard accessibility & focus" class="bg-black">
  <Item text="timdamen.io">
    <carbon:link />
  </Item>
  <Item text="Tim Damen">
    <carbon:logo-linkedin />
  </Item>
    <Item text="timdamen">
    <carbon:logo-github />
  </Item>
</BarBottom>

---

## layout: center

# Never remove or hide the <span>focus ring!</span>

<style>
span {
  border: 5px double white;
  padding: 0px 10px;
}
.slidev-layout{
width: 800px;
margin: auto;
}
</style>

---

layout: image
image: /images/steal-cursor.png

---

<BarBottom title="Laura Carvajal on stage at Fronteers conference 2018." class="bg-black">
  <Item text="timdamen.io">
    <carbon:link />
  </Item>
  <Item text="Tim Damen">
    <carbon:logo-linkedin />
  </Item>
    <Item text="timdamen">
    <carbon:logo-github />
  </Item>
</BarBottom>

---

## level: 2

# Basic keyboard navigation

How to navigate a website with the keyboard, [keyboard navigation](https://accessibleweb.com/question-answer/navigate-website-keyboard/)

| **Keyboard**                                        | **Action**                                                                                                |
| --------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| <kbd>Tab</kbd>                                      | move to next interactive element                                                                          |
| <kbd>Shift</kbd> + <kbd>Tab</kbd>                   | move to previous interactive element                                                                      |
| <kbd>Return</kbd>/<kbd>Enter</kbd>                  | activate elements (links, buttons, etc)                                                                   |
| <kbd>Spacebar</kbd>                                 | activates buttons, checkbox, selectbox (such as to pause/play videos, submit forms, etc)                  |
| <kbd>Esc</kbd>                                      | close opened content (modals, navigation menus, etc) or cancel current action                             |
| <kbd>←</kbd>/<kbd>↑</kbd>/<kbd>→</kbd>/<kbd>↓</kbd> | navigate within widgets (tablists, checkboxes within a disclosure button, etc) and navigate around a page |

<BarBottom title="keyboard accessibility & focus">
  <Item text="timdamen.io">
    <carbon:link />
  </Item>
  <Item text="Tim Damen">
    <carbon:logo-linkedin />
  </Item>
    <Item text="timdamen">
    <carbon:logo-github />
  </Item>
</BarBottom>

---

## layout: center

# Good focus styles

- Visible
- 3:1 contrast <span v-mark.underline>against adjacent colors</span>
- Consistent

<BarBottom title="keyboard accessibility & focus">
  <Item text="timdamen.io">
    <carbon:link />
  </Item>
  <Item text="Tim Damen">
    <carbon:logo-linkedin />
  </Item>
    <Item text="timdamen">
    <carbon:logo-github />
  </Item>
</BarBottom>

---

layout: two-cols
layoutClass: gap-16

---

# Oreo focus style

   <p class="white">
    This is a dark text on a white background. It contains <a href="#">a link on a white background</a> and serves as an excellent example.
    </p>

  <p class="gray">
      This is a dark text on a gray background. It contains <a href="#">a link on a gray background</a> and serves as an excellent example.
  </p>

  <p class="black">
      This is a light text on a black background. It contains <a href="#">a link on a black background</a> and serves as an excellent example.
  </p>

::right::

<div class="mt-50"></div>

```css
:focus {
  box-shadow: 0 0 0 0.25rem white;
  outline: 0.375rem double black;
  border-radius: 0.125rem;
}
```

<style>
  :focus {
  box-shadow: 0 0 0 .25rem white;
  outline: .375rem double black;
  border-radius: .125rem;
}

p {
  padding: 1rem;
  max-width: 20rem;
}

.white {
  background-color: white;
  color: black;
}

.gray {
  background-color: #757575;
}

.black {
  color: white;
  background-color: black;
}
.black a {
  color: #aaa;
}
</style>

<BarBottom title="https://www.erikkroes.nl/blog/the-universal-focus-state/">
  <Item text="timdamen.io">
    <carbon:link />
  </Item>
  <Item text="Tim Damen">
    <carbon:logo-linkedin />
  </Item>
    <Item text="timdamen">
    <carbon:logo-github />
  </Item>
</BarBottom>

---

## layout: center

# Only one thing on a given page can have <span>focus</span> at a time

<style>
.slidev-layout{
width: 750px;
margin: auto;
text-align: center;
}

span {
  border: 5px ridge white;
  padding: 0px 5px;
  line-height: 2;
}
</style>

---

## layout: center

# Interactive elements

`<button>`,`<a href>`,`<input>`,`<details>`,`<select>`

<BarBottom title="keyboard accessibility & focus">
  <Item text="timdamen.io">
    <carbon:link />
  </Item>
  <Item text="Tim Damen">
    <carbon:logo-linkedin />
  </Item>
    <Item text="timdamen">
    <carbon:logo-github />
  </Item>
</BarBottom>

---

## layout: center

# Let's try!

<br>

## `<button>` and `<a href>`

<button class="mr-4">button</button> [link](#)

## Color `<input type="color">`

<input type="color" value="#fd00ff">

<div class="mt-10"></div>

## `<radio>` and `<checkbox>`

<div class="bg-white text-black">
<fieldset>
  <legend>Do you like coffee?</legend>
  <div class="radio">
    <input type="radio" name="coffee" id="no" value="no"/>
    <label for="no">Nope</label>
    <input type="radio" name="coffee" id="yes" value="yes"/>
    <label for="yes">Yes</label>
    <input type="radio" name="coffee" id="love" value="love" />
    <label for="love">No, I LOVE it!</label>
  </div>
</fieldset>

<fieldset>
  <legend>Please send me</legend>
  <div class="checkbox">
    <input type="checkbox" name="snacks" id="snacks-pizza" value="pizza">
    <label for="snacks-pizza">Pizza</label>
    <input type="checkbox" name="snacks" id="snacks-cake" value="cake">
    <label for="snacks-cake">Cake</label>
    <input type="checkbox" name="snacks" id="snacks-ice-cream" value="ice-cream">
    <label for="snacks-ice-cream">Ice Cream</label>
  </div>
</fieldset>
</div>

<style>
:focus {
  box-shadow: 0 0 0 .25rem white;
  outline: .375rem double black;
  border-radius: .125rem;
}
button, select, a, label, fieldset, legend, input {
  all: revert;
}

button, input[type="color"] {
  margin-right: 1rem;
    background-color: black;
  color: white;
}

button {
    background-color: darkblue ;
  color: white;
border-style: solid;
border-color: orange;
  font-size: 120%;
  margin: 0.4rem;
}

a:active {
  color: red;
}
button:active {
  background-color: red;
}
</style>

---

## layout: center

# Debugging focused element

```js
document.addEventListener(
  "focus",
  function () {
    console.log("focused: ", document.activeElement);
  },
  true
);
```

<BarBottom title="keyboard accessibility & focus">
  <Item text="timdamen.io">
    <carbon:link />
  </Item>
  <Item text="Tim Damen">
    <carbon:logo-linkedin />
  </Item>
    <Item text="timdamen">
    <carbon:logo-github />
  </Item>
</BarBottom>

---

## layout: center

# Focus with JavaScript

```js
element.focus();
```

<BarBottom title="keyboard accessibility & focus">
  <Item text="timdamen.io">
    <carbon:link />
  </Item>
  <Item text="Tim Damen">
    <carbon:logo-linkedin />
  </Item>
    <Item text="timdamen">
    <carbon:logo-github />
  </Item>
</BarBottom>

---

layout: image-left
image: /images/itsatrap.png
backgroundSize: contain

---

# When do we need to trap focus?

- Within a modal window
- Within modal navigation
- In a full screen alert

<BarBottom title="keyboard accessibility & focus">
  <Item text="timdamen.io">
    <carbon:link />
  </Item>
  <Item text="Tim Damen">
    <carbon:logo-linkedin />
  </Item>
    <Item text="timdamen">
    <carbon:logo-github />
  </Item>
</BarBottom>

---

layout: image-left
image: /images/focustrapp.png
backgroundSize: contain

---

# How to trap focus within an element

```js
modal.show();
modal.trapFocus();
```

```html
<div
  id="dialog"
  role="dialog"
  tabindex="-1"
  hidden
  aria-labelledby="dialog-title"
>
  <form class="dialog-content">
    <h1 id="dialog-title">Name Entry</h1>

    <label for="within-dialog">Name</label>
    <input id="within-dialog" />

    <button type="button" id="close-dialog">Close</button>
    <button type="submit" id="save-dialog">Save</button>
  </form>
</div>
```

<BarBottom title="https://hidde.blog/using-javascript-to-trap-focus-in-an-element/">
  <Item text="timdamen.io">
    <carbon:link />
  </Item>
  <Item text="Tim Damen">
    <carbon:logo-linkedin />
  </Item>
    <Item text="timdamen">
    <carbon:logo-github />
  </Item>
</BarBottom>

---

## layout: center

# How to trap focus within an element (2)

```js
// method of the HTMLDialogElement
modal.showModal();
```

---

# Demo `modal.show()` vs `modal.showModal()`

- The modal should trap focus
- First focusable element should be focused
- Close with <kbd>Esc</kbd>
- When the modal is closed, focus should return to the element that opened the modal

<dialog id="modal1">
  <h1>Welcome!</h1>
  <p>Click Close or press esc to close modal</p>
  <form method="dialog" class="text-end">
    <button class="btn btn-primary mr-2">Submit</button>
    <button class="btn btn-primary">Close</button>
  </form>
</dialog>

<dialog id="modal2">
  <h1>Welcome!</h1>
  <p>Click Close or press esc to close modal</p>
  <form method="dialog" class="text-end">
    <button class="btn btn-primary mr-2">Submit</button>
    <button class="btn btn-primary">Close</button>
  </form>
</dialog>

<button onclick="modal1.show()" class="btn btn-primary">show()</button>
<button onclick="modal2.showModal()" class="btn btn-primary">ShowModal()</button>

<BarBottom title="keyboard accessibility & focus">
  <Item text="timdamen.io">
    <carbon:link />
  </Item>
  <Item text="Tim Damen">
    <carbon:logo-linkedin />
  </Item>
    <Item text="timdamen">
    <carbon:logo-github />
  </Item>
</BarBottom>

<style>
  dialog {
    all: revert;
  }
  button {
    all: revert;
    margin-right: 5px;
      background-color: black;
  color: white;
  }
  button, input[type="color"] {
    background-color: darkblue ;
  color: white;
border-style: solid;
border-color: orange;
  font-size: 120%;
  margin: 0.4rem;
}
  :focus {
  box-shadow: 0 0 0 .25rem white;
  outline: .375rem double black;
  border-radius: .125rem;
}
</style>

---

## layout: center

# HTML (`tabindex`) allows us to customise focus order

use this feature with caution!

<style>
.slidev-layout{
width: 800px;
margin: auto;
text-align: center;
}
</style>

---

layout: two-cols
layoutClass: gap-1

---

# What is the `tabindex` attribute?

<p>The <code>tabindex</code> attribute specifies the tab order of an element. It can have three different types of values:</p>

<dl>
  <dt><code>tabindex="0"</code></dt>
  <!-- <dd>Makes an element focusable via keyboard in the natural document order</dd> -->
  <dt class="font-semibold mt-4"><code>tabindex="-1"</code></dt>
  <!-- <dd>Makes an element programmatically focusable, but not via keyboard navigation</dd> -->
  <dt class="font-semibold mt-4"><code>tabindex="1+"</code> (positive values)</dt>
  <!-- <dd>Defines an explicit tab order (generally not recommended)</dd> -->
</dl>

<BarBottom title="keyboard accessibility & focus">
  <Item text="timdamen.io">
    <carbon:link />
  </Item>
  <Item text="Tim Damen">
    <carbon:logo-linkedin />
  </Item>
    <Item text="timdamen">
    <carbon:logo-github />
  </Item>
</BarBottom>

---

# Natural Tab Order

<div class="demo-box">
  <p>These elements are in their natural tab order (no <code>tabindex</code>):</p>
  <div class="container">
      <button>First Button</button>
      <a href="#">Link</a>
      <button>Second Button</button>
      <input type="text">
      <button>Third Button</button>
  </div>  
  <div class="tips positive">
      <p class="text-sm">Whenever possible, structure your HTML so that the natural tab order matches the logical reading order. This is the most accessible approach.</p>
  </div>
</div>

<style>
:focus {
  box-shadow: 0 0 0 .25rem white;
  outline: .375rem double black;
  border-radius: .125rem;
}
button, select, a, label, fieldset, legend, input {
  all: revert;
  margin-right: 1rem;
}

a {
color: white;
}

button, input[type="color"] {
  margin-right: 1rem;
    background-color: darkblue ;
  color: white;
}

a:active {
  color: red;
}
button:active {
  background-color: red;
}
</style>

<BarBottom title="keyboard accessibility & focus">
  <Item text="timdamen.io">
    <carbon:link />
  </Item>
  <Item text="Tim Damen">
    <carbon:logo-linkedin />
  </Item>
    <Item text="timdamen">
    <carbon:logo-github />
  </Item>
</BarBottom>

---

## Making Non-Interactive Elements Focusable

<div class="demo-box">
  <p>Regular divs are not focusable by default, but <code>tabindex="0"</code> makes them part of the tab sequence:</p>
    
  <div class="element border-2 border-red600 p1" tabindex="0">This div has <code>tabindex="0"</code> - It is now keyboard focusable</div>
  <div class="element border-2 border-green600 mt-2 p1" tabindex="0">Another div with <code>tabindex="0"</code></div>

<button>Regular button (naturally focusable)</button>

</div>

<style>
:focus {
  box-shadow: 0 0 0 .25rem white;
  outline: .375rem double black;
  border-radius: .125rem;
}
button, select, a, label, fieldset, legend, input {
  all: revert;
  margin-right: 1rem;
}

button, input[type="color"] {
  margin-right: 1rem;
    background-color: darkblue ;
  color: white;
}

a:active {
  color: red;
}
button:active {
  background-color: red;
}
</style>

<BarBottom title="keyboard accessibility & focus">
  <Item text="timdamen.io">
    <carbon:link />
  </Item>
  <Item text="Tim Damen">
    <carbon:logo-linkedin />
  </Item>
    <Item text="timdamen">
    <carbon:logo-github />
  </Item>
</BarBottom>

---

## Programmatic Focus with <code>tabindex="-1"</code>

<div class="demo-box">
  <p>Elements with <code>tabindex="-1"</code> can receive focus programmatically but are not in the tab order:</p>
    <a href="#">Link</a>
  <div class="element border-2 border-red600 p1" tabindex="-1">This div has <code>tabindex="-1"</code> - Not in tab order</div>
  <button onclick="document.querySelector('[tabindex=\'-1\']').focus()">Click to focus the element above</button>
<br>
<br>

Focus with with javascript

```js
element.focus();
```

<v-click>
  
  `tabindex="-1"` is useful for:
  <ul>
      <li>Custom widgets where you manage focus manually</li>
      <li>Off-screen content that needs to be focused programmatically</li>
      <li>Managing focus for elements that should only be focused under specific conditions</li>
  </ul>
</v-click>
</div>

<style>
:focus {
  box-shadow: 0 0 0 .25rem white;
  outline: .375rem double black;
  border-radius: .125rem;
}
button, select, a, label, fieldset, legend, input {
  all: revert;
  margin-right: 1rem;
}

button, input[type="color"] {
  margin-right: 1rem;
    background-color: darkblue ;
  color: white;
}

a {
color: white;
}

a:active {
  color: red;
}
button:active {
  background-color: red;
}
</style>

<BarBottom title="keyboard accessibility & focus">
  <Item text="timdamen.io">
    <carbon:link />
  </Item>
  <Item text="Tim Damen">
    <carbon:logo-linkedin />
  </Item>
    <Item text="timdamen">
    <carbon:logo-github />
  </Item>
</BarBottom>

---

## Positive Tabindex Values (Not Recommended)

<div class="demo-box">
    <p>Positive tabindex values create a custom tab order that overrides the document structure:</p>
    
  <div class="container">
    <button tabindex="3">Button with tabindex="3" (third)</button>
    <button tabindex="1">Button with tabindex="1" (first)</button>
    <button tabindex="2">Button with tabindex="2" (second)</button>
    <button>Button with no tabindex (fourth)</button>
  </div>
    
<v-click>
  <div class="tips negative mt-10">
      <h2>❌ Not Recommended</h2>
      <p>Using positive tabindex values is generally discouraged because:</p>
      <ul>
          <li>It creates a disconnect between visual and keyboard navigation orders</li>
          <li>It's difficult to maintain as your HTML changes</li>
          <li>It can create a confusing experience for keyboard and screen reader users</li>
          <li>It can lead to "tab traps" where users get stuck in a section</li>
      </ul>
  </div>
</v-click>
</div>

<style>
:focus {
  box-shadow: 0 0 0 .25rem white;
  outline: .375rem double black;
  border-radius: .125rem;
}
button, select, a, label, fieldset, legend, input {
  all: revert;
  margin-right: 1rem;
}

button, input[type="color"] {
    background-color: darkblue ;
  color: white;
border-style: solid;
border-color: orange;
  font-size: 120%;
  margin: 0.4rem;
}

a:active {
  color: red;
}
button:active {
  background-color: red;
}
</style>

<BarBottom title="keyboard accessibility & focus">
  <Item text="timdamen.io">
    <carbon:link />
  </Item>
  <Item text="Tim Damen">
    <carbon:logo-linkedin />
  </Item>
    <Item text="timdamen">
    <carbon:logo-github />
  </Item>
</BarBottom>

---

## layout: center

# Summary

- People using the web with a keyboard
- Shortcuts
- Interactive elements
- Focus rings
- Focus traps
- Tabindex

<BarBottom title="keyboard accessibility & focus">
  <Item text="timdamen.io">
    <carbon:link />
  </Item>
  <Item text="Tim Damen">
    <carbon:logo-linkedin />
  </Item>
    <Item text="timdamen">
    <carbon:logo-github />
  </Item>
</BarBottom>

---

## layout: center

# focustrap podcast

I'm hosting a podcast called "focustrap" where we discuss all things digital accessibility.

Check it out! [focustrap](https://focusring.io/podcast-focustrap) ❤️

<div class="flex justify-center gap-4 mt-10">
 <img src="/images/qr.png" alt="focustrap qr code" class="ml-10 size-50" />
  <img src="/images/latest-focustrap.png" alt="focustrap qr code" class="ml-10 max-w-[500px]" />
 
</div>

<BarBottom title="keyboard accessibility & focus">
  <Item text="timdamen.io">
    <carbon:link />
  </Item>
  <Item text="Tim Damen">
    <carbon:logo-linkedin />
  </Item>
    <Item text="timdamen">
    <carbon:logo-github />
  </Item>
</BarBottom>

---

## layout: center

# Thank you! 🙏

Let's stay in touch!

<div class="flex justify-start gap-4 mt-10">
<img src="/images/LQR.png" alt="linkedIn QR" class="ml-10 size-50 align-right" />
</div>

<BarBottom title=" ">
  <Item text="timdamen.io">
    <carbon:link />
  </Item>
  <Item text="Tim Damen">
    <carbon:logo-linkedin />
  </Item>
    <Item text="timdamen">
    <carbon:logo-github />
  </Item>
</BarBottom>
