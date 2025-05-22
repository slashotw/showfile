Showfile
showfile is a Bash script that allows you to display the contents of files based on various criteria such as directory, file extension, name, size, or a specific list of files. It also supports copying the output to the system clipboard for easy use.
Features

Search files in a specified directory (default: current directory).
Filter files by extension, name (substring), or minimum size (in KB).
Process specific files provided in a comma-separated list.
Identify and display text files while skipping binary/non-text files.
Optionally copy the output to the system clipboard.
Cross-platform clipboard support (macOS, Linux, Windows WSL).

Installation

Clone the repository:git clone https://github.com/slashotw/showfile.git


Navigate to the repository directory:cd showfile


Make the script executable:chmod +x showfile


Optionally, move the script to a directory in your PATH (e.g., /usr/local/bin) for global access:sudo mv showfile /usr/local/bin/



Usage
showfile [OPTIONS]

Options

-d, --directory DIRSpecify the directory to search (default: current directory).
-e, --extension EXTFilter files by extension (e.g., .txt, .conf).
-n, --name NAMEFilter files by name (substring match).
-s, --size SIZEFilter files larger than SIZE (in KB).
-f, --files FILESSpecify a comma-separated list of file names to search for.
-c, --copyCopy the output to the system clipboard.
-h, --helpDisplay the help message.

Examples

Display all .txt files larger than 100 KB in /path/to/dir:showfile -d /path/to/dir -e .txt -s 100


Display files containing "config" in their name and copy the output to the clipboard:showfile -n config -c


Display specific files (file1.txt and file2.conf) in the current directory:showfile -f file1.txt,file2.conf



Dependencies

Core utilities: bash, find, file, cat, tr (typically pre-installed on Unix-like systems).
Clipboard utilities (optional, for -c option):
pbcopy (macOS, pre-installed).
xclip or xsel (Linux, install via package manager, e.g., sudo apt install xclip).
clip.exe (Windows WSL, pre-installed).



Notes

The script checks if a file is text-based before displaying its contents. Binary or non-text files will show a placeholder message.
The output is saved to a temporary file during processing and automatically deleted afterward.
Ensure the specified directory and files are accessible to avoid permission errors.

License
This project is licensed under the MIT License. See the LICENSE file for details.
Contributing
Contributions are welcome! Please submit a pull request or open an issue on the GitHub repository.
