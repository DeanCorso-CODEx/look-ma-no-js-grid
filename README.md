# No-JS Birthday GIFt Site 🎁

✨ **Live Demo:** [Check out the final result here!](https://look-ma-no-js-grid.mihail-andrei-05.workers.dev/) ✨

This project started as a standard module assignment on Scrimba ("Build a Birthday Website"), but I decided to push the constraints of the initial design to see how far I could take a purely HTML/CSS architecture without relying on JavaScript. 

The core idea was to shift the user experience from a simple linear scroll to an interactive "Advent Calendar" style reveal.

## The Evolution of the Layout

The original codebase provided a basic single-column layout using basic Flexbox. The interactivity was limited to the CSS `:hover` pseudo-class, meaning the GIF "gifts" would close as soon as the cursor left the element. 

To make the project feel more like a modern web application, I implemented three major structural changes:

### 1. From Flexbox to CSS Grid
Instead of a long, monotonous vertical scroll, I refactored the layout engine to use CSS Grid (`grid-template-columns: repeat(2, 1fr)`). This allowed the gifts to sit side-by-side on larger screens, naturally creating the visual grid of an Advent calendar. The final "cheers" gift was set to span the entire column (`grid-column: 1 / -1`) to act as a definitive conclusion to the page.

### 2. The "CSS Checkbox Hack" for State Management
The biggest challenge was the interaction mechanic. I wanted the user to click a gift to open it, and for it to *stay open* permanently, revealing the meme underneath. 

Normally, saving state in the DOM requires JavaScript. To bypass this, I utilized the **"CSS Checkbox Hack"**. By pairing a hidden `<input type="checkbox">` with a `<label>` that wraps the gift image, a click on the image triggers the `:checked` state in CSS. This allowed me to swap the `background-image` permanently based purely on user interaction, achieving JS-like behavior with zero scripts.

### 3. Aspect Ratio Control
GIFs rarely have uniform dimensions. Some of the memes chosen were getting cropped awkwardly by the standard 1:1 aspect ratio when using `background-size: contain`. To fix the "letterbox" effect (ugly black bars), I updated the `.gift-img` container to use `background-size: cover`. This ensures every GIF fills the square frame perfectly without distorting the image.

## Design Identity: The "CSS Purist"

I strayed from the generic "happy birthday" theme and opted for a meta-joke about web development. The visual identity was overhauled into a dark "Cyber-Synthwave" theme (deep blues, neon cyan borders, and glassmorphism effects). 

The GIFs chosen represent the typical emotional rollercoaster of a developer—from the struggle of centering a div to the smug satisfaction of writing clean code. It’s essentially a satirical nod to the over-reliance on JavaScript for basic UI interactions, proving you can build engaging, state-driven interfaces using only cascading style sheets.

---

### Getting Started

Install the dependencies and run the project locally:

```bash
npm install
npm run dev

Head over to https://vitejs.dev/ to learn more about configuring vite
## About Scrimba

At Scrimba our goal is to create the best possible coding school at the cost of a gym membership! 💜
If we succeed with this, it will give anyone who wants to become a software developer a realistic shot at succeeding, regardless of where they live and the size of their wallets 🎉
The Fullstack Developer Path aims to teach you everything you need to become a Junior Developer, or you could go further with one of our advanced courses 🚀

- [Our courses](https://scrimba.com/courses)
- [The Frontend Career Path](https://scrimba.com/fullstack-path-c0fullstack)
- [Become a Scrimba Pro member](https://scrimba.com/pricing)

Happy Coding!
