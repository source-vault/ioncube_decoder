<div align="center">

# SourceVault ionCube Decoder

**Official ionCube PHP Decoder CLI — download, configure, and run. No build or dependencies required.**

[![Telegram](https://img.shields.io/badge/Telegram-@source__vault-2CA5E0?logo=telegram)](https://t.me/source_vault)
[![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20Linux%20%7C%20macOS%20%7C%20FreeBSD-blue)](#download)
[![PHP](https://img.shields.io/badge/PHP-5%20%7C%207%20%7C%208-777BB4?logo=php)](#supported-php-versions)

</div>

---

## What it does

Provide your ionCube protected PHP files or whole project folders, run the binary, and get clean, restored PHP source files — preserving the complete directory structure.

```
encoded/
├── index.php          ← ionCube protected bytecode
└── app/
    └── core.php       ← ionCube protected bytecode

       ↓  decoder -i encoded/ -o decoded/ -type ioncube -php 8  ↓

decoded/
├── index.php          ✓ clean PHP source
└── app/
    └── core.php       ✓ clean PHP source
```

---

## Download

> Pre-compiled static binaries — no installation, no dependencies.
> Download the archive for your operating system, extract, and run.

### Latest release

| Platform | Architecture | Binary in Zip | Download Link |
|----------|-------------|---------------|---------------|
| **Windows** | x64 (64-bit) | `decoder.exe` | [decoder-windows-amd64.zip](https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-windows-amd64.zip) |
| **Windows** | x86 (32-bit) | `decoder.exe` | [decoder-windows-386.zip](https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-windows-386.zip) |
| **Windows** | ARM64 | `decoder.exe` | [decoder-windows-arm64.zip](https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-windows-arm64.zip) |
| **Linux** | x64 (64-bit) | `decoder` | [decoder-linux-amd64.zip](https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-linux-amd64.zip) |
| **Linux** | x86 (32-bit) | `decoder` | [decoder-linux-386.zip](https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-linux-386.zip) |
| **Linux** | ARM64 (aarch64) | `decoder` | [decoder-linux-arm64.zip](https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-linux-arm64.zip) |
| **Linux** | ARM32 (ARMv7) | `decoder` | [decoder-linux-armv7.zip](https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-linux-armv7.zip) |
| **macOS** | Intel (x64) | `decoder` | [decoder-darwin-amd64.zip](https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-darwin-amd64.zip) |
| **macOS** | Apple Silicon (M1/M2/M3/M4) | `decoder` | [decoder-darwin-arm64.zip](https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-darwin-arm64.zip) |
| **FreeBSD** | x64 (64-bit) | `decoder` | [decoder-freebsd-amd64.zip](https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-freebsd-amd64.zip) |

---

## Quick Start

### Step 1 — Download & Extract

**Windows (PowerShell)**
```powershell
# Download
Invoke-WebRequest -Uri "https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-windows-amd64.zip" -OutFile decoder.zip
Expand-Archive decoder.zip .
cd decoder-windows-amd64
```

**Linux / macOS (Terminal)**
```bash
# Download
curl -L "https://github.com/source-vault/ioncube_decoder/raw/refs/heads/main/decoders/decoder-linux-amd64.zip" -o decoder.zip
unzip decoder.zip
cd decoder-linux-amd64
chmod +x decoder
```

### Step 2 — Configure API Key

Save your key once so you don't need to pass it every time:

```bash
./decoder config -key YOUR_API_KEY_HERE
```

Or set the environment variable:

```bash
export SOURCEVAULT_API_KEY="YOUR_API_KEY_HERE"
```

> **Get your key & credits →** Join **[@source_vault](https://t.me/source_vault)** on Telegram.

### Step 3 — Decode Files

#### Decode a single PHP file
```bash
./decoder -i encrypted_script.php -o clean_script.php -type ioncube -php 8
```

#### Decode an entire folder or project
```bash
./decoder -i ./protected_app -o ./decoded_app -type ioncube -php 8 -concurrency 4
```

#### Check account credit balance
```bash
./decoder credits
```

#### Test connectivity
```bash
./decoder ping
```

---

## Command-Line Options

```text
USAGE:
    decoder [flags] <command> [arguments]
    decoder -i <input_path> [-o <output_path>] [flags]

COMMANDS:
    decode <path>       Decode a single PHP script or an entire directory
    credits, balance    Show your remaining account credits and expiry
    ping                Test service connectivity and verify your API key
    config              View or update saved API key and default preferences
    version             Display version information
    help                Show help screen

FLAGS:
    -i, -input <path>     Path to encoded PHP file or folder to decode
    -o, -output <path>    Output destination file or folder
    -key <api_key>        SourceVault API Key (or env SOURCEVAULT_API_KEY)
    -type <decoder>       Decoder type: ioncube, zend, sourceguardian (default: ioncube)
    -php <version>        PHP target version: 8, 7, 5 (default: 8)
    -concurrency <n>      Concurrent workers for directory decoding (default: 4)
    -timeout <sec>        Timeout in seconds per file waiting in queue (default: 180)
    -save-key             Save the provided key to ~/.sourcevault/config.json
    -v, -verbose          Enable verbose debug logging
```

---

## Supported PHP Versions

| Major Version | Flag Value | Target Runtime |
|---|---|---|
| **PHP 8.x** | `-php 8` (default) | PHP 8.0, 8.1, 8.2, 8.3, 8.4 |
| **PHP 7.x** | `-php 7` | PHP 7.0, 7.1, 7.2, 7.3, 7.4 |
| **PHP 5.x** | `-php 5` | PHP 5.4, 5.5, 5.6 |

---

## Support & Community

Join our official Telegram channel for updates, credits, and support:

**➜ [@source_vault](https://t.me/source_vault)**

---

<div align="center">
<sub>SourceVault — High-Performance Cross-Platform Decoders</sub>
</div>
