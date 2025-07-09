# 🐚 SQL Minifier — Bash/Perl One-Liner for Compact SQL

A blazing-fast, dependency-free SQL minifier for the command line.
Removes comments and collapses whitespace so your SQL is ready for logs, APIs, or inline embedding.

---

## ✨ Features

* ✅ Removes `--` style comments (outside of quotes)
* ✅ Collapses all whitespace (tabs, newlines, spaces) into a single space
* ✅ Preserves quoted strings (`'`, `"`, `` ` ``)
* ✅ Outputs minified SQL as a single line
* ✅ Native support on any machine with Bash + Perl (no external dependencies!)

---

## 🆚 Why This Tool?

Most SQL minification tools:

* ❌ Require installing Node.js, Python packages, or NPM libraries
* ❌ Aren't optimized for CLI usage or piping workflows
* ❌ Ignore SQL quoting edge cases (e.g. comment symbols inside strings)

**This tool** is:

* 🔧 100% shell-native (just Bash and Perl)
* 🪶 Lightweight — under 10 lines of Perl
* 🧠 Intelligent — skips `--` comments unless inside quotes
* 🚀 Ideal for scripting, CI/CD logs, and API payloads

---

## 💻 Usage

### 🗃️ From SQL file

```bash
./minify-sql.sh path/to/query.sql > output.sql
```

### 📥 From pipe

```bash
cat path/to/query.sql | ./minify-sql.sh
```

Or:

```bash
echo "SELECT * FROM users -- fetch all" | ./minify-sql.sh
```

---

## 📦 Example

Input (`query.sql`):

```sql
SELECT *
FROM users -- fetch user table
WHERE name = 'John -- Doe'
AND email LIKE "%@example.com";
```

Command:

```bash
./minify-sql.sh query.sql
```

Output:

```
SELECT * FROM users WHERE name = 'John -- Doe' AND email LIKE "%@example.com";
```

---

## 🧪 Requirements

* `bash`
* `perl` (standard on macOS, most Linux distributions, WSL, and Git Bash for Windows)

---

## 🤖 Authorship & AI Credit

This project was written **100% using AI**, specifically **[ChatGPT by OpenAI](https://openai.com/chatgpt)**.
It was designed, debugged, and documented with zero human coding beyond execution and copy/paste.

If you’re impressed, thank [ChatGPT](https://chat.openai.com)!

---

## 🧩 Alternatives?

There are currently **no open source** CLI tools dedicated to SQL minification.

* **JS-based tools** exist in browser environments or for bundlers
* **Database tools** sometimes offer formatting, but rarely minification
* **Regex hacks** fail on real-world SQL with comments inside strings

This tool fills that gap for developers and ops engineers who just want clean, reliable SQL output.

---

## 🔓 License

MIT — free to use, copy, and share.
