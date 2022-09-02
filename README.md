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

# pkg/ に成果物が生成される
# pkg/<name>.js がエントリ

# index.html を作る
# import init from "./pkg/<name>.js";
# でエントリ js ファイルから async function init() をインポートし
# これを呼ぶと wasm のロードが開始される
# then() か async function 内で await init() して完了後に
# wasm からエクスポートされた関数が使えるようになる

# file:/// で直接開いても駄目っぽい
# wasm の MINE に対応しているサーバを立ち上げる
$ python3 -m http.server

# index.html をブラウザで開く
# http://localhost:8000/
```

## Note
なんかダウンロードがタイムアウトする感じの時は Ctrl-C してやり直すと
そのうちうまくいく。
