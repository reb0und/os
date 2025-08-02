# Cross-Compiler
- Will create a compiler that will have a generic target, that allows leaving the current operating system behind, meaning that no headers or libraries of the host OS will be used, without using a cross-compiler for OS development, unexpected things can happen since the compiler assums the code is running on the host OS

## Cross-compilation
- This is needed with Rust
- [`rustup` cross compilation](https://rust-lang.github.io/rustup/cross-compilation.html)
- To compiler to other platforms need to install target platforms
    - Done with `rustup target add <target>` command
    - Example: `rustup target add arm-linux-androideabi`
        - Can build for Android with Cargo by passing the `--target` flag, `cargo build --target=arm-linux-androideabi`
- Can build for a specific target with `cargo build --target=<target>`
- `rustup target` only installs the Rust standard library for a given target, there are more toools necessary to cross compile, such as a linker
- Can view the [target](https://doc.rust-lang.org/cargo/reference/config.html#target) section of `cargo` for configuration on how to setup a linker to use for a certain target
- To install a target for a toolchain that isn't the default toolchain, can use the `--toolchain` argument of `rustup target add`
- Example: `rustup target add --toolchain <toolchain> <target>`

### Platforms
- [`rustc` platforms](https://doc.rust-lang.org/beta/rustc/platform-support.html)

#### Targets
- [`x86_64-unknown-none`](https://doc.rust-lang.org/beta/rustc/platform-support/x86_64-unknown-none.html)

### Toolchains
- [`rustc` toolchains](https://rust-lang.github.io/rustup/concepts/toolchains.html)
- Can link a toolchain with `rustup toolchain link <toolchain name> <path to toolchain>`
- Need to at least specify the channel and host (target triple) of the toolchain intended to be used
    - Can setup Flake environment for this

### Review
- [Rust critique](https://www.reddit.com/r/osdev/comments/18e6r6m/switched_back_from_rust_to_c/)

### Immediate TODOs
- Cross-compilation and targeting
- Testing
- Dev environment
- Plan rest of order
