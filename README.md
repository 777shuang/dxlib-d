# dxlib-d

DXライブラリのD言語で使うためのポーティングライブラリです。
**現在Windowsのみ対応**しています。

## 利用手順

### 必要なもの

- **DMD**
  - LDCやGDCでの動作は未確認です
- [DxLib.dll](https://github.com/777shuang/DxLib.dll/releases)
- [DxLib.lib](https://github.com/777shuang/DxLib.dll/releases)

### ビルド方法

- 作業ディレクトリにこのリポジトリをクローンします
  ```
  git clone https://github.com/777shuang/dxlib-d dxlib
  ```
  - もし作業ディレクトリがGitリポジトリの一部で、submoduleとして追加したいときは以下を実行します
    ```
    git submodule add https://github.com/777shuang/dxlib-d dxlib
    ```
- DXライブラリを使用するソースファイル冒頭でimportします。
  ```D
  import dxlib
  ```
- 作業ディレクトリに[DxLib.lib](https://github.com/777shuang/DxLib.dll/releases)を置きます
- コンパイルします
  ```
  dmd -m64 source.d DxLib.lib 
  ```
  - もしくは、ソースファイル冒頭でDxLib.libをリンクする設定を記述します。dubで管理している場合などに有効です。
    ```D
    pragma(lib, "DxLib.lib")
    ```

## dxlib-d自体の作成手順

### 必要なもの

- 本家DXライブラリ本体
  - ヘッダーファイルが必要です
- このリポジトリ
- bash, sed, iconv等(git等に付属)
  - スクリプトの実行に必要です
  - MSYS2で動作確認をしています

### 変換方法

1. このリポジトリをクローン
  - `git clone https://github.com/777shuang/dxlib-d`
2. DXライブラリ本体をダウンロードし、ヘッダファイル`DxLib.h`、`DxFunctionWin.h`をdxlib-d.shのある場所に移動させます
3. `dxlib-d.sh`を実行して変換を待ちます。
4. `dxlib.d`と`dxfunctionwin.d`が生成されます。

## 著作権表記

dxlib.dには自動変換されたDXライブラリのコードが含まれています。

DX Library Copyright (C) 2001-2024 Takumi Yamada.
