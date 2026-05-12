# Course Outline: CLIs

**Title:** CLIs — The Developer's Best Tool
**Skill:** __ — Skill: Proveer de herramientas a un Agente mediante CLIs
**Learnpack:** + CLIs
**File:** s__-w20d58-clis
**Prerequisite:** Basic Python programming
**Target Audience:** Beginner developers who have never built a command-line tool
**Total Lessons:** 8
**Format:** Mixed (12.5% hands-on)

---

## Course Description

Command-line interfaces (CLIs) are how developers actually interact with tools — git, npm, docker, python. This course explains what CLIs are, why every developer eventually needs to build one, and how to build a good one in Python using Click or argparse. Students come away understanding the anatomy of a CLI command, the design principles that make a CLI pleasant to use, and with a working CLI tool they built themselves.

---

## Course Philosophy

This course emphasizes:
- Learning by seeing what great CLIs look like first, then building
- Understanding the user experience before the implementation
- Simple, focused exercises — no library complexity, just the core pattern

---

## Course Statistics Summary

| Section | Lessons |
|---------|---------|
| 00 - Welcome | 1 |
| 01 - Understanding CLIs | 2 |
| 02 - Building a CLI | 3 |
| 03 - Assessment | 1 |
| 04 - Outro | 1 |
| **Total** | **8** |

---

### 00.0 The Developer's Best Tool 📖

**Learning Objectives:**
- Explain what a CLI is and where CLIs fit in a developer's daily workflow
- Give examples of CLIs they already use without realizing it

**Content Outline:**
- What is a CLI? A text-based interface where you type commands and get responses
- CLIs developers use every day: `git commit`, `npm install`, `docker run`, `python script.py`
- Why CLIs matter: reproducible, scriptable, automatable — things GUIs can't match
- The course overview: what a CLI is, why developers love them, and how to build one

**Transitions:**
This lesson sets the stage. Section 01 goes deep into what CLIs are and why they're built the way they are.

**Key Principles:**
- CLIs are the interface of automation — anything you can do in a GUI can be scripted with a CLI
- Text-based interfaces are universally accessible: they work the same on every machine

**Examples:**
- `git status` → tells you the state of your repository
- `npm install express` → installs a package
- `docker ps` → lists running containers
All of these are CLIs. You've been using them for years.

---

### 01.0 Understanding CLIs 📖

**Learning Objectives:**
- Define CLI and explain how it differs from a GUI and an API
- Describe the anatomy of a CLI command: program, subcommand, arguments, options, flags
- Preview what lesson 01.1 covers (why developers love CLIs)

**Content Outline:**
- **What a CLI is:** a program that reads text commands from the terminal and produces text output
- **CLI vs GUI:** GUIs are for point-and-click; CLIs are for typing; CLIs are faster for repetitive tasks
- **CLI vs API:** an API is a programmatic interface between programs; a CLI is a human-facing interface at the terminal
- **Anatomy of a CLI command:**
  - `git commit -m "Fix login bug"` broken down:
    - `git` → the program name
    - `commit` → the subcommand
    - `-m` → an option (short form)
    - `"Fix login bug"` → the argument to the `-m` option
  - Arguments (positional): values passed directly — `git add file.txt`
  - Options (named): prefixed with `-` or `--` — `--verbose`, `--output=file`
  - Flags (boolean options): `--dry-run`, `-v` (present = true, absent = false)
  - Help text: every good CLI has `--help`

**Transitions:**
Now you know what a CLI is structurally. Lesson 01.1 explains why developers choose them over GUIs.

**Key Principles:**
- The anatomy of CLI commands is standardized — once you learn the pattern, you can use any CLI
- Arguments are positional (order matters); options are named (order doesn't matter)

**Examples:**
Breaking down `docker run --name myapp -p 8080:80 nginx`:
- `docker` → program
- `run` → subcommand
- `--name myapp` → named option with value
- `-p 8080:80` → short option with value
- `nginx` → positional argument (the image)

---

### 01.1 Why Developers Love CLIs 📖

**Learning Objectives:**
- Explain three practical advantages of CLIs over GUIs: automation, composability, and reproducibility
- Give a real example where a CLI approach is clearly superior to a GUI approach

**Content Outline:**
- **Automation:** CLIs can be scripted — run the same command 1,000 times with a loop
  - GUI: you must click through each step manually
  - CLI: `for f in *.csv; do python process.py $f; done`
- **Composability:** CLI tools can be combined using pipes and redirects
  - `git log --oneline | grep "fix" | wc -l` — count commits mentioning "fix"
  - Each tool does one thing; they chain together
- **Reproducibility:** a CLI command is a recipe anyone can follow exactly
  - Share a CLI command in a README: anyone can reproduce your result
  - Share a GUI workflow: you need screenshots and hope the UI hasn't changed
- **Speed:** once you know a CLI, it's faster than any GUI — no menus to navigate
- **Remote access:** CLIs work over SSH; GUIs often don't
- **The Unix philosophy:** do one thing and do it well; compose rather than monolith

**Transitions:**
You understand the why. Section 02 now teaches the how — how to design and build a CLI.

**Key Principles:**
- CLIs scale with you: a script that runs your CLI can do in seconds what would take hours clicking through a GUI
- The best CLIs feel natural — you can guess what a command does before reading the docs

**Anti-patterns:**
- **Building a CLI that requires memorizing dozens of flags:** good CLIs have sensible defaults and clear help text
- **Building a CLI when a GUI is actually the right tool:** CLIs are for power users and automation; if your users are non-technical, a GUI may be better

**Examples:**
Compare adding 50 users to a system:
- GUI approach: click "Add User" 50 times, fill in each form manually
- CLI approach: `for user in users.txt; do adduser $user; done`

---

### 02.0 Building a CLI 📖

**Learning Objectives:**
- Describe the Python Click library and how it compares to argparse
- Explain the basic structure of a Click CLI: a function decorated with `@click.command()`
- Preview what lessons 02.1 (design principles) and 02.2 (hands-on) cover

**Content Outline:**
- **Why Python for CLIs?** Python has excellent CLI libraries and is already in most developer environments
- **argparse (stdlib):** built into Python; more verbose but no external dependencies
- **Click:** third-party but widely used; clean decorator-based API; automatic help text generation
- **Basic Click pattern:**
  ```python
  import click
  
  @click.command()
  @click.argument("name")
  def greet(name):
      click.echo(f"Hello, {name}!")
  
  if __name__ == "__main__":
      greet()
  ```
  Run: `python greet.py Alice` → outputs `Hello, Alice!`
- **What Click handles automatically:** help text (`--help`), argument validation, error messages
- Overview of what 02.1 covers (design principles) and 02.2 (hands-on challenge)

**Transitions:**
You know the basic structure. Lesson 02.1 covers the design principles that separate great CLIs from frustrating ones.

**Key Principles:**
- Click turns a Python function into a CLI command with one decorator
- Always test your CLI with `--help` after building it — if the help text is confusing, the CLI will be confusing

**Examples:**
```python
# argparse version
import argparse
parser = argparse.ArgumentParser()
parser.add_argument("name")
args = parser.parse_args()
print(f"Hello, {args.name}!")

# Click version (same result, cleaner code)
import click
@click.command()
@click.argument("name")
def greet(name):
    click.echo(f"Hello, {name}!")
```

---

### 02.1 CLI Design Principles 📖

**Learning Objectives:**
- Apply four CLI design principles: clear commands, predictable behavior, good error messages, single responsibility
- Evaluate a CLI command for usability — is it obvious what it does?
- Rewrite a poorly named CLI command using better naming conventions

**Content Outline:**
- **Clear commands:** the command name should describe what it does
  - Bad: `dt process --m 1 --x` → what does this do?
  - Good: `data-tool convert --mode csv --output report.csv`
- **Predictable behavior:** follow conventions that users know from other CLIs
  - `--verbose` / `-v` for verbose output
  - `--output` / `-o` for output file
  - `--help` / `-h` for help
  - Non-zero exit codes on failure (exit code 0 = success, non-zero = failure)
- **Good error messages:** tell the user what went wrong AND what to do
  - Bad: `Error: invalid input`
  - Good: `Error: 'file.xyz' is not a supported format. Supported formats: csv, json, parquet`
- **Single responsibility:** each command does one thing; use subcommands for grouped functionality
  - Bad: one CLI that processes, formats, uploads, and emails results
  - Good: `tool process`, `tool format`, `tool upload` — each does one thing
- **Sensible defaults:** the most common usage should require the fewest arguments
- **Reversibility / --dry-run:** for destructive operations, add a `--dry-run` flag

**Transitions:**
With design principles clear, lesson 02.2 puts them into practice.

**Key Principles:**
- A CLI is a product — it has users, and those users form opinions from the first command
- The best CLIs are self-documenting: clear names + good help text = no need to read external docs

**Anti-patterns:**
- **Cryptic flag names:** `-x`, `-q`, `-z` with no explanation
- **No error messages:** silently doing nothing when input is wrong
- **Doing too much in one command:** hard to test, hard to compose with other tools

**Examples:**
Good CLI design checklist:
- ✓ Does `--help` clearly explain every argument?
- ✓ Do error messages say what went wrong AND how to fix it?
- ✓ Does each command do exactly one thing?
- ✓ Do default values make sense for the most common use case?
- ✓ Does the command name describe what it does?

---

### 02.2 Your First CLI Tool 💻

**Challenge Prompt:**
Build a Python CLI using Click that accepts a name as a required argument and an optional `--count` option (default 1), and prints a greeting the specified number of times.

**Solution Code:**
```python
import click

@click.command()
@click.argument("name")
@click.option("--count", default=1, help="Number of times to greet.")
def greet(name, count):
    for _ in range(count):
        click.echo(f"Hello, {name}!")

if __name__ == "__main__":
    greet()
```

**Challenge Code:**
```python
import click

@click.command()
@click.argument("name")
@click.option("--count", default=1, help="Number of times to greet.")
def greet(name, count):
    # your code here: print f"Hello, {name}!" exactly `count` times
    pass

if __name__ == "__main__":
    greet()
```

---

### 03.0 CLI Assessment 🧠

**Learning Objectives:**
- Demonstrate understanding of CLI anatomy and design principles
- Identify good and bad CLI design from examples
- Apply Click patterns correctly

**Question Format:** Multiple choice

**Questions:**

1. In the command `git commit -m "Add tests"`, what is `-m`?
   - a) The program name
   - b) A positional argument
   - c) A named option (short form)
   - d) A boolean flag

2. Which of the following is a boolean flag?
   - a) `--output report.csv`
   - b) `--count 5`
   - c) `--verbose`
   - d) `--name Alice`

3. You run a CLI and it outputs nothing when given invalid input. What design principle was violated?
   - a) Single responsibility
   - b) Clear commands
   - c) Good error messages
   - d) Predictable behavior

4. What does `click.echo()` do compared to Python's `print()`?
   - a) It's identical — both print to stdout
   - b) It handles different output streams correctly and works with Click's testing utilities
   - c) It writes to a file instead of the terminal
   - d) It adds color to all output automatically

5. A CLI command is named `dt -x 2 -q output.csv`. What is wrong with this?
   - a) Nothing — short flags are always preferred
   - b) The command name and flags are cryptic — a user can't guess what this does
   - c) CSV output is not supported in CLIs
   - d) The number 2 cannot be passed as an argument

6. What does a non-zero exit code from a CLI indicate?
   - a) The command ran successfully with warnings
   - b) The command encountered an error or failure
   - c) The command is still running in the background
   - d) The output was written to a file

7. Which Click decorator turns a Python function into a CLI command?
   - a) `@click.argument()`
   - b) `@click.option()`
   - c) `@click.command()`
   - d) `@click.group()`

**Evaluation Criteria:**
- 7/7: Excellent — strong command of CLI anatomy and design
- 5–6/7: Good — minor gaps in Click API or design principles
- 3–4/7: Needs review — revisit Sections 01 and 02
- Below 3/7: Restart recommended

**Score Interpretation:**
Questions map to: CLI anatomy (Q1), boolean flags (Q2), error messages (Q3), click.echo (Q4), cryptic names (Q5), exit codes (Q6), Click decorator (Q7).

---

### 04.0 Command Mastered

**Content Outline:**
- Course recap: what students accomplished
  - Understood what CLIs are and the anatomy of a command (program, subcommand, arguments, options, flags)
  - Learned why developers prefer CLIs for automation, composability, and reproducibility
  - Built a Python CLI with Click — a real, working command-line tool
  - Applied CLI design principles: clear names, predictable behavior, good error messages, single responsibility
- Connection to bigger picture: CLIs are the foundation of the next topic — how AI agents use CLIs as tools. An agent that can call CLIs can leverage the entire ecosystem of existing tools
- Next steps: the next learnpack covers CLIs from the AI's perspective — what makes a CLI good for an AI agent to call, not just for a human
- Resources for further exploration:
  - Click documentation: click.palletsprojects.com
  - Python argparse docs: docs.python.org/3/library/argparse.html
  - "The Art of Command Line": github.com/jlevy/the-art-of-command-line
- Encouragement: you now know how to build tools that other developers (and AI agents) can use — that's a serious capability

**Note:** This is conclusion only — no theory, exercises, or assessment.

---
