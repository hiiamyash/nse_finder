# 🔎 Script Finder – Advanced Nmap Script Search Tool

NSE Finder is a command-line tool built in **Bash** to help penetration testers and red teamers quickly find relevant [Nmap Scripting Engine (NSE)](https://nmap.org/book/nse.html) scripts.  
Instead of digging through `/usr/share/nmap/scripts/` or grepping `script.db` manually, Script Finder makes NSE discovery **fast, filtered, and operator-friendly**.

---

## ✨ Features

- Search NSE scripts by **keyword** (`-k`)  
- Search by **categories** (`-c`) with support for:
  - **AND mode (default):** script must belong to all specified categories
  - **OR mode:** script can belong to any of the categories
- Color-coded, formatted output for quick scanning
- Displays **script paths and categories**
- Lists all available **keywords and categories**
- Flexible: combine `-k` and `-c` for precision searches

---

## ⚡ Installation

Clone or download this repo, then make the script executable:

```bash
git clone https://github.com/<yourusername>/script-finder.git
cd script-finder
chmod +x script.sh
```
## Ensure Nmap is installed and the script.db path is correct:

```bash
sudo apt install nmap
```Do you want me to also create a Sample Output table (with example results for one command) so the README shows exactly what to expect?
## Default path:

```
/usr/share/nmap/scripts/script.db
```
### Update SCRIPT_DB in the script if your path differs.

## 🚀 Usage

```bash
./script.sh [options]
```
### Options

| Option            | Description                                                                 |
|-------------------|-----------------------------------------------------------------------------|
| `-k <keyword>`    | Search scripts by keyword (matches script name or description)              |
| `-c <categories>` | Search within categories. Use commas for multiple categories.               |
| `--cat-mode or`   | Switch category search from **AND** (default) to **OR** mode.               |
| `-h, --help`      | Show help and list available keywords/categories.                           |

## 🎯 Examples

| Example | Command                                                                 |
|---------|-------------------------------------------------------------------------|
| **1. Find SMB scripts in both `discovery` AND `default`** | `./script.sh -k smb -c discovery,default` |
| **2. Find SMB scripts in `discovery` OR `default`**       | `./script.sh -k smb -c discovery,default --cat-mode or` |
| **3. Find all scripts in the `vuln` category**            | `./script.sh -c vuln` |
| **4. Simple keyword search for `http-title`**             | `./script.sh -k http-title` |


