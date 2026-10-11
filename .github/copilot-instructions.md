# Copilot instructions

## Project structure and architecture

- This is a dependency-free browser quiz implemented entirely in the root `index.html`. The document contains the markup, CSS, question data, and interaction logic; there is no build step or server requirement. Open the file directly in a browser to run it.
- The `questions` array is the quiz content source. `renderQuestion()` creates the answer buttons from the current item, `chooseAnswer()` handles scoring and feedback, `showResults()` renders the completion screen, and `restart()` resets the quiz.
- CSS custom properties in `:root` define the light palette; `@media (prefers-color-scheme: dark)` overrides them for dark mode. Keep shared UI colors theme-aware through these variables.

## Commands and checks

- There are no build, test, or lint commands configured in this repository.
- To check UI or interaction changes, open `index.html` directly in a browser and exercise answer selection, progression, feedback, results, restart, and keyboard focus. No local server is needed.

## Project-specific conventions

- Keep the app self-contained in `index.html`; do not add a framework, package manager, external asset, or runtime dependency without a requirement to change the standalone-file constraint.
- Keep question wording and answer options in the `questions` data array rather than embedding per-question markup. The `answer` value is a zero-based index into that item's `choices`.
- Use native `<button>` elements for answer and navigation controls. Preserve the current focus handoffs between answer, next question, and results, and keep feedback/results announced with the existing live regions.
- Preserve the dark and light theme behavior, responsive narrow-column layout, and `prefers-reduced-motion` handling when changing styles or animations.
