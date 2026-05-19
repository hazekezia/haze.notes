---
icon: github
---

# Proper Git Commit Naming

Using clear commit messages helps keep project history clean and easy to understand.

Recommended format:

```git-commit
type: short description
```

Example:

```git-commit
feat: add login feature
```

***

## Common Commit Types

### `feat`

Used for new features.

```git-commit
feat: add dark modefeat: add file upload feature
```

***

### `fix`

Used for bug fixes.

```git-commit
fix: resolve login errorfix: prevent application crash
```

***

### `docs`

Used for documentation changes.

```git-commit
docs: update installation guide
```

***

### `style`

Used for formatting changes.

```git-commit
style: format code with prettier
```

***

### `refactor`

Used for code improvements without changing functionality.

```git-commit
refactor: simplify authentication logic
```

***

### `test`

Used for adding or updating tests.

```git-commit
test: add login unit test
```

***

### `chore`

Used for maintenance tasks.

```git-commit
chore: update dependencies
```

***

## Good Commit Message Examples

```git-commit
feat: add search feature
fix: resolve upload issue
docs: update README
```

***

## Bad Commit Message Examples

```
update
fix
final
test
```

These messages do not clearly describe the changes made. Future developers, including yourself, will suffer quietly while reading them.
