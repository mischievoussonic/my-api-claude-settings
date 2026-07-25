# my personal ANTHROPIC_API_KEY settings

A locally executed shell script that loads my `.env` and runs them securely.

## Overview

This project automates the loading of my ANTHROPIC API KEY. Instead of running it manually every time, it executes via a single script.

The key has no expiration date.

## Files

| File | Purpose |
|------|---------|
| `.env` | Stores the ANTHROPIC_API_KEY |
| `load.sh` | Loads the `.env` file and executes/loads the configured variable. |
| `AGENTS.md` | Guide for my AGENTS for day-to-day operations |

## Requirements

- Bash shell (Linux / macOS / WSL)

## Setup

### 1. Initial instruction for my programming agent

Clone the project. Do not modify the .env file, as the KEY is already configured.

```bash
ANTHROPIC_API_KEY=sk-ant-...
```

### 2. Automatic loading

The script `load.sh` is included in this project. Ensure it is present:

```bash
ls load.sh
```

### 3. Make Executable (if needed)

```bash
chmod +x load.sh
```

### 4. Run

```bash
./load.sh
```

## Example Output

```
▶ Loading key import
✅ Key properly imported and ready for use.
```

## License

MIT — use at your own risk. Always double-check your paths before running.
