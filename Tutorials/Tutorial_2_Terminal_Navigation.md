
# 🖥️ Tutorial 2: Terminal Navigation & File Management

Mastering the terminal is essential for efficient development and system management. This guide covers the most useful terminal commands for navigating and managing files and directories.

---

## 📂 Navigation

- **Current directory**:
```bash
pwd
```

- **List contents**:
```bash
ls
ls -l   # long format
ls -a   # include hidden files
```

- **Change directory**:
```bash
cd folder_name
cd ..       # up one directory
cd ~        # home directory
```

---

## 🗂️ Creating, Moving, Renaming, and Deleting Files and Folders

- **Create a directory**:
```bash
mkdir new_folder
```

- **Create a file**:
```bash
touch new_file.txt
```

- **Move a file or directory**:
```bash
mv source.txt destination_folder/
```

- **Rename a file or directory**:
```bash
mv old_name.txt new_name.txt
```

- **Copy a file**:
```bash
cp file.txt copy_file.txt
```

- **Copy a directory recursively**:
```bash
cp -r source_folder/ destination_folder/
```

- **Remove a file**:
```bash
rm file.txt
```

- **Remove a directory**:
```bash
rm -r folder_name/
```

---

## 📝 Opening Files from the Terminal

- **Open file in VS Code**:
```bash
code file.txt
```

- **Open with default application**:
```bash
xdg-open file.txt     # Linux
open file.txt         # macOS
start file.txt        # Windows
```

---

## 🖨️ Viewing File Content

- **Display contents**:
```bash
cat file.txt
```

- **View page by page**:
```bash
less file.txt
```

- **Show beginning of file**:
```bash
head file.txt
```

- **Show end of file**:
```bash
tail file.txt
```

---

## 🔍 Finding Files

- **Find by name**:
```bash
find . -name "file.txt"
```

- **Find by type**:
```bash
find . -type f        # files
find . -type d        # directories
```

- **Find and delete a file**:
```bash
find . -name "*.log" -delete
```

- **Find using regex (with `grep`)**:
```bash
grep -r "pattern" .
```

---

## ⚙️ Tips for Efficient Terminal Use

- Use `tab` to auto-complete file and folder names.
- Use `Ctrl + R` to search your command history.
- Combine commands with `&&` or `;` for more powerful workflows.



---

## 🌳 Viewing Directory Structure with `tree`

The `tree` command displays a visual representation of directory structures.

### Basic usage
```bash
tree path/target_directory_name
```

```bash
⚠️ If tree is not installed, install it with:

sudo apt install tree   # Ubuntu/Debian
brew install tree       # macOS (with Homebrew)
```


- Limit depth of folders displayed
```bash
tree -L 2
```

- List files with entered pattern
```bash
tree -P "*.txt"
```

- Show hidden files
```bash
tree -a
`or` 
tree --all
```

- List directories only.
```bash
tree -d
`or` 
tree --dirs-only
```

- Show file sizes: Print the size of each file along with the name.
```bash
tree -s
```

- Print the date of the last modification time for the file listed. 
```bash
tree -D
```

- Prints the full path prefix for each file. 
```bash
tree -f
`or` 
tree --full-path
```

---

Master these commands to become more productive and confident using the terminal in any development or system task.

**Stay efficient and code on! 🚀**
