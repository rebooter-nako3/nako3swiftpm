# Swift Playgrounds × なでしこ 3 (Swiftpm ファイル作成ツール)

- **対応バージョン:** Python 3.9以上
- **用途:** iPad/iPadOS の Swift Playgrounds で動作可能な swiftpm プロジェクト構成ファイルの作成

---

## 📢 はじめに

このCLIツールは、iPad 上で日本語プログラミング言語「なでしこ 3」を使用した iPhone/iPad アプリを制作するための、Swift Playgrounds のプロジェクト構成ファイル（swiftpm ファイル）を生成するものです。

---

## ⚠️ 注意 (必ずお読みください)

ツールを実行する前に以下の手順を強く推奨します。

1. **バックアップ**
   現在のプログラミング中の swiftpm ファイルを必ずバックアップしてください。
2. **環境準備**

   **ターミナルアプリ**で以下の手順を行います。
   - 空の作業フォルダを作成する。
   - カレントディレクトリ（現在位置）をそのフォルダに移動させる (`cd`)。
   - このCLIツールをカレントディレクトリにダウンロードする

   - **ファイルを追加する場合:** 追加するファイルまたはフォルダ構成を維持する場合は追加するファイルがあるフォルダをカレントディレクトリにコピーする

   - **新規作成する場合**も、空の作業フォルダを作成後に実行することを推奨します。

---

## 🛠 用意する実行環境 (動作確認済)

 [iPad]

 ① ローカル端末エミュレータ「a-Shell mini」

- **対応 App Store:** [a-Shell mini](https://apps.apple.com/jp/app/a-shell-mini/id1543537943?platform=ipad)

 ② 組み込みエミュレート端末内蔵のコードエディタ「Code App」（買い切り1100円）

- **対応 App Store:** [Code App](https://apps.apple.com/jp/app/code-app/id1512938504?platform=ipad)
- **金額:** 買い切り1100円

 [Mac]

 標準のターミナルアプリ

---

## 📂 コマンド説明

| コマンド | 説明 |
| --- | --- |
| `nako3swiftpm init` | **新規作成**: Swift Playgroundsで実行可能なswiftpmファイルを新規作成|
| `nako3swiftpm upgrade` | **アップグレード**: 内蔵の「なでしこ３」本体を最新バージョンに置き換え |
| `nako3swiftpm add` | **追加/上書き**: 指定のフォルダ以下のファイルor指定のファイルを追加/上書き|
| `nako3swiftpm version` | **バージョン情報を表示**|
| `nako3swiftpm` | **使い方を表示**|
---

## 📖 使い方例

入力: `hello.swiftpm` (initでは拡張子なし可)

1. **新規作成**

   Swift Playgroundsで実行可能なhello.swiftpmを新規作成する。

   ```bash
   nako3swiftpm init hello
   # → "hello.swiftpm" が生成されます。
   ```

2. **アップグレード**

   hello.swiftpmのなでしこ３を最新版にアップグレードする。

   ```bash
   nako3swiftpm upgrade hello.swiftpm
   ```

3. **フォルダ以下のファイルの追加**

   hello.swiftpmに指定フォルダ以下のファイルを追加または上書きコピーする。

   ```bash
   nako3swiftpm add hello.swiftpm home
   # 指定フォルダが「home」場合
   # home/* → hello.swiftpm/nako3/*
   
   nako3swiftpm add hello.swiftpm home/image
   # 指定フォルダが「home/image」場合
   # home/image/* → hello.swiftpm/nako3/image/*
   
   nako3swiftpm add hello.swiftpm ./image
   # 指定フォルダが「./image」場合
   # ./image/* → hello.swiftpm/nako3/image/*
   ```

4. **ファイルの追加**

   hello.swiftpmに指定ファイルを追加または上書きコピーする。

   ```bash
   nako3swiftpm add hello.swiftpm main.nako3
   # 指定ファイルが「main.nako3」場合
   # main.nako3 → hello.swiftpm/nako3/main.nako3
   
   nako3swiftpm add hello.swiftpm ./image/img.png
   # 指定ファイルが「./image/img.png」場合
   # ./image/img.png → hello.swiftpm/nako3/image/img.png
   
   nako3swiftpm add hello.swiftpm image/img.png
   # 指定ファイルが「image/img.png」場合
   # image/img.png → hello.swiftpm/nako3/img.png
   ```

> **※制限事項:**
> iPadのターミナルアプリで「フォルダ以下のファイルの追加」「ファイルの追加」でフォルダやファイルの指定に「../」を使用しないでください。想定外の場所(パス)にファイルが追加される原因となります。

## ℹ️ 追加情報

- [Swift Playgroundsになでしこ３の文法エラーを表示する方法](./ADDINFO_001.md)
- .swiftpmファイル(実体はフォルダ)のnako3フォルダ以下のファイル構成は[なでしこ3配布キット(nadesiko3webkit)](https://github.com/kujirahand/nadesiko3webkit)のwebappフォルダ以下のファイル構成と同じ物になります。nadesiko3フォルダは、本CLIツールの実行時のなでしこ3本体の最新バージョンに置き換えられています。
