# AutoSubtitle

AviUtl2 用 自動字幕生成プラグインです。  
音声ファイルや動画ファイルから音声認識を行い、字幕を自動生成して  
AviUtl2 のタイムラインへ挿入します。

---

## 動作要件

以下の環境が必要です。

- **OS**
  - Windows 10 / Windows 11（64bit）

- **対応ソフト**
  - AviUtl2（最新版推奨）

- **外部ソフトウェア**
  - Python 3.12（推奨）
  - faster-whisper
  - ffmpeg（※任意）

※ 本プラグインには Python / faster-whisper / ffmpeg は同梱されていません。  
※ ffmpeg を使用しない場合でも、字幕生成は可能です。

---

## 導入方法

1. GitHub の Releases ページから最新版の ZIP をダウンロードします。  
   https://github.com/umasyu/AutoSubtitle/releases/latest

2. ZIP を解凍し、以下のファイルを AviUtl2 の Plugin フォルダに配置します。
・AutoSubtitle.dll
・README.txt
・LICENSE.txt

3. AviUtl2 を起動します。

4. メニューから **AutoSubtitle** を開きます。

5. 初回起動時は「実行環境」タブで Python 実行ファイルを指定してください。
- 未指定の場合、自動検出を試みます。

設定は自動的に保存され、次回起動時に復元されます。

---

## 主な機能

- 音声認識による字幕自動生成
- AviUtl2 タイムラインへの字幕自動挿入
- 認識プロファイル・デコード設定の切り替え
- テキスト整形（改行、文字数制限、フィラー削除など）
- ffmpeg を使用した音声前処理（ノイズ除去・音量正規化など）
- 詳細ログ出力（デバッグ用途、任意）

---

## ffmpeg について

- ffmpeg を指定すると、音声の前処理が有効になります。
- ffmpeg を指定しない場合、音声前処理は行われません。

※ ffmpeg は必須ではありません。  
※ 使用する場合は、各自で入手し、ffmpeg のライセンス条件を遵守してください。

---

## ログについて

- 「詳細ログを有効にする」を ON にした場合のみ、詳細なログが出力されます。
- エラー発生時は、以下のフォルダにログが出力されます。

C:\ProgramData\aviutl2\Plugin\AutoSubtitle\Logs\


（Python 関連のログは `Logs\Python` フォルダ内に出力されます）

不具合報告の際は、ログファイルを添えてご連絡ください。

---

## ライセンス

本プラグインは **MIT License** のもとで公開されています。  
詳細は同梱の `LICENSE.txt` をご確認ください。

※ 本プラグインは Python / faster-whisper / ffmpeg を同梱していません。  
それらのライセンスについては、各配布元の規約に従ってください。

---

## 連絡先

不具合報告・ご要望・ご質問は、以下までご連絡ください。

- **Twitter (X)**  
  https://twitter.com/（ここにアカウント名を記載）

可能であれば、以下の情報を添えていただけると助かります。

- 発生した問題の内容
- AviUtl2 のバージョン
- Python のバージョン
- 出力されたログファイル
