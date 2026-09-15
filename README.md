# huuufu

## 🧩 Products

**[Netflix 挂载本地双语字幕](https://chromewebstore.google.com/detail/ihcnabaolepmlcecedadhfoplgelgapb)** — Chrome 拡張 · v2.0.2

- Netflix のプレイヤーにローカル字幕(SRT / VTT)を重ねて二言語表示。20 言語のリアルタイム翻訳、位置・サイズ・色・影のカスタマイズ。UI は日本語 / 英語 / 中国語に対応。
- Overlay local SRT/VTT subtitles on the Netflix player for bilingual viewing; real-time translation into 20 languages; customizable position, size, color and shadow. UI in Japanese, English and Chinese.

## 🌱 Open Source Contributions

**[Unstructured-IO/unstructured](https://github.com/Unstructured-IO/unstructured)** (15k ★) — document parsing / ETL library for LLM and RAG pipelines

**[PR #4484](https://github.com/Unstructured-IO/unstructured/pull/4484)** · merged 2026-09 — `fix(html): recognize single-block list items`

- Markdown の空行区切りリスト(loose list)は `<li><p>…</p></li>` にコンパイルされ、`partition_md()` が `ListItem` ではなく `Text` として返していた。`<li>` が単一の段落ブロックだけを含む場合にその内容を採用するよう HTML パーサを修正し、インライン注釈・入れ子の深さ・ページ番号を維持。崩してはいけない 14 ケースをテストで固定。2024 年からの Issue #3499 を解決。
- Markdown loose lists compile to `<li><p>…</p></li>`, which `partition_md()` returned as `Text` instead of `ListItem`. A `<li>` whose only child is a single plain text block now adopts that block's content, preserving inline annotations, nesting depth and page numbers; 14 must-not-change cases are pinned by tests. Resolves #3499 (open since 2024).

**[PR #4465](https://github.com/Unstructured-IO/unstructured/pull/4465)** · merged 2026-09 — `fix: tolerate non-UTF-8 soffice output in doc/ppt conversion`

- `partition_doc()` / `partition_ppt()` が Windows 上でマルチバイト文字を含むパスの文書を変換すると、soffice の出力を UTF-8 で厳密デコードして `UnicodeDecodeError` で失敗する問題を修正。3 箇所のデコードを 1 つのヘルパーに集約して `backslashreplace` で寛容化し、テストを追加。2024 年からの Issue #3652 を解決。
- Fixed `convert_office_doc()` crashing with `UnicodeDecodeError` on non-UTF-8 `soffice` output (Windows locale-codepage paths) during DOC/PPT partitioning; the three decode sites now share one `backslashreplace` helper, with tests. Resolves #3652 (open since 2024).

**[Issue #4466](https://github.com/Unstructured-IO/unstructured/issues/4466)** · open — `detect_file_encoding()` returns mojibake

- 文字コード自動判定が、Shift_JIS の日本語テキストを `johab`、Latin-1 のフランス語を `windows-1250` として読み、文字化けのまま要素テキストにしてしまう問題を報告。再現コード、原因(未使用の `validate_encoding()`、`iso_8859_1` が候補リストの残り 18 件を到達不能にしている)、試した修正案とそれぞれが回帰させる反例(cp1254 のトルコ語)を添付。
- Reported silent mojibake from encoding auto-detection (Shift_JIS Japanese read as `johab`, Latin-1 French as `windows-1250`), with a repro, root-cause analysis (unused `validate_encoding()`, `iso_8859_1` shadowing the other 18 candidates) and the trade-offs of the candidate fixes, including the regression each one introduces.
