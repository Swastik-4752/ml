# ml — Machine Learning practical loader

Students type one command in any terminal, pick a practical number, and the full
code is printed in that same terminal, copied to the clipboard, and saved as a file.

Then it asks **"Run practical now? (y/N)"**. On `y` it installs the Python packages,
creates the `.py` file and runs it in a NEW terminal window (Git Bash on Windows), and
closes the window the student started from. Practicals marked **(needs CSV)** read the
teacher's CSV file: put it in the folder first, then run. Graphs open in
their own window: close each one to let the program continue. `ml 2.1` (number given
up front) only shows and saves — it never runs anything.

| Where | Command |
|---|---|
| Windows PowerShell | `irm https://swastik-4752.github.io/ml/w.txt \| iex` |
| Windows cmd | `powershell -c "irm https://swastik-4752.github.io/ml/w.txt \| iex"` |
| Linux / macOS / Git Bash | `curl -fsSL https://swastik-4752.github.io/ml/l.txt \| bash` |
| Any terminal, no menu | `curl -fsSL https://swastik-4752.github.io/ml/7.txt` (prints practical 7; use `curl.exe` in PowerShell) |
| Install `ml` on Windows (once) | `irm https://swastik-4752.github.io/ml/install.txt \| iex` → then `ml` or `ml 7` |

Linux/macOS shortcut: add to `~/.bashrc` → `alias ml='curl -fsSL https://swastik-4752.github.io/ml/l.txt | bash -s'`

Needs Python 3 with pip on the PATH, and Git for Windows (for Git Bash) to use "Run practical now".

## Files

| File | What it is |
|---|---|
| `list.txt` | The menu: `number \| title \| file name it is saved as` |
| `1.txt`, `2.1.txt`, … | The code for each practical |
| `data/` | The CSV datasets the practicals download |
| `w.txt` | Windows loader (PowerShell) |
| `l.txt` | Linux / macOS loader (bash) |
| `run.txt` | Runner: writes a practical's files and runs its commands (bash) |
| `install.txt` | Puts an `ml.cmd` on the Windows PATH |
| `index.html` | Web page with copy buttons and the practical list |

Practical file format the runner reads: `# ----- file.py -----` starts a file,
`# ----- Commands -----` starts commands (also the default), a header with spaces in it
is notes only, and the comment `# create ... then:` in the commands is where the files get written.

## Adding a practical

1. Put the code in `11.txt` (any number, `11.1` works too). Datasets go in `data/`.
2. Add a line to `list.txt`: `11 | Title of practical | ml11_name.txt`
3. Push to GitHub. Students get it on their next run — nothing to reinstall.

## Hosting (free, GitHub Pages)

Live at https://swastik-4752.github.io/ml (GitHub Pages, `main` branch, root).
A push to `main` updates the site in about a minute.
