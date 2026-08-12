# quiz-cli

An interactive command-line quiz game for learning JavaScript and general programming concepts.

`quiz-cli` lets you choose a question category, decide how many questions to play, answer multiple-choice prompts in the terminal, and review your results at the end with helpful explanations for incorrect answers.

## Features

- Interactive terminal-based quiz experience
- Category selection before starting a game
- Adjustable question count per round
- Shuffled questions for a fresh experience each run
- Real-time score tracking and progress display
- Final results summary with answer review
- Replay prompt for quick retry sessions
- Colorized output for a more polished CLI experience
- Clean error handling and graceful readline shutdown

## Tech Stack

- **Node.js** v18+
- **ES Modules** (`type: module`)
- **Built-in `readline`** for terminal input
- **Native Node test runner** (`node --test`)
- **No external dependencies**

## Prerequisites

- **Node.js 18.0.0 or newer**
- **npm** (bundled with Node.js)

You can verify your version with:

```bash
node --version
npm --version
```

## Installation

1. Clone the repository:

```bash
git clone <repository-url>
cd quiz-cli
```

2. Install dependencies:

```bash
npm install
```

> This project does not use external packages, so `npm install` mainly prepares the project for standard Node workflows.

## Usage

### Start the quiz

```bash
npm start
```

Or run the entry point directly:

```bash
node index.js
```

### What happens when you launch it

1. A welcome banner is displayed
2. You select a quiz category
3. You choose how many questions to answer
4. The quiz begins and tracks your progress
5. Your final score is shown
6. Incorrect answers are reviewed with explanations
7. You can choose to play again

## Scripts

Available npm scripts from `package.json`:

```bash
npm start   # Runs the quiz CLI
npm test    # Runs the test suite using node --test
```

## Project Structure

```text
.
├── data/
│   └── questions.json
├── index.js
├── package.json
└── src/
    ├── colors.js
    ├── input.js
    └── quiz.js
```

### File overview

- **`index.js`** — CLI entry point; loads questions, handles menu flow, runs the quiz loop, prints results, and manages replay.
- **`src/input.js`** — Reusable readline helpers for prompts, selection, confirmation, and pause interactions.
- **`src/quiz.js`** — `Quiz` class that shuffles questions, tracks answers and score, shows progress, and renders results.
- **`src/colors.js`** — ANSI color/style utilities for success, error, warning, info, and highlight output.
- **`data/questions.json`** — Question bank organized by category.

## Data Format

The quiz questions live in `data/questions.json`.

Each question set includes categories such as:

- **JavaScript Basics**
- **Node.js Fundamentals**
- **General Programming**

Questions are multiple choice and include explanations so players can learn from mistakes and reinforce correct answers.

### Extending the question bank

To add more content:

1. Open `data/questions.json`
2. Add a new category or more questions to an existing one
3. Keep the structure consistent with the current question format
4. Include:
   - a category name
   - the question prompt
   - answer choices
   - the correct answer
   - an explanation

## Extending the Quiz

This project is intentionally small and easy to grow. A few good ways to extend it:

- Add more categories, such as:
  - HTML/CSS fundamentals
  - React basics
  - Git and GitHub
  - Algorithms and data structures
- Add difficulty levels
- Add timed questions
- Track high scores across sessions
- Support importing questions from additional JSON files
- Add true/false or multi-select question types
- Improve test coverage for quiz logic and input helpers

## Notes

- The project is designed for Node.js terminals and uses ANSI colors for readable output.
- If your terminal does not support colors well, output may appear plain but still remains fully usable.
- Because the quiz uses built-in Node APIs only, it is lightweight and easy to run anywhere Node.js 18+ is available.

## License

MIT

## Thanks for trying it out

Have fun learning JavaScript one question at a time!
