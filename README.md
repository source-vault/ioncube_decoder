<div align="center">

# SourceVault PHP Decoder

**API-based PHP deobfuscator — download, configure, and run. No build required.**

[![Telegram](https://img.shields.io/badge/Telegram-@source__vault-2CA5E0?logo=telegram)](https://t.me/source_vault)
[![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20Linux%20%7C%20macOS%20%7C%20Android-blue)](#download)
[![PHP](https://img.shields.io/badge/PHP-4.0%20→%208.5-777BB4?logo=php)](#usage)

</div>

---

## What it does

Drop encoded / obfuscated PHP files into the `encoded/` folder, run the binary, and get clean decoded files in `decoded/` — preserving the full directory tree.

```
encoded/
├── index.php          ← obfuscated
└── app/
    └── core.php       ← obfuscated

       ↓  decoder --php 8.1  ↓

decoded/
├── index.php          ✓ decoded
└── app/
    └── core.php       ✓ decoded
```

---

## Download

> Pre-compiled static binaries — no installation, no dependencies.
> Download the file for your platform, make it executable, and run it.

### Latest release

| Platform | Architecture | Download |
|----------|-------------|---------|
| **Windows** | x64 (64-bit) | [decoder-windows-x64.exe.zip](https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-windows-x64.exe.zip) |
| **Windows** | x86 (32-bit) | [decoder-windows-x86.exe.zip](https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-windows-x86.exe.zip) |
| **Windows** | ARM64 | [decoder-windows-arm64.exe.zip](https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-windows-arm64.exe.zip) |
| **Linux** | x64 (64-bit) | [decoder-linux-x64.zip](https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-linux-x64.zip) |
| **Linux** | x86 (32-bit) | [decoder-linux-x86.zip](https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-linux-x86.zip) |
| **Linux** | ARM64 / Android | [decoder-linux-arm64.zip](https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-linux-arm64.zip) |
| **Linux** | ARM32 | [decoder-linux-arm32.zip](https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-linux-arm32.zip) |
| **Linux** | MIPS little-endian | [decoder-linux-mipsle.zip](https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-linux-mipsle.zip) |
| **Linux** | MIPS big-endian | [decoder-linux-mips.zip](https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-linux-mips.zip) |
| **Linux** | MIPS64 LE | [decoder-linux-mips64le.zip](https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-linux-mips64le.zip) |
| **Linux** | MIPS64 BE | [decoder-linux-mips64.zip](https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-linux-mips64.zip) |
| **Linux** | RISC-V 64 | [decoder-linux-riscv64.zip](https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-linux-riscv64.zip) |
| **Linux** | PowerPC 64 LE | [decoder-linux-ppc64le.zip](https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-linux-ppc64le.zip) |
| **Linux** | PowerPC 64 | [decoder-linux-ppc64.zip](https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-linux-ppc64.zip) |
| **Linux** | s390x (IBM Z) | [decoder-linux-s390x.zip](https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-linux-s390x.zip) |
| **macOS** | Intel (x64) | [decoder-macos-x64.zip](https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-macos-x64.zip) |
| **macOS** | Apple Silicon (ARM64) | [decoder-macos-arm64.zip](https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-macos-arm64.zip) |
| **FreeBSD** | x64 | [decoder-freebsd-x64.zip](https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-freebsd-x64.zip) |
| **FreeBSD** | ARM64 | [decoder-freebsd-arm64.zip](https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-freebsd-arm64.zip) |
| **NetBSD** | x64 | [decoder-netbsd-x64.zip](https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-netbsd-x64.zip) |
| **OpenBSD** | x64 | [decoder-openbsd-x64.zip](https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-openbsd-x64.zip) |
| **Solaris** | x64 | [decoder-solaris-x64.zip](https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-solaris-x64.zip) |
| **Plan 9** | x64 | [decoder-plan9-x64.zip](https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-plan9-x64.zip) |
| **WebAssembly** | WASI | [decoder-wasip1.wasm.zip](https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-wasip1.wasm.zip) |
| 📦 **All platforms** | combined bundle | [decoder-bundle.zip](https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-bundle.zip) |

---

## Quick Start

### Step 1 — Download & extract

**Windows (PowerShell)**
```powershell
# Download
Invoke-WebRequest -Uri "https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-windows-x64.exe.zip" -OutFile decoder.zip
Expand-Archive decoder.zip .
```

**Linux / macOS (bash)**
```bash
# Download
curl -L "https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-linux-x64.zip" -o decoder.zip
unzip decoder.zip
chmod +x decoder-linux-x64
```

### Step 2 — Create `config.ini`

Create a file named `config.ini` in the same directory as the binary:

```ini
# SourceVault PHP Decoder — config
api_key=YOUR_API_KEY_HERE
telegram_id=@your_telegram_id
```

> **Get your API key →** join **[@source_vault](https://t.me/source_vault/)** on Telegram.

### Step 3 — Put encoded files in `encoded/`

The `encoded/` and `decoded/` directories are created automatically on first run.
Just copy your obfuscated PHP files there — subdirectories are fully supported.

```
your-folder/
├── decoder.exe        (or decoder-linux-x64, decoder-macos-arm64 …)
├── config.ini
├── encoded/
│   └── your-files.php
└── decoded/           ← created automatically
```

### Step 4 — Run

```bash
# Default PHP version (7.4)
./decoder

# Specify PHP version
./decoder --php 8.1
./decoder -p 5.6

# Help
./decoder --help
```

---

## Supported PHP Versions

| Range | Versions |
|-------|---------|
| PHP 4.x | `4.0` `4.1` `4.2` `4.3` `4.4` |
| PHP 5.x | `5.0` `5.1` `5.2` `5.3` `5.4` `5.5` `5.6` |
| PHP 7.x | `7.0` `7.1` `7.2` `7.3` `7.4` |
| PHP 8.x | `8.0` `8.1` `8.2` `8.3` `8.4` `8.5` |

Default version: **7.4**

---

## Usage Reference

```
Usage: decoder [--php <version>] [-p <version>] [--help]

Options:
  --php, -p <ver>   PHP version to use for decoding
                    Supported: 4.0-4.4, 5.0-5.6, 7.0-7.4, 8.0-8.5
                    Default  : 7.4
  --help, -h        Show this help message
```

### Example output

```
================================================
  SourceVault PHP Decoder  |  PHP 8.1
================================================

[*] Source  : encoded/
[*] Output  : decoded/
[*] PHP ver : 8.1

[1] encoded/index.php
     [OK]  -> decoded/index.php
[2] encoded/app/core.php
     [OK]  -> decoded/app/core.php
[3] encoded/old/legacy.php
     [ERR] HTTP 400 — unsupported encoding format

================================================
  Done!  Total: 3  |  OK: 2  |  Failed: 1
================================================
```

---

## Error Reference

| Error | Meaning |
|-------|---------|
| `Config file 'config.ini' not found` | Create `config.ini` next to the binary |
| `api_key not found` | Add `api_key=...` to `config.ini` |
| `invalid api_key (HTTP 403)` | Your key is wrong or expired — get a new one from [@source_vault](https://t.me/source_vault/) |
| `unauthorized (HTTP 401)` | Key present but rejected — check for typos |
| `HTTP 400` | File format not recognized by the API |
| `HTTP request failed` | Network error — check internet connection |
| `empty response from API` | API returned no content — try again |

---

## Exit Codes

| Code | Meaning |
|------|---------|
| `0` | All files decoded successfully |
| `1` | Configuration or argument error |
| `2` | One or more files failed to decode |

---

## API

| | |
|--|--|
| **Endpoint** | `https://api.sourcevault.eu.cc/decode` |
| **Method** | `POST multipart/form-data` |
| **Auth** | `Authorization: Bearer <api_key>` |
| **Fields** | `file` (binary), `php_version` (string), `telegram_id` (string, optional) |

---

## Support & API Key

Join the Telegram channel to get your API key and report issues:

**➜ [@source_vault](https://t.me/source_vault/)**

---

<div align="center">
<sub>SourceVault PHP Decoder — pre-built static binaries, no source required</sub>
</div>
