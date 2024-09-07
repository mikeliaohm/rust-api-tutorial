# Rust API Server

## Developing and Testing the repo

Use cargo watch to compile the server code. The `--release` flag was to run the server in the release mode since running the server in default (debug mode) will cause fs locking in the build directory since the cargo test will also recompile and require access to the executable from the source code.

```bash
cargo watch -q -c -w src/ -x "run --release"
```

Use httpc-test library to test the endpoint. Use cargo watch (installed with cargo install cargo-watch) to compile saved changes.

```bash
cargo watch -q -c -w tests/ -x "test -q quick_dev -- --nocapture"
```

