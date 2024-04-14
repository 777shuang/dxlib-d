# dxlib-d

DXライブラリのD言語で使うためのポーティングライブラリです。
**現在Windowsのみ対応**しています。

## 利用手順

### 必要なもの

- **DMD**
  - LDCやGDCでの動作は未確認です
- [DXライブラリのDLL](https://github.com/777shuang/DxLib.dll/releases)
  - DLLに加え**`DxLib.lib`も必要です**
- `dxlib.d`

### ビルド方法

ご自身のソースと`dxlib.d`、DXライブラリのlibファイル群を指定してコンパイル

```
dmd -m64 source.d dxlib.d DxLib.lib
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
