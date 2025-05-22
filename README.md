# Showfile

`showfile` is a Bash script that allows you to display the contents of files based on various criteria such as directory, file extension, name, size, or a specific list of files. It also supports copying the output to the system clipboard for easy use.

## Features
- Search files in a specified directory (default: current directory).
- Filter files by extension, name (substring), or minimum size (in KB).
- Process specific files provided in a comma-separated list.
- Identify and display text files while skipping binary/non-text files.
- Optionally copy the output to the system clipboard.
- Cross-platform clipboard support (macOS, Linux, Windows WSL).

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/slashotw/showfile.git
   ```
2. Navigate to the repository directory:
   ```bash
   cd showfile
   ```
3. Make the script executable:
   ```bash
   chmod +x showfile
   ```
4. Optionally, move the script to a directory in your PATH (e.g., `/usr/local/bin`) for global access:
   ```bash
   sudo mv showfile /usr/local/bin/
   ```

## Usage
```bash
showfile [OPTIONS]
```

### Options
- `-d, --directory DIR`  
  Specify the directory to search (default: current directory).
- `-e, --extension EXT`  
  Filter files by extension (e.g., `.txt`, `.conf`).
- `-n, --name NAME`  
  Filter files by name (substring match).
- `-s, --size SIZE`  
  Filter files larger than SIZE (in KB).
- `-f, --files FILES`  
  Specify a comma-separated list of file names to search for.
- `-c, --copy`  
  Copy the output to the system clipboard.
- `-h, --help`  
  Display the help message.

### Examples
1. Display all `.txt` files larger than 100 KB in `/path/to/dir`:
   ```bash
   showfile -d /path/to/dir -e .txt -s 100
   ```
2. Display files containing "config" in their name and copy the output to the clipboard:
   ```bash
   showfile -n config -c
   ```
3. Display specific files (`file1.txt` and `file2.conf`) in the current directory:
   ```bash
   showfile -f file1.txt,file2.conf
   ```

## Dependencies
- **Core utilities**: `bash`, `find`, `file`, `cat`, `tr` (typically pre-installed on Unix-like systems).
- **Clipboard utilities** (optional, for `-c` option):
  - `pbcopy` (macOS, pre-installed).
  - `xclip` or `xsel` (Linux, install via package manager, e.g., `sudo apt install xclip`).
  - `clip.exe` (Windows WSL, pre-installed).

## Notes
- The script checks if a file is text-based before displaying its contents. Binary or non-text files will show a placeholder message.
- The output is saved to a temporary file during processing and automatically deleted afterward.
- Ensure the specified directory and files are accessible to avoid permission errors.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Contributing
Contributions are welcome! Please submit a pull request or open an issue on the [GitHub repository](https://github.com/slashotw/showfile).

