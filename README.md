# これ
https://developer.mozilla.org/ja/docs/WebAssembly/Rust_to_wasm
https://rustwasm.github.io/wasm-bindgen/

## 手順
```
# Rust は普通にセットアップしておく

$ cargo install wasm-pack

$ cargo new --lib <NAME>
# Cargo.toml に crate-type と dependency 設定を追加
# [lib]
# crate-type = ["cdylib"]
# [dependencies]
# wasm-bindgen = "<VERSION>"

$ wasm-pack build --target web
```

## Note
なんかダウンロードがタイムアウトする感じの時は Ctrl-C してやり直すと
そのうちうまくいく。
