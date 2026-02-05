# simple-rust-template

<div align="left">

[![Rust](https://img.shields.io/badge/Rust-000000?style=flat&logo=rust&logoColor=white)](https://www.rust-lang.org/)

</div>

A simple Rust project template for single-package applications.

## Overview

This is a **single-package** Rust project template (not a workspace). It provides a clean starting point for Rust applications with:

- Standard project structure
- Pre-configured CI/CD workflows
- Docker support
- Code formatting and linting setup
- Testing framework (nextest)
- License header checking (hawkeye)

> **Note**: This template is designed for **single-package** projects. If you need a **workspace** template with multiple crates, please use [rust-template](https://github.com/itscheems/rust-template) instead.

## Quick Start

### Prerequisites

- Rust (stable toolchain)
- [just](https://github.com/casey/just) - A command runner (optional but recommended)
- [hawkeye](https://github.com/itscheems/hawkeye) - License header checker (required for `just fmt` and `just lint`)
- [cargo-nextest](https://nexte.st/) - Fast test runner (required for `just test`)
- [cloc](https://github.com/AlDanial/cloc) - Lines of code counter (required for `just cloc`, optional)

### Installation

1. Clone this repository:

   ```bash
   git clone https://github.com/your-username/simple-rust-template.git
   cd simple-rust-template
   ```

2. Update `Cargo.toml` with your project name and details

3. Start coding in `src/main.rs`

## Development

### Build

```bash
# Debug build
cargo build

# Release build
cargo build --release
```

### Run

```bash
cargo run
```

### Using Just Commands

This project uses [just](https://github.com/casey/just) for common tasks:

```bash
# List all available commands
just --list

# Format code
just fmt

# Lint code
just lint
# or use alias
just l

# Run tests
just test
# or use alias
just t

# Calculate lines of code
just cloc
```

### Manual Commands

If you prefer not to use `just`:

```bash
# Format code
cargo fmt
hawkeye format

# Lint code
hawkeye check
cargo check --locked --all-features --all-targets
cargo clippy --locked --all-targets -- -D warnings

# Run tests
cargo nextest run --locked --no-tests=pass
```

## Project Structure

```
.
├── src/
│   └── main.rs          # Main application entry point
├── deploy/
│   ├── Dockerfile       # Docker build configuration
│   └── .dockerignore    # Docker ignore patterns
├── .github/
│   └── workflows/       # CI/CD workflows
├── Cargo.toml           # Project dependencies and metadata
├── Cargo.lock           # Dependency lock file
├── justfile             # Just command definitions
├── rust-toolchain.toml  # Rust toolchain version
├── rustfmt.toml         # Rustfmt configuration
├── clippy.toml          # Clippy linting configuration
└── LICENSE              # Apache 2.0 License
```

## Docker

Build and run with Docker:

```bash
cd deploy
docker build -t rust-template .
docker run rust-template
```

## Configuration

- **Rust Edition**: 2024
- **License**: Apache-2.0
- **Rust Toolchain**: Defined in `rust-toolchain.toml`
- **Code Style**: Configured in `rustfmt.toml` and `clippy.toml`

## License

Licensed under the Apache License, Version 2.0. See [LICENSE](LICENSE) for details.

## Related Templates

- **Workspace Template**: [rust-template](https://github.com/itscheems/rust-template) - For multi-crate workspace projects
