## 📖 Overview

This repository demonstrates setting up a robust Git commit workflow using:

- **Husky 9+** for Git hooks management
- **Commitlint** to validate commit messages
- **Commitizen (cz)** with **cz-customizable** for an interactive commit message wizard

The goal is to ensure every commit follows the [Conventional Commit](https://www.conventionalcommits.org/en/v1.0.0/) standard, making Git history clean and readable.

## Understanding

- How Git hooks work internally with Husky 9+.
- Know how to enforce commit message standards with Commitlint.
- Use Commitizen to guide developers in writing standardized commits interactively.
- Customize type and scope selections with cz-customizable.

## 🛠 Setup

### 1. Install dependencies

```bash
npm install
```

### 2. Initialize Husky (if not already)

```bash
npx husky init
```

### 3. Configure Git hooks

```bash
echo "pre-commit" > .husky/pre-commit
echo "npx --no -- commitlint --edit \$1" > .husky/commit-msg
```

✅ Git hooks are now ready!

### 4. Configure Commitizen

In `package.json`:

```json
"config": {
    "commitizen": {
      "path": "./node_modules/cz-conventional-changelog"
    }
  }
```

or customizable

```json
"config": {
  "commitizen": {
    "path": "cz-customizable"
  }
}
```

Create `.cz-config.js` for types and scopes customization ref : [Commitlint rule configuration](https://commitlint.js.org/reference/rules.html).

### 5. Set up Commitlint

Create [`commitlint.config.js`](https://github.com/kaweel/try-huskey-2025/blob/master/commitlint.config.js):

## 🚀 Daily Workflow

1.Stage your changes:

```bash
git add .
```

2.Run Commit or Commitizen wizard:

```bash
# run commitizen wizard then select type, scope, and write a short description.
npm run commit

# run git commit
git commit -m "<type>(optional-scope): <subject>"
```

3.Husky will automatically validate the commit message.

## 📚 Resources

- Husky - [Read More](https://typicode.github.io/husky/)
- Commitlint - [Read More](https://commitlint.js.org/)

## ✨ Summary

This repository proves that by combining Husky, Commitlint, and Commitizen, we can automate and standardize Git workflows while keeping developer experience simple and smooth.

- Clean, consistent, and meaningful commit messages.
- Reduced human error in commit practices.
- Automated quality checks at commit time.
- Easier Git history tracking for future developers and reviewers.

## 📜 License

MIT License.

### 🚀 Happy Coding! 😊
