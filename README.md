# Quiz CLI

An interactive command-line quiz game for learning JavaScript, Node.js fundamentals, and general programming concepts.

## Project Overview

Quiz CLI is a terminal-based learning app that lets users:

- choose a quiz category
- select how many questions to answer
- answer multiple-choice questions from a local JSON dataset
- receive immediate feedback after each answer
- review incorrect answers at the end of the quiz
- replay the game without restarting the program

The project is designed as a compact example of Node.js fundamentals, ES modules, file I/O, asynchronous input handling, and simple object-oriented design.

## Tools & Tech Stack

| Area | Technology |
| --- | --- |
| Runtime | Node.js >= 18 |
| Language | JavaScript (ES Modules) |
| CLI/Input | Built-in `readline` module |
| File I/O | `node:fs/promises` |
| Path Handling | `node:path`, `node:url` |
| Data Source | Local JSON file (`data/questions.json`) |
| Styling | ANSI escape codes for terminal colors |
| Testing | Node test runner (`node --test`) |

## Features

- Terminal-based interactive quiz flow
- Category-based question selection
- Question count selection per category
- Randomized question order
- Progress indicator for quiz completion
- Instant correct/incorrect feedback
- Explanations shown for each answer
- End-of-quiz score summary
- Review list of missed questions
- Replay support without leaving the app

## Project Structure

```text
.
├── index.js
├── package.json
├── data
│   └── questions.json
└── src
    ├── colors.js
    ├── input.js
    └── quiz.js
```

### Main Files

- `index.js` — application entry point; loads quiz data and runs the main loop
- `src/input.js` — readline helpers for prompts, selections, confirmations, and pauses
- `src/quiz.js` — quiz logic, scoring, progress, and results display
- `src/colors.js` — terminal color utilities
- `data/questions.json` — quiz categories, questions, answers, and explanations

## Prerequisites

- **Node.js 18 or newer**
- **npm** (bundled with Node.js)

No external npm dependencies are required.

## Setup Instructions

### 1) Clone the repository

```bash
git clone <repository-url>
cd test-app
```

### 2) Install dependencies

There are no production dependencies, but running install will prepare the project for standard Node workflows:

```bash
npm install
```

### 3) Environment variables

This application does not currently require environment variables.

If you add configuration later, create a `.env.example` file and document it here.

## Getting Started

### Run the application in development mode

```bash
npm start
```

This launches the CLI and walks you through:

1. choosing a category
2. selecting the number of questions
3. answering each question
4. reviewing your score and missed answers

### Run the test suite

```bash
npm test
```

This uses the Node.js built-in test runner.

### Build for production

There is no separate build step for this project. The app runs directly with Node.js.

To package or distribute it, use the entry point:

```bash
node index.js
```

## Usage Example

Example session flow:

```bash
$ npm start

Choose a category:
  1. JavaScript Basics
  2. Node.js Fundamentals
  3. General Programming

How many questions?
  1. All questions
  2. 3 questions
  3. 5 questions

Starting quiz...
Select your answer by entering the number.
```

During the quiz, answer by entering the option number shown on screen.

## Data Format

Quiz content is stored in `data/questions.json` using the following structure:

```json
{
  "categories": {
    "category-id": {
      "name": "Category Name",
      "questions": [
        {
          "question": "Question text",
          "options": ["A", "B", "C", "D"],
          "answer": 2,
          "explanation": "Why the answer is correct"
        }
      ]
    }
  }
}
```

## Implementation Notes

- The app uses ES module syntax (`import` / `export`).
- Questions are loaded from disk at runtime with `readFile`.
- The quiz shuffles questions with the Fisher-Yates algorithm.
- Terminal colors are implemented with ANSI escape codes, so no dependency is needed.
- Input handling is promise-based to keep the CLI flow readable.

## Scripts

| Script | Command | Description |
| --- | --- | --- |
| Start app | `npm start` | Runs the quiz CLI |
| Test | `npm test` | Runs Node's test runner |

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add or update tests where relevant
5. Submit a pull request

## License

MIT