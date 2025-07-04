# PyInstaller Extractor (pyinstxtractor)

This script allows you to **extract contents of a PyInstaller-generated executable (.exe)** back into its constituent files (e.g., `.pyc`, `.pyz`, etc.), enabling reverse engineering and static analysis of packaged Python applications.

> 🛠️ Maintained and shared by **Ömer Faruk Günay** for research and educational use.

## 🚀 Features

- Supports **PyInstaller versions 2.0 up to 3.6+**
- Extracts Python bytecode `.pyc` files
- Extracts and decompresses embedded `.pyz` archives
- Automatically fixes corrupted or missing `.pyc` headers
- Works with both Python 2.x and 3.x
- Creates a dedicated extraction directory for safe output

## 📦 Usage

Copy `pyinstxtractor.py` to the folder containing the `.exe` file and run it like this:

```bash
python pyinstxtractor.py yourfile.exe
```

A folder named `yourfile.exe_extracted/` will be created containing the extracted files.

> You can now use tools like [uncompyle6](https://github.com/rocky/python-uncompyle6) to decompile the `.pyc` files back into `.py` source code.

## 🧠 Example

```bash
$ python pyinstxtractor.py sample.exe
[+] Processing sample.exe
[+] Pyinstaller version: 3.6
[+] Python version: 3.8
[+] Found 14 files in CArchive
[+] Beginning extraction...please standby
...
[+] Successfully extracted pyinstaller archive: sample.exe
```

## ⚠️ Notes

- If `.pyz` extraction fails due to Python version mismatch, try running the script with the same Python version used to build the executable.
- Encrypted `.pyz` contents will be dumped as-is.

## 📜 Changelog (Summary)

- **v2.0**: Python 3.7/3.8 and PyInstaller 3.6 support added
- **v1.9 and earlier**: Compatibility with 2.0 through 3.3, subdir support, header fixes, etc.

## 📁 License

This project is open-source and free to use for educational or security research purposes.

---

Made with by [@ofarukgunay](https://github.com/ofarukgunay)
