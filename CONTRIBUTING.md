# Contributing

Thanks for your interest in improving **Kotlin Fundamentals**! Whether you're fixing a typo, adding a new chapter, or improving an existing explanation, every contribution is welcome.

## How to contribute

### 1. Fork & clone

```bash
# Fork via GitHub UI, then:
git clone https://github.com/<your-username>/Learn-Kotlin.git
cd Learn-Kotlin
```

### 2. Create a branch

Name it after what you're working on:

```bash
git checkout -b add-chapter-10
# or
git checkout -b fix-typo-collections
```

### 3. Make your changes

#### Adding a new chapter

Each chapter lives in its own numbered folder following the pattern `XX-topic-name/`:

```
XX-topic-name/
├── README.md   ← Explanation in French, with code blocks and exercises
└── main.kt     ← Runnable Kotlin source file
```

- **Numbering**: Use the next available two-digit number (e.g. `10-lambda-expressions-with-receiver/`).
- **README.md**: Write the lesson content in French. Include Kotlin code examples inside fenced blocks (` ```kotlin `), and add a **Practice** section with at least one exercise and its solution.
- **main.kt**: A standalone file that compiles and runs with `kotlinc`. It should demonstrate the chapter's key concepts.
- **Navigation links**: Add a `[Prochaine étape](../XX-next-chapter/README.md)` link at the bottom, and update the previous chapter's link to point to yours.

#### Editing existing content

- Fix typos, improve explanations, or add exercises — anything that makes the material clearer.
- Keep the existing French/English style consistent with the rest of the chapter.

#### Style guidelines

- Use **French** for lesson prose and comments.
- Use standard Kotlin [coding conventions](https://kotlinlang.org/docs/coding-conventions.html) in code examples.
- Keep code blocks indented consistently (4 spaces).

### 4. Test locally

Make sure the MkDocs site still builds without errors:

```bash
pip install mkdocs-material   # if not already installed
mkdir -p docs
cp -r [0-9][0-9]-* docs/
sed 's#https://github.com/clarkhawk/Learn-Kotlin/blob/main/##g' README.md > docs/index.md
mkdocs build --strict
```

If you added a `main.kt`, verify it compiles:

```bash
kotlinc XX-topic-name/main.kt -include-runtime -d main.jar && java -jar main.jar
```

### 5. Commit & push

Write clear commit messages:

```bash
git add .
git commit -m "add: chapter 10 — lambda expressions with receiver"
# or
git commit -m "fix: typo in collections chapter"
git push origin your-branch-name
```

### 6. Open a Pull Request

- Go to [the repository](https://github.com/clarkhawk/Learn-Kotlin) and click **"Compare & pull request"**.
- Describe what you changed and why.
- Link any related issue if applicable.

## Reporting issues

Found a bug, a broken link, or have a suggestion? [Open an issue](https://github.com/clarkhawk/Learn-Kotlin/issues/new) with a clear description.

## Code of Conduct

Be respectful and constructive. We're all here to learn.
