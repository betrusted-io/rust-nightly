# Rust Nightly for Xous

Nightly rebuilds of Xous support for Rust.

Each night this repo installs the latest `nightly` compiler, then applies these patches on top to ensure
that they still work. If upstream changes the API, the build errors and we will adjust the Xous patches
to match.

## Building From Source

1. Install a RISC-V toolchain, and ensure it's in your path.
2. Enter the `rust` directory and make sure it's checked out. Use `rustc +nightly -Vv` to get the hash used by the compiler.
3. Apply all patches: `git am ../*.patch`. Fix patches as necessary.
4. Run `CC=riscv-none-elf-gcc RUST_TOOLCHAIN=+nightly ../build.sh` to verify the build works.

## Building on Windows Powershell

On Windows, you can use the `build.ps1` script to drive the compilation instead.
