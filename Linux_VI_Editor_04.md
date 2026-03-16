# 📝 VI (Text Editor)

### Description
The `vi` command opens the **vi editor**, one of the most widely used text editors in Linux.

**Basic Command:**

```bash
vi file_name   # Open file in vi editor
```

---

## Modes in VI Editor

### 1️⃣ Normal Mode (default)

Used for **navigation** and **command execution**.

| Command | Description                          |
|-------|--------------------------------------|
| `gg`  | Go to the **first line** of the file |
| `7gg` | Go to the **7th line** of the file   |
| `G`   | Move to the **end of the file**      |
| `M`   | Move to the **middle** of the file   |
| `:9`  | Move to **line number 9**            |

---

```bash
vi -R file_name                         # View file in read only mode

:se nu                                  # set line numbers

:se nonu                                # Hide line numbers
```

---

### 2️⃣ Insert Mode

Used for **text editing** (press `i` to enter, `Esc` to exit).

#### Insert Mode Shortcuts

| Command | Description                              |
|-------|------------------------------------------|
| `i`   | Insert before cursor                     |
| `Esc` | Exit insert mode                         |
| `I`   | Move to **start of the line** and insert |
| `A`   | Move to **end of the line** and insert   |
| `o`   | Create a **new line below**              |
| `O`   | Create a **new line above**              |

---

### ✏️ Editing Text

| Command    | Description                      |
|-----------|----------------------------------|
| `yy`      | Copy (yank) the current line     |
| `p`       | Paste (print) the copied content |
| `u`       | Undo last action                 |
| `Ctrl + r`| Redo last undone action          |
| `dd`      | Delete the current line          |

---

### 🔍 Search and Replace

| Command | Description |
|-------|-------------|
| `/pattern` | Search forward for a pattern |
| `:%s/oldword/newword` | Replace a word throughout the file |
| `:se nu` | Show line numbers |

---

### ⚙️ Command Mode

Used for **saving**, **quitting**, and **searching** (press `:` in Normal mode).

| Command | Description |
|-------|-------------|
| `:wq` | Save and exit |
| `:q!` | Exit without saving |
````
