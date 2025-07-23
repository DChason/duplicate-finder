<h2 align="center">
    <img height="200" alt="duplicate-finder" src="images/header-duplicate-finder.png" />
    <br>
    duplicate-finder: for when “copy-paste” gets out of hand.
</h2>

---

<div align="center">

<a href="https://www.python.org/downloads/"><img src="https://img.shields.io/badge/python-3.6%2B-blue.svg" alt="Python 3.6+ supported"></a>
[![Last Commit](https://img.shields.io/github/last-commit/DChason/duplicate-finder.svg)](https://github.com/DChason/duplicate-finder/commits/main)
[![Issues](https://img.shields.io/github/issues/DChason/duplicate-finder.svg)](https://github.com/DChason/duplicate-finder/issues)
[![GitHub stars](https://img.shields.io/github/stars/DChason/duplicate-finder.svg)](https://github.com/DChason/duplicate-finder/stargazers)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Follow on LinkedIn](https://img.shields.io/badge/Follow%20me-LinkedIn-blue?logo=linkedin)](https://www.linkedin.com/in/damienchason/)

</div>

**duplicate-finder** is a command-line utility for identifying possible duplicate files across one or more directories. It works by first grouping files by size, then comparing their contents using cryptographic hashes (default: sha256) for accuracy and efficiency. Use it to reclaim disk space, reduce clutter, and keep your storage organized.

- Scans one or more directories for duplicate files
- Includes/excludes hidden files with the `-i` flag
- Cross-platform: works on Linux, macOS, and Windows

---

## Installation (Linux or macOS)

**Recommended:**
Clone the repository and copy `duplicate-finder` to a directory in your PATH:

```sh
git clone https://github.com/DChason/duplicate-finder.git
cd duplicate-finder
cp duplicate-finder /usr/local/bin/
chmod +x /usr/local/bin/duplicate-finder
```
<br>

**Alternative:**
Download directly via `wget` or `curl`:

```sh
wget https://raw.githubusercontent.com/DChason/duplicate-finder/main/duplicate-finder -O /usr/local/bin/duplicate-finder
chmod +x /usr/local/bin/duplicate-finder
```

or

```sh
curl -o /usr/local/bin/duplicate-finder https://raw.githubusercontent.com/DChason/duplicate-finder/main/duplicate-finder
chmod +x /usr/local/bin/duplicate-finder
```

---

## Flags & Options

```sh
duplicate-finder [-h] [-a HASH_ALGO] [-b BUFFER_SIZE] [-i] -d DIRECTORY [-d DIRECTORY ...]
```

- `-h`, `--help`
  - Show help message and exit.
- `-d`, `--directory DIR`
  - Directory to search. Can be specified multiple times.
  - Defaults to current directory if not given.
- `-a`, `--algorithm ALG`
  - Hash algorithm to use for file comparison (default: sha256).
- `-b`, `--buffer-size N`
  - Buffer size in bytes for file reading (default: 65536).
- `-i`, `--include-hidden`
  - Include hidden files in the search.

---

## Example Usage

Find duplicate files in two directories, including hidden files:

```sh
duplicate-finder -d ~/Downloads -d ~/Documents -i
```

Use a different hash algorithm and buffer size:

```sh
duplicate-finder -d . -a md5 -b 131072
```

---

## License

MIT License. See [LICENSE](LICENSE) for details.

---
