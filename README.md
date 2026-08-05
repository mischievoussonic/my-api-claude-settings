<div align="center">

# Personal API Environment Loader

<p>
  A lightweight Bash utility to securely load my local API credentials from a 
  <code>.env</code> file into the current shell session.
</p>

<p>
  <img src="https://img.shields.io/badge/Shell-Bash-4EAA25?logo=gnu-bash&logoColor=white" alt="Bash">
  <img src="https://img.shields.io/badge/Platform-Linux%20%7C%20macOS%20%7C%20WSL-blue" alt="Supported platforms">
  <img src="https://img.shields.io/badge/License-MIT-yellow.svg" alt="MIT License">
</p>

</div>

---

## Overview

This project provides a simple local workflow for loading my Anthropic API key from a `.env` file.

Instead of manually exporting the environment variable whenever a new terminal session is opened, the included `load.sh` script loads the configured values into the current shell environment.

The project is intentionally minimal and contains no external dependencies.

## Project Structure

| File        | Purpose                                                           |
| ----------- | ----------------------------------------------------------------- |
| `.env`      | Stores the local `ANTHROPIC_API_KEY` value. 
| `load.sh`   | Validates and loads the environment variables                     |
| `AGENTS.md` | Operational instructions for programming agents                   |
| `README.md` | Project documentation                                             |

## Requirements

* Bash
* Linux, macOS or Windows Subsystem for Linux

No package installation is required.

## Installation

### 1. Clone the repository

```bash
git clone https://github.com/mischievoussonic/my-api-claude-settings.git
cd my-api-claude-settings
```

Replace the placeholders with the URL and directory name of your repository.

### 2. Make the script executable

```bash
chmod 700 load.sh
```

## Usage

Load the API key into the current shell session:

```bash
source ./load.sh
```

The `source` command is required when the variable must remain available in the current terminal after the script finishes.

You can also use the shorter Bash syntax:

```bash
. ./load.sh
```

## Verification

Confirm that the variable was loaded without displaying the API key:

```bash
if [[ -n "${ANTHROPIC_API_KEY:-}" ]]; then
  echo "API key loaded successfully."
else
  echo "API key is not available."
fi
```

Example output:

```text
▶ Loading environment variables
✓ My API key loaded successfully
```

## Troubleshooting

<details>
<summary><strong>Permission denied when running the script</strong></summary>

Make the script executable:

```bash
chmod 700 load.sh
```

Then load it again:

```bash
source ./load.sh
```

</details>

<details>
<summary><strong>The API key disappears after the script finishes</strong></summary>

Running the script as a separate process does not modify the parent shell environment:

```bash
./load.sh
```

Load it into the current shell instead:

```bash
source ./load.sh
```

</details>

<details>
<summary><strong>The API key was not loaded</strong></summary>

Confirm that `.env` exists:

```bash
test -f .env && echo ".env found" || echo ".env not found"
```

</details>

## License

Distributed under the MIT License.

Use this project at your own risk and review scripts before executing them in your environment.

---

<div align="center">

Created for a simple, local, and secure API development workflow for my day-to-day work.

</div>
