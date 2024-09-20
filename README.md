# Windows Server Folder Detective 🕵️‍♂️

[![PowerShell 7](https://img.shields.io/badge/PowerShell-7+-blue.svg)](https://github.com/PowerShell/PowerShell)
[![License: Unlicense](https://img.shields.io/badge/License-Unlicense-green.svg)](https://unlicense.org/)

**🔍 Uncover storage hogs on your Windows systems with ease!**

**Windows Folder Detective** is a PowerShell script that swiftly analyzes your drives, pinpointing large folders and helping you reclaim valuable disk space. Ideal for both casual users and enterprise environments, it's especially useful for **Windows Server** where finding free tier tools can be challenging.

## 🎯 Key Features

- **🚀 Lightning-fast analysis** with dynamic parallel processing (on PowerShell 7+)
- **📊 Real-time progress tracking** while analyzing thousands of folders
- **🗂️ Instant detection and reporting** of folders taking up more than 1GB
- **💻 Compatible with** Windows 7/Server 2008 R2 and newer
- **🛠️ Works in older versions of PowerShell** with legacy sequential processing

## 🚀 Quick Start Guide

### 1️⃣ Prerequisites

- **PowerShell** version 5.1+ for legacy mode, **PowerShell 7+** for parallel processing.
- **Administrator privileges** are required to access system folders and run the script.

### 2️⃣ Running the Script

1. **Clone the repository** or download the script:
   ```bash
   git clone https://github.com/your-repo/windows-folder-detective.git
   cd windows-folder-detective
   ```

2. Run the script in PowerShell with administrator privileges:

   ```powershell
   ./FolderDetective.ps1
   ```

   Example for analyzing C:\ drive:

   ```powershell
   $Path = "C:\"
   ./FolderDetective.ps1 -Path $Path
   ```

### 3️⃣ Output

- **Progress**: Real-time progress shown in the console as it analyzes folders.
- **Results**: Folders larger than 1GB are listed in the terminal and saved to a CSV file called `LargeFolders.csv`.

## 💡 How It Works

Windows Folder Detective performs a recursive scan of the specified path, excluding critical system directories (like C:\Windows, Program Files, etc.). It identifies folders larger than 1GB and outputs the results in a CSV file and a formatted table within the terminal.

**Dual-mode processing:**

- **PowerShell 7+**: Utilizes parallel processing to significantly speed up the analysis of large file systems.
- **PowerShell 5.1 and below**: Uses sequential processing to ensure compatibility with older environments.

## 📊 Example Output

```
Obteniendo la lista de carpetas...
Total de carpetas a analizar: 3554
PowerShell 7 detectado. Utilizando procesamiento en paralelo.

Carpeta grande encontrada: C:\Example\BigFolder - 12.34 GB
Carpeta grande encontrada: C:\Example\AnotherFolder - 8.76 GB

Análisis completado. Total de carpetas analizadas: 3554
```

The `LargeFolders.csv` will look like this:

| Path | Size |
|------|------|
| C:\Example\BigFolder | 12.34 GB |
| C:\Example\AnotherFolder | 8.76 GB |

## 🛠️ Configuration

- **Path Parameter**: You can specify any drive or folder path to analyze:

  ```powershell
  $Path = "D:\"
  ./FolderDetective.ps1 -Path $Path
  ```

- **Excluded Folders**: The script automatically excludes critical system directories, such as:
  - C:\Windows
  - C:\Program Files
  - C:\ProgramData
  - C:\Users\[User]\AppData

## 👥 Contributors

- Me - Creator and maintainer

Feel free to contribute by submitting pull requests, issues, or feature requests!

## 📄 License

This is free and unencumbered software released into the public domain. See the [Unlicense](https://unlicense.org/) for more details.

```
This is free and unencumbered software released into the public domain.

Anyone is free to copy, modify, publish, use, compile, sell, or distribute this 
software, either in source code form or as a compiled binary, for any purpose, 
commercial or non-commercial, and by any means.

In jurisdictions that recognize copyright laws, the author or authors of this 
software dedicate any and all copyright interest in the software to the public 
domain. We make this dedication for the benefit of the public at large and to 
the detriment of our heirs and successors. We intend this dedication to be an 
overt act of relinquishment in perpetuity of all present and future rights to 
this software under copyright law.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR 
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, 
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE 
AUTHORS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN 
ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION 
WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
```

## 📢 Feedback & Support

If you encounter any issues or have suggestions for improvements, please open an issue.
