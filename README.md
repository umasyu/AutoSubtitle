# AutoSubtitle

AviUtl2 用 自動字幕生成プラグインです。  
音声ファイルや動画ファイルから音声認識を行い、字幕を自動生成して  
AviUtl2 のタイムラインへ挿入します。

---

## 動作要件

以下の環境が必要です。

### OS
- Windows 10 / Windows 11（64bit）

### 対応ソフト
- AviUtl2

### 外部ソフトウェア
- **Python 3.12（必須）**  
 https://www.python.org/downloads/release/python-3120/
- **faster-whisper（必須）**
- **ffmpeg（任意）**
  https://www.ffmpeg.org/download.html

### GPU を使用する場合（任意）
- **CUDA Toolkit 12.1（必須）**
  https://developer.nvidia.com/cuda-12-1-0-download-archive?target_os=Windows&target_arch=x86_64&target_version=11&target_type=exe_local

※ GPU を使用しない場合（CPU実行）は CUDA Toolkit は不要です。  
※ 本プラグインには Python / faster-whisper / ffmpeg / CUDA Toolkit は同梱されていません。

### 外部ソフトの導入方法はこちらを参照
- https://qiita.com/taiki_i/items/3d2d0d0b2dd79059f30e

---

## 導入方法

1. GitHub の Releases ページから最新版の ZIP をダウンロードします。  
   https://github.com/umasyu/AutoSubtitle/releases/latest

2. ZIP を解凍し、以下のファイルを AviUtl2 の Plugin フォルダに配置します。
 - AutoSubtitle.dll
 - README.txt
 - LICENSE.txt

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
- CPU / GPU（CUDA）実行の切り替え
- 詳細ログ出力（デバッグ用途、任意）

---

## GPU（CUDA）使用について

- GPU を使用する場合は **CUDA Toolkit 12.1 が必須**です。
- CUDA Toolkit がインストールされていない場合、GPU は使用できません。
- GPU が使用できない場合でも、CPU モードで字幕生成は可能です。

※ NVIDIA ドライバおよび CUDA Toolkit のインストール方法については  
　NVIDIA 公式サイトをご確認ください。

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
 - C:\ProgramData\aviutl2\Plugin\AutoSubtitle\Logs\


（Python 関連のログは `Logs\Python` フォルダ内に出力されます）

不具合報告の際は、ログファイルを添えてご連絡ください。

---

## ライセンス

本プラグインは **MIT License** のもとで公開されています。  
詳細は同梱の `LICENSE.txt` をご確認ください。

※ 本プラグインは Python / faster-whisper / ffmpeg / CUDA Toolkit を同梱していません。  
それらのライセンスについては、各配布元の規約に従ってください。

---

## 連絡先

不具合報告・ご要望・ご質問は、以下までご連絡ください。

- **Twitter (X)**  
  https://x.com/umasyu2525

可能であれば、以下の情報を添えていただけると助かります。

- 発生した問題の内容
- AviUtl2 のバージョン
- Python のバージョン
- CPU / GPU 使用の有無
- 出力されたログファイル

---

## 宣伝

普段は配信活動と動画投稿活動をしていますので良ければ応援してください。

- **Twitch**  
   https://www.twitch.tv/umasyu_ttv
  
- **Youtube**  
   https://www.youtube.com/@UMASYUChannel

また、Discordサーバーを運営しているので、気になったら参加してみてください。

- **Discord鯖**  
   discord.com/invite/9A693VGghp
