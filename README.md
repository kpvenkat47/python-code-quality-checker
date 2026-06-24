# 🛠️ Python Code Quality Checker

> **One command. Five tools. Clean code guaranteed.**

Tired of running `black`, `isort`, `flake8`, `pylint`, and `mypy` one by one?  
This tool runs all of them **in one shot** — and tells you exactly what passed and what didn't.

---

## ✨ What It Does

Every time you run it, it automatically:

- 🎨 **Formats** your code with `black`
- 📦 **Organizes** your imports with `isort`
- 🔍 **Checks** PEP 8 style with `flake8`
- 🧠 **Inspects** for errors and warnings with `pylint`
- ✅ **Validates** your type hints with `mypy`

Then gives you a clean **pass/fail summary** at the end — so you know exactly where to look.

---

## 🖥️ Demo Output

```
==================================================
RUNNING : black your_script.py
==================================================
reformatted your_script.py
PASSED | Time: 0.45s

==================================================
RUNNING : pylint your_script.py
==================================================
your_script.py:12:0: C0114: Missing module docstring
FAILED | Time: 1.23s

==================================================
SUMMARY
==================================================
  ✅  isort
  ✅  black
  ✅  flake8
  ❌  pylint
  ✅  mypy

Some checks failed — review the output above.
==================================================
```

---

## ⚙️ Installation

### 1. Clone this repo
```bash
git clone https://github.com/kpvenkat47/python-code-quality-checker
cd python-code-quality-checker
```

### 2. Install the required tools
```bash
pip install black isort flake8 pylint mypy
```

That's it. No complex setup. No config files needed to get started.

---

## 🚀 Usage

### Basic usage — check a single file
```bash
python quality_checker.py your_script.py
```

### Example
```bash
python quality_checker.py etl_pipeline.py
python quality_checker.py data_cleaner.py
python quality_checker.py api_handler.py
```

---

## 📌 Current Limitations (Roadmap)

This tool currently works on **one Python file at a time**.  
Here's what's planned for future versions:

| Feature | Status |
|---------|--------|
| ✅ Single file support | **Available now** |
| 🔜 Folder/project support | Coming soon |
| 🔜 `--fix` flag (formatters only) | Coming soon |
| 🔜 `--strict` flag (fail on warnings) | Coming soon |
| 🔜 JSON/HTML report output | Coming soon |
| 🔜 `pip install` support | Coming soon |

> 💡 **Want a feature?** Open an issue and let me know!

---

## 🧰 Tools Explained

Not sure what each tool does? Here's a quick breakdown:

| Tool | Type | What It Does | Changes Your Code? |
|------|------|--------------|-------------------|
| `black` | Formatter | Enforces consistent code style | ✅ Yes |
| `isort` | Formatter | Sorts and groups imports | ✅ Yes |
| `flake8` | Linter | Checks PEP 8 rules and basic errors | ❌ No |
| `pylint` | Linter | Deep inspection — errors, warnings, suggestions | ❌ No |
| `mypy` | Type Checker | Validates type hints and annotations | ❌ No |

> 💡 **Formatters** clean up your code automatically.  
> 💡 **Linters** tell you what's wrong — you fix it yourself.  
> 💡 **Type checkers** only work well when you use type hints.

---

## 💡 Why I Built This

I profile and review every Python script before delivery — it's a habit I follow on every project.

But running five tools manually every single time was slow and easy to forget.  
So I automated the whole process into one command.

Now I run this before delivering **any** script. It takes under 10 seconds and catches issues I might have missed.

---

## 📋 Requirements

- Python 3.8+
- black
- isort
- flake8
- pylint
- mypy

---

## 🤝 Contributing

Contributions are welcome!  
If you have ideas for improvements or new features:

1. Fork the repo
2. Create a new branch (`git checkout -b feature/your-idea`)
3. Make your changes
4. Open a Pull Request

Even small improvements (better error messages, new flags, docs) are appreciated. 🙏

---

## 📄 License

MIT License — free to use, modify, and share.

---

## 👋 About

Built by **Pitchaiah Venkat K** — Python Engineer working on data pipelines, ETL systems, and developer tooling.

---
⭐ **If this tool saved you time, consider giving it a star!** It helps others find it too.
