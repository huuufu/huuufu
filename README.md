# huuufu

## 🧩 Products

**[Netflix 挂载本地双语字幕](https://chromewebstore.google.com/detail/ihcnabaolepmlcecedadhfoplgelgapb)** — Chrome 拡張 · v2.0.2

- Netflix のプレイヤーにローカル字幕(SRT / VTT)を重ねて二言語表示。20 言語のリアルタイム翻訳、位置・サイズ・色・影のカスタマイズ。UI は日本語 / 英語 / 中国語に対応。
- Overlay local SRT/VTT subtitles on the Netflix player for bilingual viewing; real-time translation into 20 languages; customizable position, size, color and shadow. UI in Japanese, English and Chinese.

## 🌱 Open Source Contribution

**[Unstructured-IO/unstructured](https://github.com/Unstructured-IO/unstructured)** (15k ★) — [PR #4465](https://github.com/Unstructured-IO/unstructured/pull/4465) · merged 2026-09

- `partition_doc()` / `partition_ppt()` が Windows 上でマルチバイト文字を含むパスの文書を変換すると、soffice の出力を UTF-8 で厳密デコードして `UnicodeDecodeError` で失敗する問題を修正。3 箇所のデコードを寛容化し、テストを追加。
- Fixed `convert_office_doc()` crashing with `UnicodeDecodeError` on non-UTF-8 `soffice` output (Windows locale-codepage paths) during DOC/PPT partitioning; hardened three decode sites and added tests.
