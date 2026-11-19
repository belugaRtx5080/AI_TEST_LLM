```text
Analyze the entire codebase in the current working directory thoroughly.

Execution Rules:
1. Explore & Read:
   - List all files and folders in the project, strictly ignoring `.git`, `build`, `dist`, `target`, `node_modules`, `__pycache__`, `.venv`, vendor/submodules, binary assets (images, fonts, audio, archives), and ANY license or legal text files (`LICENSE*`, `COPYING*`, `gpl*`, `mit*`, `apache*`, `*.txt` license texts — DO NOT open or read license files).
   - Focus on build configurations (`CMakeLists.txt`, `Makefile`, `package.json`, `Cargo.toml`, `*.pro`, etc.), entry points, core source modules, UI/rendering files, and tests.
   - Delegate file inspection and sub-module summaries to the @general subagent to keep the main context clean.

2. Comprehensive Report:
   - **Project Overview:** What this project does, its detected tech stack, build system, and main entry points.
   - **Directory & File Structure:** Output a clean ASCII tree of the analyzed project files with a concise 1-line description of each file's responsibility.
   - **Architecture & Data Flow (ASCII Diagram + Explanation):** Draw a clean, well-formatted ASCII box-and-arrow architecture diagram showing the main layers/modules, external dependencies, and how data or control flows between them, followed by a brief explanation.
   - **Code Quality & Potential Issues:** Point out any bugs, missing error handling, platform constraints, hardcoded assumptions, or architectural improvements.

3. Exact Token & Cost Calculation (NO GUESSING):
   - Before writing your final response, use your bash tool to fetch the REAL token metrics from the latest OpenCode session using this exact one-liner:
     `python3 -c "import sqlite3, os; db=os.path.expanduser('~/.local/share/opencode/opencode.db'); c=sqlite3.connect(db).cursor(); print(c.execute('SELECT json_extract(data, \"$.tokens\") FROM message WHERE json_extract(data, \"$.tokens\") IS NOT NULL ORDER BY rowid DESC LIMIT 25').fetchall())"`
   - Sum up the actual **Input tokens**, **Output tokens**, **Cache Read tokens**, and **Cache Write tokens** from that output (if the query returns empty or fails, explicitly state that exact metrics were unavailable instead of guessing).
   - Calculate the equivalent API cost assuming **$0.10 per 1,000,000 tokens** for both Input and Output (and include Cache Read/Write in the total token count). Show the exact math formula and final USD amount.
```
