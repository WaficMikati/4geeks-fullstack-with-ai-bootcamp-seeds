# Course Outline: Command Line Fundamentals

**Title:** Command Line Fundamentals for Developers  
**Prerequisite:** File System Hierarchy (Week 2, Day 4 - previous learnpack)  
**Target Audience:** Beginner developers (Week 2, Day 4) learning essential terminal commands for daily development work  
**Total Lessons:** 14  
**Estimated Total Length:** ~7,000 words  
**Format:** Practical (64% hands-on)

---

## Course Description

The command line is a developer's most powerful tool for interacting with their computer. While graphical interfaces are comfortable, professional developers use the terminal to work faster, automate tasks, and access powerful features unavailable through clicking and dragging.

This course teaches the essential commands every developer uses daily. Building on your understanding of file system hierarchy from the previous learnpack, you'll learn the actual commands to navigate, create, manage, and search files. By the end of this course, you'll be comfortable executing the 10 most common developer commands and solving real file management problems from the terminal.

These commands form the foundation for version control with Git (coming next), running development servers, deploying applications, and working efficiently in any development environment.

---

## Course Philosophy

This course emphasizes:
- **Commands over theory**: Learn by doing, not by memorizing syntax
- **Muscle memory through repetition**: Practice each command extensively
- **Real-world workflows**: Combine commands to solve actual problems
- **Safety awareness**: Understand dangerous commands before using them
- **Path of least resistance**: Master basic usage before exploring advanced options
- **No AI assistance**: Build genuine command line proficiency

---

## Course Statistics Summary

| Section | Lessons | Estimated Words |
|---------|---------|----------------|
| 00 - Welcome to the Command Line | 1 | ~450 |
| 01 - Navigation Commands | 3 | ~1,650 |
| 02 - File Management Commands | 4 | ~2,200 |
| 03 - Working with Content | 3 | ~1,650 |
| 04 - Mastery & Assessment | 2 | ~1,400 |
| 05 - Your Command Line Journey | 1 | ~450 |
| **Total** | **14** | **~7,000** |

---

## Section 00: Welcome to the Command Line

### 00.0 Why Developers Use the Terminal 📖 (~450 words)

**Learning Objectives:**
- Understand why professional developers prefer the command line over graphical interfaces
- Recognize situations where the terminal is faster and more efficient
- Identify the connection between command line commands and future development work
- Set expectations for the learning curve

**Content Outline:**
- What makes the command line powerful for developers
- Graphical interfaces vs command line efficiency
- Real-world development scenarios requiring terminal commands
- Overview of the 10 essential commands you'll learn
- Why mastering these commands matters for your career

**Transitions:**
In the previous learnpack, you learned how file systems are organized—the hierarchy, paths, and structure. Now you'll learn the actual commands to work within that structure. Let's start with the most fundamental question: "Where am I?"

**Key Principles:**
- Commands are faster than clicking once you know them
- Every graphical operation has a command line equivalent
- Terminal commands are essential for Git, servers, and automation
- These 10 commands cover 90% of daily development tasks
- Building muscle memory takes practice, not memorization

**Examples:**
- Creating 100 folders: 2 hours clicking vs 2 seconds with `mkdir`
- Finding all files containing "TODO": impossible with clicks, instant with `grep`
- Renaming files following a pattern: manual vs one command
- Running development servers: `npm start`, `python app.py`
- Deploying code to production: all done via terminal

---

## Section 01: Navigation Commands

### 01.0 Finding Your Location: pwd 💻 (~500 words)

**Learning Objectives:**
- Execute the `pwd` command to display current working directory
- Interpret the output showing your absolute path
- Understand why knowing your location is critical before executing other commands
- Build the habit of checking location frequently

**Content Outline:**
- What `pwd` stands for: "print working directory"
- When to use `pwd`: before any file operation
- Reading the output: understanding the absolute path displayed
- Why every terminal session has a "current location"
- Common scenarios where `pwd` saves you from mistakes

**Transitions:**
Now that you can identify where you are, you need to learn how to move somewhere else. That's where `cd` comes in.

**Key Principles:**
- `pwd` shows your current location in the file system
- Always run `pwd` when you're unsure of your location
- The output is always an absolute path
- Your current directory affects which files commands can see
- "Where am I?" is the most important question in the terminal

**Examples:**
- Opening terminal: `pwd` shows `/Users/yourname` or `/home/yourname`
- After navigating: `pwd` shows `/Users/yourname/Documents/projects`
- In a project: `pwd` shows `/Users/yourname/Desktop/my-website`
- Lost in directories: `pwd` helps you orient yourself

**Hands-On Exercise:**
**Your First Command**
1. Open your terminal application
2. Type `pwd` and press Enter
3. Read the output—this is where you started
4. Open a new terminal window
5. Run `pwd` again—compare the location
6. Notice if they're the same (usually your home directory)

**Practice Scenario:**
You'll execute `pwd` hundreds of times today. Get comfortable with:
- Opening terminal and immediately running `pwd`
- Reading the full path from root to current location
- Recognizing your home directory path
- Understanding that `pwd` never changes anything—it just shows information

**Success Criteria:**
- Successfully execute `pwd` command
- Read and interpret the absolute path output
- Understand that this shows current working directory
- Build the habit of running `pwd` before other commands

---

### 01.1 Moving Around: cd 💻 (~550 words)

**Learning Objectives:**
- Use `cd` to change your current working directory
- Navigate using both absolute and relative paths (from previous learnpack)
- Use shortcuts: `cd ~` for home, `cd ..` for parent, `cd -` for previous
- Combine `cd` and `pwd` for safe navigation

**Content Outline:**
- What `cd` stands for: "change directory"
- Basic syntax: `cd [destination]`
- Using absolute paths: `cd /Users/yourname/Documents`
- Using relative paths: `cd Documents` (from home)
- Essential shortcuts you'll use constantly
- Why you should run `pwd` after every `cd`

**Transitions:**
You can find your location and move around. But to navigate effectively, you need to see what's available at each location. That's what `ls` does.

**Key Principles:**
- `cd` changes your current working directory
- If `cd` succeeds, you see no output (silence means success in Unix)
- `cd` without arguments returns you to home directory
- Always verify your move with `pwd`
- Shortcuts save time: `~` (home), `..` (parent), `-` (previous)

**Examples:**
- `cd Documents` - move into Documents folder (relative path)
- `cd ~/Desktop` - move to Desktop using home shortcut (absolute from home)
- `cd ..` - go up one level to parent directory
- `cd ../..` - go up two levels
- `cd -` - return to previous directory (like browser back button)
- `cd` - return to home directory (no arguments)

**Hands-On Exercise:**
**Navigation Practice**
1. Run `pwd` to see your starting location
2. Run `cd Desktop` to move to Desktop
3. Run `pwd` to confirm you moved
4. Run `cd ..` to go back up
5. Run `pwd` to see where you are now
6. Run `cd ~` to return home
7. Run `pwd` to verify you're home
8. Run `cd Documents`
9. Run `cd -` to return to previous location
10. Run `pwd` to see the result

**Practice Scenario:**
Navigate through your system:
- Start at home: `pwd`
- Go to Desktop: `cd Desktop`
- Verify: `pwd`
- Go to Documents from anywhere: `cd ~/Documents`
- Verify: `pwd`
- Go up one level: `cd ..`
- Verify: `pwd`
- Return home: `cd`
- Verify: `pwd`

**Success Criteria:**
- Successfully navigate to different directories
- Use absolute paths to move anywhere from anywhere
- Use relative paths to move within your current location
- Use shortcuts (`~`, `..`, `-`) effectively
- Always verify moves with `pwd`

---

### 01.2 Seeing Contents: ls and Its Options 💻 (~600 words)

**Learning Objectives:**
- Use `ls` to list directory contents
- Understand and apply common flags: `-l`, `-a`, `-la`, `-h`
- Distinguish between files and directories in output
- List contents of other directories without navigating there

**Content Outline:**
- What `ls` stands for: "list"
- Basic usage: `ls` shows visible files and folders
- Long format: `ls -l` shows details (permissions, size, date)
- Show all files: `ls -a` includes hidden files (starting with `.`)
- Combining flags: `ls -la` or `ls -l -a` (same result)
- Human-readable sizes: `ls -lh` shows KB/MB instead of bytes
- Listing other locations: `ls ~/Desktop` without moving there

**Transitions:**
You now have the three fundamental navigation commands: `pwd` (where am I?), `cd` (go somewhere), and `ls` (what's here?). These three commands work together in every terminal session. Now let's learn commands that actually create and modify files.

**Key Principles:**
- `ls` shows directory contents without changing your location
- Flags modify command behavior (always start with `-`)
- You can combine multiple flags: `-la` = `-l` + `-a`
- Hidden files (starting with `.`) are important in development (`.git`, `.env`)
- Long format (`-l`) shows file details developers need

**Examples:**
- `ls` - simple list of visible items
- `ls -l` - detailed view with permissions, owner, size, date
- `ls -a` - show all files including hidden (`.bashrc`, `.gitignore`)
- `ls -la` - detailed view including hidden files
- `ls -lh` - detailed view with human-readable sizes (5.2M instead of 5242880)
- `ls ~/Documents` - list Documents contents without going there
- `ls ..` - list parent directory contents

**Hands-On Exercise:**
**Exploring with ls**
1. Navigate to your home directory: `cd ~`
2. Run basic ls: `ls`
3. Run with all files: `ls -a` (notice the hidden files starting with `.`)
4. Run detailed view: `ls -l` (see permissions, sizes, dates)
5. Run combined: `ls -la`
6. Run human-readable: `ls -lh`
7. List Desktop without moving: `ls ~/Desktop`
8. List parent directory: `ls ..`
9. Navigate to Desktop: `cd Desktop`
10. Compare `ls` output to what you saw before

**Practice Scenario:**
Explore your file system:
- Check home contents: `cd ~`, then `ls -la`
- Find hidden files (starting with `.`)
- Check Desktop: `ls -lh ~/Desktop`
- Navigate there: `cd Desktop`
- List details: `ls -l`
- Look at file sizes and modification dates
- Go back: `cd ..`
- List again to orient yourself

**Success Criteria:**
- Execute `ls` with various flag combinations
- Identify hidden files in output
- Read long format output (permissions, sizes, dates)
- List contents of directories without navigating to them
- Understand when to use which flags

---

## Section 02: File Management Commands

### 02.0 Creating: mkdir and touch 💻 (~550 words)

**Learning Objectives:**
- Create new directories using `mkdir`
- Create new empty files using `touch`
- Create multiple items with a single command
- Create nested directory structures with `-p` flag
- Verify creation using `ls`

**Content Outline:**
- The `mkdir` command: "make directory"
- Creating single directories: `mkdir foldername`
- Creating multiple directories: `mkdir folder1 folder2 folder3`
- Creating nested structures: `mkdir -p` flag
- The `touch` command: creates empty files
- Creating multiple files at once
- Best practices: naming conventions (no spaces, use `-` or `_`)
- Always verify with `ls` after creating

**Transitions:**
Creating files and folders is just the beginning. Often you need to duplicate files for backups or organize by copying content. That's where `cp` comes in.

**Key Principles:**
- `mkdir` creates directories (folders)
- `touch` creates empty files
- Use `-p` flag with `mkdir` to create nested structures in one command
- Both commands can create multiple items at once
- Avoid spaces in names (use `my-file.txt`, not `my file.txt`)
- Silent success: no output means it worked

**Examples:**
- `mkdir projects` - create single directory
- `mkdir project-a project-b project-c` - create three directories at once
- `mkdir -p projects/2024/january` - create entire nested structure
- `touch index.html` - create empty HTML file
- `touch app.js styles.css readme.md` - create three files at once
- `touch src/components/Header.js` - create file in existing directory

**Hands-On Exercise:**
**Building a Project Structure**
1. Navigate to Desktop: `cd ~/Desktop`
2. Verify location: `pwd`
3. Create project folder: `mkdir command-line-practice`
4. Verify creation: `ls`
5. Navigate into it: `cd command-line-practice`
6. Create multiple folders: `mkdir src public assets`
7. Verify: `ls`
8. Create nested structure: `mkdir -p src/components src/utils`
9. Verify: `ls src`
10. Create files: `touch index.html readme.md`
11. Create files in subdirectory: `touch src/app.js src/styles.css`
12. Verify everything: `ls -R` (recursive list)

**Practice Scenario:**
Build this structure from scratch:
```
my-website/
├── index.html
├── about.html
├── css/
│   └── styles.css
├── js/
│   └── app.js
└── images/
```

Commands:
1. `mkdir my-website`
2. `cd my-website`
3. `touch index.html about.html`
4. `mkdir css js images`
5. `touch css/styles.css js/app.js`
6. `ls -R` to verify

**Success Criteria:**
- Create directories successfully with `mkdir`
- Create files successfully with `touch`
- Use `-p` flag to create nested structures
- Create multiple items in one command
- Verify all creations with `ls`

---

### 02.1 Copying Files: cp Command 💻 (~550 words)

**Learning Objectives:**
- Copy files using the `cp` command
- Copy directories using the `-r` (recursive) flag
- Copy multiple files to a destination directory
- Understand the danger of overwriting files
- Use `ls` to verify copies were created

**Content Outline:**
- The `cp` command syntax: `cp source destination`
- Copying single files: creates duplicate with new name/location
- Copying directories: requires `-r` flag (recursive)
- Copying multiple files to a directory
- Original file remains unchanged (copy creates duplicate)
- Warning: `cp` overwrites without asking if destination exists
- Always verify with `ls` after copying

**Transitions:**
Copying creates duplicates, but sometimes you need to relocate or rename files. That's when you use `mv` instead of `cp`.

**Key Principles:**
- `cp` creates a duplicate (original remains, copy created)
- Syntax: `cp what where`
- Directories require `-r` flag: `cp -r directory new-directory`
- Multiple files can be copied to a directory at once
- Overwrites destination without warning—be careful!
- Use tab completion to avoid typos in filenames

**Examples:**
- `cp app.js app-backup.js` - copy file with new name
- `cp index.html ../index.html` - copy to parent directory
- `cp -r images images-backup` - copy entire directory
- `cp file1.txt file2.txt file3.txt backup/` - copy multiple files to folder
- `cp ~/Desktop/file.txt .` - copy from Desktop to current directory (`.` = here)

**Hands-On Exercise:**
**Practicing File Copying**
1. Navigate to your practice project: `cd ~/Desktop/command-line-practice`
2. Verify location: `pwd`
3. List contents: `ls`
4. Copy a file: `cp index.html index-backup.html`
5. Verify: `ls` (should see both files)
6. Create backup folder: `mkdir backup`
7. Copy file into folder: `cp index.html backup/`
8. Verify: `ls backup/`
9. Copy directory: `cp -r src src-backup`
10. Verify: `ls` (should see both `src` and `src-backup`)
11. Copy multiple files: `cp index.html readme.md backup/`
12. Verify: `ls backup/`

**Practice Scenario:**
Create a complete backup:
- You have a project with multiple files and folders
- Create a `backup` directory
- Copy all HTML files to backup
- Copy the entire `src` directory to backup
- Copy configuration files (`readme.md`, etc.) to backup
- Verify everything copied correctly

**Success Criteria:**
- Successfully copy files with `cp`
- Use `-r` flag when copying directories
- Copy multiple files in one command
- Understand that original files remain unchanged
- Always verify copies were created

---

### 02.2 Moving and Renaming: mv Command 💻 (~550 words)

**Learning Objectives:**
- Move files and directories using `mv`
- Rename files and directories using `mv`
- Understand the difference between `cp` and `mv`
- Recognize that `mv` doesn't require `-r` for directories
- Use `ls` to verify moves and renames

**Content Outline:**
- The `mv` command: "move"
- Syntax: `mv source destination`
- Moving files to different directories
- Renaming: `mv oldname newname` in same directory
- Moving directories: no `-r` flag needed (unlike `cp`)
- Original file disappears (unlike `cp` which keeps both)
- Warning: `mv` overwrites without asking
- Renaming vs moving: same command, different intent

**Transitions:**
You can create, copy, and move files. Now you need to see what's inside them before deciding what to do with them. That's where file viewing commands come in.

**Key Principles:**
- `mv` relocates or renames (original disappears)
- Same syntax for moving and renaming: `mv old new`
- Directories don't need `-r` flag (unlike `cp`)
- Overwrites destination without warning—be careful!
- Original file location no longer has the file
- Renaming is just "moving" to a new name in same directory

**Examples:**
- `mv app.js main.js` - rename file
- `mv styles.css css/` - move file into directory
- `mv old-folder new-folder` - rename directory
- `mv file1.txt file2.txt file3.txt archive/` - move multiple files
- `mv ~/Desktop/project.txt .` - move from Desktop to current directory

**Hands-On Exercise:**
**Practicing Moving and Renaming**
1. Navigate to practice project: `cd ~/Desktop/command-line-practice`
2. List contents: `ls`
3. Rename a file: `mv readme.md README.md` (changing case)
4. Verify: `ls` (old name gone, new name appears)
5. Create organization folder: `mkdir organized`
6. Move file into folder: `mv index-backup.html organized/`
7. Verify source: `ls` (file is gone)
8. Verify destination: `ls organized/` (file is there)
9. Rename a directory: `mv assets media`
10. Verify: `ls` (assets gone, media appears)
11. Move multiple files: `mv about.html index.html organized/`
12. Verify: `ls` and `ls organized/`

**Practice Scenario:**
Reorganize a messy project:
- Rename `old-app.js` to `legacy.js`
- Move all `.html` files to a `pages` folder
- Move all `.css` files to `styles` folder
- Rename `test` directory to `tests`
- Move backup files to `backup` folder
- Verify each step with `ls`

**Success Criteria:**
- Successfully move files between directories
- Rename files and directories
- Understand original files disappear after `mv`
- Move multiple files in one command
- Verify moves and renames with `ls`

---

### 02.3 Viewing Files: cat, less, and head 💻 (~550 words)

**Learning Objectives:**
- View entire file contents using `cat`
- Navigate large files using `less`
- Preview file beginnings using `head`
- Choose appropriate viewing command for file size
- Use keyboard shortcuts in `less`

**Content Outline:**
- The `cat` command: displays entire file
- When to use `cat`: small files, quick checks
- The `less` command: page-by-page viewing
- Navigation in `less`: space, arrows, `q` to quit
- Searching in `less`: `/searchterm`, `n` for next match
- The `head` command: shows first 10 lines
- Customizing `head`: `head -n 20` shows first 20 lines
- Choosing the right viewer for the situation

**Transitions:**
Viewing files is useful, but often you need to find specific content across multiple files. That's where `grep` becomes invaluable.

**Key Principles:**
- `cat` dumps entire file to screen (good for small files)
- `less` shows one page at a time (good for large files)
- `head` shows just the beginning (good for previews)
- Use `less` for any file longer than one screen
- In `less`: space = forward, `b` = back, `q` = quit
- `cat` multiple files: `cat file1 file2` shows them sequentially

**Examples:**
- `cat readme.md` - view README contents
- `less app.js` - view JavaScript file page by page
- `head package.json` - preview first 10 lines
- `head -n 5 index.html` - show first 5 lines only
- `cat file1.txt file2.txt` - view multiple files
- In `less`: `/function` searches for "function", `n` finds next

**Hands-On Exercise:**
**File Viewing Practice**
1. Navigate to practice project: `cd ~/Desktop/command-line-practice`
2. Create a test file with content (or use existing)
3. View small file: `cat README.md`
4. Find a larger file on your system
5. Open with less: `less /path/to/large/file`
6. Practice navigation:
   - Press space to go forward
   - Press `b` to go back
   - Press `/` and type a search term
   - Press `n` to find next occurrence
   - Press `q` to quit
7. Preview file: `head ~/.bashrc` (or `.zshrc`)
8. Show more lines: `head -n 20 ~/.bashrc`
9. Compare: `cat` vs `less` vs `head` for different files

**Practice Scenario:**
Explore different viewing methods:
- Use `cat` on a short README file
- Use `less` on your shell configuration file (`~/.bashrc` or `~/.zshrc`)
- Search for "PATH" in that file with `/PATH`
- Use `head` to preview a code file
- Use `head -n 3` to see just first 3 lines
- Compare when each command is most useful

**Success Criteria:**
- View small files with `cat`
- Navigate large files with `less`
- Use search function in `less`
- Preview files with `head`
- Choose appropriate viewer for file size
- Exit `less` properly with `q`

---

## Section 03: Working with Content

### 03.0 Searching with grep 💻 (~600 words)

**Learning Objectives:**
- Search for text patterns in files using `grep`
- Use common flags: `-i` (ignore case), `-n` (line numbers), `-r` (recursive)
- Search across multiple files with wildcards
- Interpret `grep` output format
- Apply `grep` to real development scenarios

**Content Outline:**
- What `grep` does: find text patterns in files
- Basic syntax: `grep "pattern" filename`
- Case-sensitive vs case-insensitive searching
- Showing line numbers with `-n` flag
- Searching multiple files: `grep "pattern" *.js`
- Recursive search: `grep -r "pattern" .` searches all files in directory tree
- Combining flags: `grep -in "pattern" file.txt`
- Reading `grep` output: filename, line number (if `-n`), matched line

**Transitions:**
You can now search, view, and manage files. But sometimes you need to remove files you no longer need. Deleting requires extra caution—let's learn the `rm` command and how to use it safely.

**Key Principles:**
- `grep` finds lines containing your search pattern
- Case-sensitive by default (use `-i` to ignore case)
- Returns filename and matching line
- Incredibly powerful for finding code, TODOs, errors in logs
- Wildcards let you search many files: `*.js`, `*.html`
- Recursive search (`-r`) searches entire directory trees

**Examples:**
- `grep "function" app.js` - find "function" in app.js
- `grep -i "error" log.txt` - find "error" ignoring case (matches Error, ERROR)
- `grep -n "TODO" app.js` - find TODOs with line numbers
- `grep "import" *.js` - find imports in all JavaScript files
- `grep -r "component" .` - search all files in current directory and subdirectories
- `grep -in "fetch" src/*.js` - case-insensitive search with line numbers

**Hands-On Exercise:**
**Search Practice**
1. Navigate to practice project: `cd ~/Desktop/command-line-practice`
2. Create test file with content: `touch test.txt`
3. Add content (or use existing code files)
4. Search for text: `grep "html" index.html`
5. Search ignoring case: `grep -i "HTML" index.html`
6. Search with line numbers: `grep -n "div" index.html`
7. Search all HTML files: `grep "title" *.html`
8. Recursive search: `grep -r "function" .`
9. Combine flags: `grep -rin "class" .`
10. Try searches that return no results (understand the output)

**Practice Scenario:**
Real development tasks:
- Find all files containing "import React" in a project
- Search for all TODO comments: `grep -rn "TODO" .`
- Find error messages in log files: `grep -i "error" *.log`
- Locate where a function is defined: `grep -rn "function myFunction" .`
- Find all CSS class names: `grep -r "className" src/`

**Success Criteria:**
- Successfully search files for text patterns
- Use `-i`, `-n`, and `-r` flags appropriately
- Search multiple files with wildcards
- Search entire directories recursively
- Interpret `grep` output correctly
- Apply `grep` to practical development problems

---

### 03.1 Deleting Safely: rm Command 💻 (~550 words)

**Learning Objectives:**
- Delete files using the `rm` command
- Delete directories using `rm -r`
- Understand that `rm` is permanent (no trash/recycle bin)
- Use `ls` before `rm` to verify what you're deleting
- Recognize dangerous `rm` patterns to avoid

**Content Outline:**
- The `rm` command: "remove"
- Basic syntax: `rm filename`
- Deleting multiple files: `rm file1 file2 file3`
- Deleting directories: `rm -r directory`
- Critical warning: `rm` is PERMANENT (files don't go to trash)
- Best practice: `ls` first, then `rm`
- Dangerous commands to NEVER use: `rm -rf /`, `rm -rf *`
- When in doubt, don't delete—ask for help

**Transitions:**
Deleting requires confidence. But confidence comes from understanding what can go wrong. Let's review common command line mistakes and how to avoid them.

**Key Principles:**
- `rm` permanently deletes (cannot undo)
- Files don't go to trash—they're GONE
- Directories require `-r` flag (recursive)
- Always run `ls` before `rm` to verify targets
- Be extra careful with wildcards (`*`)
- When uncertain, DON'T delete—ask someone

**Examples:**
- `rm test.txt` - delete single file
- `rm old1.txt old2.txt old3.txt` - delete multiple files
- `rm -r old-folder` - delete directory and contents
- `rm *.log` - delete all log files (use with extreme caution)

**NEVER DO THESE:**
- `rm -rf /` - deletes entire system
- `rm -rf *` - deletes everything in current directory
- `rm -rf ~` - deletes your entire home directory

**Hands-On Exercise:**
**Safe Deletion Practice**
1. Navigate to practice project: `cd ~/Desktop/command-line-practice`
2. Create test files: `touch delete-me1.txt delete-me2.txt`
3. Create test folder: `mkdir delete-this`
4. Verify they exist: `ls`
5. Delete single file: `rm delete-me1.txt`
6. Verify it's gone: `ls`
7. Delete remaining file: `rm delete-me2.txt`
8. Verify: `ls`
9. Try to delete directory without `-r`: `rm delete-this` (will fail)
10. Read the error message
11. Delete directory correctly: `rm -r delete-this`
12. Verify: `ls`

**Practice Scenario:**
Safe deletion workflow:
1. You want to delete `old-backup` folder
2. First verify: `ls` (see it exists)
3. Check contents: `ls old-backup/` (see what's inside)
4. Confirm you want to delete it
5. Delete: `rm -r old-backup`
6. Verify: `ls` (confirm it's gone)

**Success Criteria:**
- Successfully delete files with `rm`
- Successfully delete directories with `rm -r`
- Always run `ls` before `rm` to verify
- Understand that deletion is permanent
- Recognize and avoid dangerous `rm` commands
- Exercise caution with wildcards

---

### 03.2 Common Mistakes and How to Avoid Them 📖 (~500 words)

**Learning Objectives:**
- Recognize common command line mistakes beginners make
- Understand consequences of dangerous command patterns
- Learn prevention strategies for each mistake
- Build safe command line habits
- Know how to recover from common errors

**Content Outline:**
- Mistake 1: Working as root/administrator unnecessarily
- Mistake 2: Running `rm` without verifying with `ls` first
- Mistake 3: Using `-f` (force) flag without understanding it
- Mistake 4: Not checking location with `pwd` before operations
- Mistake 5: Copying/moving without verifying destination exists
- Mistake 6: Forgetting `-r` flag when copying directories
- Mistake 7: Assuming command worked without checking (run `ls` to verify)
- Prevention strategies and safe habits

**Transitions:**
You now understand all the essential commands and common pitfalls. Let's put everything together in practical challenges that simulate real development tasks.

**Key Principles:**
- The terminal does exactly what you tell it—no confirmations
- "Root" or "administrator" mode is dangerous (can break system)
- Always verify before destructive operations (`rm`, `mv`)
- Always verify after creative operations (`mkdir`, `touch`, `cp`)
- When in doubt, check `pwd` and `ls`
- If command fails, read the error message carefully

**Examples:**

**Mistake: Not checking location**
```bash
# Wrong: Don't know where I am
rm -r project

# Right: Verify first
pwd
ls
rm -r project
```

**Mistake: Deleting without verifying**
```bash
# Wrong: Just delete
rm *.txt

# Right: Check first
ls *.txt
rm *.txt
ls  # Verify deletion
```

**Mistake: Forgetting -r when copying directories**
```bash
# Wrong: Fails silently or with confusing error
cp myproject myproject-backup

# Right: Use -r for directories
cp -r myproject myproject-backup
```

**Mistake: Not verifying creation**
```bash
# Wrong: Assume it worked
mkdir newproject
cd newproject

# Right: Verify each step
mkdir newproject
ls  # See it was created
cd newproject
pwd  # Confirm I'm there
```

**Recovery Strategies:**
- Lost? Run `pwd` and `cd ~` to reset to home
- Confused about what's here? Run `ls -la`
- Command failed? Read the error message—it often explains the problem
- Deleted wrong file? If it's in Git, you can recover it (coming in next lesson)
- Made a mess? Create a new directory and start over

**Prevention Checklist:**
- [ ] Run `pwd` before any operation
- [ ] Run `ls` before `rm`
- [ ] Run `ls` after creating/copying/moving
- [ ] Use `-r` flag when copying directories
- [ ] Read error messages when commands fail
- [ ] Never work as root unless absolutely necessary
- [ ] When uncertain, stop and ask for help

---

## Section 04: Mastery & Assessment

### 04.0 Command Line Challenge Practice 💻 (~650 words)

**Learning Objectives:**
- Combine multiple commands to solve practical problems
- Build workflows using `pwd`, `cd`, `ls`, `mkdir`, `touch`, `cp`, `mv`, `rm`, `cat`, `grep`
- Develop problem-solving strategies for terminal tasks
- Practice safe command execution patterns
- Build confidence through progressive challenges

**Content Outline:**
- Challenge structure and approach
- Breaking complex tasks into command sequences
- The verification pattern: check before, execute, verify after
- Common patterns: navigate → verify → act → verify
- Progressive difficulty: simple → moderate → complex
- Tips for staying oriented during multi-step tasks

**Transitions:**
You've practiced combining commands in realistic scenarios. Now let's test your comprehensive understanding through an assessment.

**Key Principles:**
- Complex tasks are just sequences of simple commands
- Always know where you are (`pwd`)
- Always verify what's here (`ls`)
- Check your work after each step
- If lost, `cd ~` resets you to home
- Break problems into smaller steps

**Examples:**

**Challenge 1: Project Setup (Easy)**
Create this structure:
```
my-portfolio/
├── index.html
├── about.html
└── css/
    └── styles.css
```

Solution:
```bash
cd ~/Desktop
mkdir my-portfolio
cd my-portfolio
touch index.html about.html
mkdir css
touch css/styles.css
ls -R  # Verify structure
```

**Challenge 2: File Organization (Medium)**
You have mixed files. Move all `.html` to `pages/`, all `.css` to `styles/`:
```bash
pwd  # Check location
ls  # See what's here
mkdir pages styles
mv *.html pages/
mv *.css styles/
ls pages/  # Verify HTML moved
ls styles/  # Verify CSS moved
```

**Challenge 3: Backup Creation (Medium)**
Create complete backup of your project:
```bash
pwd  # Verify in parent directory
ls  # See project folder
cp -r my-website my-website-backup
ls  # Verify backup created
ls my-website-backup/  # Verify contents copied
```

**Challenge 4: Search and Organize (Hard)**
Find all files containing "TODO" and move them to `needs-work/`:
```bash
grep -rl "TODO" .  # Find files with TODO
mkdir needs-work
# Copy each file found (or use mv to move them)
cp file1.js file2.js needs-work/
ls needs-work/  # Verify
```

**Hands-On Exercise:**
**Progressive Challenges**

**Level 1: Basic Workflow**
1. Go to Desktop: `cd ~/Desktop`
2. Create folder: `mkdir cli-test`
3. Enter it: `cd cli-test`
4. Create 3 files: `touch a.txt b.txt c.txt`
5. Verify: `ls`

**Level 2: Organization**
1. Create folders: `mkdir group1 group2`
2. Move files: `mv a.txt b.txt group1/`
3. Move file: `mv c.txt group2/`
4. Verify: `ls group1/`, `ls group2/`

**Level 3: Copying and Backup**
1. Copy group1: `cp -r group1 group1-backup`
2. Verify: `ls`
3. Check contents: `ls group1-backup/`

**Level 4: Viewing and Searching**
1. View file: `cat group1/a.txt`
2. Add content (using nano in real scenario)
3. Search: `grep "text" group1/*.txt`

**Level 5: Cleanup**
1. Remove backup: `rm -r group1-backup`
2. Verify: `ls`
3. Clean up test: `cd ..`, `rm -r cli-test`

**Practice Scenario:**
**Real Development Workflow**
1. Create new project structure
2. Add files to appropriate folders
3. Create a README with project info
4. Search for placeholder text
5. Create backup before making changes
6. Organize files that were in wrong places
7. Verify entire structure is correct

**Success Criteria:**
- Complete multi-step challenges successfully
- Use verification pattern consistently
- Combine 5+ different commands in workflows
- Stay oriented throughout complex tasks
- Recover gracefully from mistakes
- Execute commands efficiently without hesitation

---

### 04.1 Testing Your Command Line Skills 🧠 (~750 words)

**Learning Objectives:**
- Demonstrate comprehensive command line understanding
- Apply commands to realistic scenarios
- Choose appropriate tools for specific tasks
- Identify safe vs dangerous command patterns

**Content Outline:**
- Assessment format and instructions
- Scenario-based questions
- Multiple-choice and command-writing questions
- Evaluation criteria

**Assessment Format:** Scenario-Based Questions

**Instructions:** For each scenario, write the command(s) you would use. Consider safety and verification steps.

---

**Question 1: Getting Oriented**

You just opened a terminal and have no idea where you are or what files are available.

*What are the first two commands you should run and why?*

**Expected answer elements:**
- `pwd` to see current location
- `ls` (or `ls -la`) to see available files/folders
- Explanation of why knowing location and contents matters

---

**Question 2: Creating Project Structure**

You need to create this structure in one efficient command sequence:
```
webapp/
├── public/
│   └── index.html
└── src/
    ├── components/
    └── utils/
```

*Write the minimal command sequence to create this structure.*

**Expected answer elements:**
- `mkdir webapp`
- `cd webapp`
- `mkdir -p public src/components src/utils`
- `touch public/index.html`
- Or equivalent efficient sequence

---

**Question 3: Safe File Deletion**

You want to delete a folder called `old-backup` but want to be absolutely sure you're deleting the right thing.

*Write the complete safe deletion workflow (3-4 commands).*

**Expected answer elements:**
- `ls` to see folder exists
- `ls old-backup/` to see what's inside
- `rm -r old-backup` to delete
- `ls` to verify deletion
- Explanation of why each step matters

---

**Question 4: File Organization**

You have 20 HTML files mixed with JavaScript and CSS files in one folder. You need to organize them into `pages/`, `scripts/`, and `styles/` folders.

*Write the command sequence to organize these files.*

**Expected answer elements:**
- `mkdir pages scripts styles`
- `mv *.html pages/`
- `mv *.js scripts/`
- `mv *.css styles/`
- Verification commands: `ls pages/`, `ls scripts/`, `ls styles/`

---

**Question 5: Finding Specific Content**

Your project has 50 JavaScript files. You need to find which ones contain the function `calculateTotal`.

*What command finds all files containing this function, showing line numbers?*

**Expected answer elements:**
- `grep -rn "calculateTotal" .` or
- `grep -n "calculateTotal" *.js` or
- `grep -rn "calculateTotal" src/`
- Explanation of flags: `-r` (recursive), `-n` (line numbers)

---

**Question 6: Backup Before Changes**

Before making major changes, you want to create a complete backup of your `my-app` project folder.

*Write the command to create a backup called `my-app-backup`, assuming you're in the parent directory.*

**Expected answer elements:**
- `cp -r my-app my-app-backup`
- Explanation of why `-r` flag is required
- Verification: `ls`, `ls my-app-backup/`

---

**Question 7: Viewing File Content**

You need to check if a configuration file contains a specific setting, but the file is 500 lines long.

*What's the best way to: (a) quickly preview the file, (b) search for specific content?*

**Expected answer elements:**
- (a) `less config.txt` to view page by page, or `head config.txt` to preview
- (b) `grep "setting-name" config.txt` to find specific content
- Or: `less config.txt` then use `/setting-name` to search within `less`

---

**Question 8: Dangerous Command Recognition**

Your friend suggests running: `rm -rf *` to "clean up unnecessary files."

*Is this safe? Why or why not? What should you do instead?*

**Expected answer elements:**
- NOT SAFE—deletes EVERYTHING in current directory permanently
- Should: `ls` first to see what exists
- Should: Delete specific files/folders individually
- Should: Use `rm filename` for specific files, not wildcards without verification

---

**Question 9: Path Navigation**

You're in `/Users/yourname/Desktop/projects/website/src` and need to get to `/Users/yourname/Documents`.

*Write at least two different ways to navigate there.*

**Expected answer elements:**
- Absolute: `cd ~/Documents` or `cd /Users/yourname/Documents`
- Relative: `cd ../../../../Documents`
- Or: `cd ~`, then `cd Documents`

---

**Question 10: Command Verification**

You just ran `mkdir new-project` but want to make sure it actually created the folder.

*What command verifies this, and what should you look for in the output?*

**Expected answer elements:**
- `ls` or `ls -la`
- Should see `new-project` in the list
- Could also: `cd new-project` (if succeeds, folder exists)
- Could also: `ls -ld new-project` (shows just that folder)

---

**Evaluation Criteria:**

**Expert Level** (9-10 correct)
- Strong command line fundamentals
- Ready for Git and advanced terminal work
- Understands safety and verification patterns

**Proficient Level** (7-8 correct)
- Good understanding of core commands
- May need practice with `grep` or complex scenarios
- Ready to proceed with careful practice

**Developing Level** (5-6 correct)
- Basic commands understood
- Need more practice combining commands
- Should review file management and search commands

**Needs Review** (0-4 correct)
- Revisit core concepts
- Practice basic commands extensively
- Work through exercises again before proceeding

---

**Self-Reflection:**
1. Which commands feel most natural to you?
2. Which scenarios were most challenging?
3. What would you like more practice with?
4. How confident do you feel using the terminal daily?

---

## Section 05: Your Command Line Journey

### 05.0 Next Steps with the Terminal (~450 words)

**Content Outline:**

**What You've Accomplished**

Congratulations! You've mastered the 10 essential commands that professional developers use every single day. You started this course never having typed a terminal command, and now you can:

- Navigate any file system confidently (`pwd`, `cd`, `ls`)
- Create project structures from scratch (`mkdir`, `touch`)
- Manage files efficiently (`cp`, `mv`, `rm`)
- View and search content (`cat`, `less`, `head`, `grep`)
- Execute safe, verified command workflows
- Recognize and avoid dangerous command patterns

These commands form the foundation of professional development work. Every developer, regardless of their specialty, uses these exact commands daily.

**How This Connects to Your Journey**

Tomorrow you'll start learning Git for version control. Here's the connection: almost every Git operation uses the command line skills you learned today.

**Git uses these commands:**
- `cd` to navigate to your project
- `pwd` to verify you're in the right place
- `ls` to see your files
- `touch` to create new files to track
- `rm` to delete files from your project
- `mkdir` to organize your project structure

When you run `git add`, `git commit`, or `git push`, you're building on the foundation you created today.

**Beyond Git:**

**Development Servers:** Running `npm start`, `python app.py`, or `node server.js` all require understanding:
- Where you are (`pwd`)
- How to navigate there (`cd`)
- What files exist (`ls`)

**Deployment:** When you deploy applications to production:
- You'll SSH to remote servers (using these same commands)
- Navigate server file systems
- View logs with `less` and `grep`
- Manage configuration files

**Automation:** As you advance, you'll write shell scripts combining these commands to automate repetitive tasks—saving hours of manual work.

**Practice Recommendations**

**Daily Practice:**
Use the terminal for regular file management instead of graphical interfaces. The more you practice, the more automatic these commands become.

**Challenge Yourself:**
- Complete all file operations for a week using only terminal
- Time yourself doing common tasks (you'll get faster)
- Teach someone else these commands (teaching solidifies learning)

**Explore Further:**
- Learn about pipes (`|`) to chain commands together
- Explore command history (up arrow, `history` command)
- Try tab completion to speed up your typing
- Learn about command options with `man command` (manual pages)

**Key Mindset**

The terminal isn't a black box anymore—it's your tool. These 10 commands give you power and speed. Where clicking takes minutes, commands take seconds. Where graphical interfaces limit you, the terminal gives you precision and control.

**Your Next Steps**

Tomorrow: Git and version control (building directly on today's skills)  
Next week: Running development servers and using package managers  
Future: Deploying applications, managing remote servers, automating workflows

Every expert started exactly where you are now. The difference is practice and persistence. You now have the foundation—keep building on it.

Welcome to the world of command line proficiency. You're now equipped with the tools every developer needs. 🎉

---

**End of Course Outline**