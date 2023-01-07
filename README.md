# <i class="fa fa-cogs"></i> VSCodeの環境設定

VSCodeの初期状態だと、効率的な環境には程遠いため、まとめて最初に設定してしまう。設定内容は大きく以下の通り。全体の流れをイメージしておく。

|番号|設定項目|概要|設定方法|
|:-:|:-|:-|:-|
|<span class="p20 red">**①**</span>|**プロジェクト設置**|仮想サーバに**研修用フォルダ**を設置|コマンドで移動|
|<span class="p20 red">**②**</span>|**基本設定**|**設定**/**ワークスペース**/**拡張機能**を追加|コマンドで移動|
|<span class="p20 red">**③**</span>|**ショートカット**|拡張機能などの**キーバインド**を設置|ファイル名を変更し移動|
|<span class="p20 red">**④**</span>|**拡張機能**|**拡張機能**を一括インストール|設定ファイルを移動後<br>一括インストール|
|<span class="p20 red">**⑤**</span>|**スニペット**|**汎用的な呼び出しコード**の設置|コマンドで移動|

![](https://i.imgur.com/rk0OQxi.jpg)

<br>

事前に設定に必要なファイルをダウンロードし、フォルダ階層、ファイルも開いておく。まずは、[GitHub](https://github.com/kenshu-app/workspace)にアクセスし、右上の「**Code**」ボタンから「**Download ZIP**」を選択し、関連ファイルをダウンロードする。またMacは自動解凍されるためそのままで良いが、WindowsはZipデータを解凍し<span class="red">**Downloads内直下**</span>に解凍した「**workspace**」フォルダを配置しておく。

![](https://i.imgur.com/QPYyUzg.jpg)

まずはVSCodeに表示を切り替えコンソール(黒い画面)を開き、==事前にできることをコマンドから実行==していく。「**Ctrl + J**」で下部パネルを開き「**ターミナル**」タブを選択する。

![](https://i.imgur.com/jGagzN0.jpg)

各OSに応じた以下のコードを1行ずつ頭の<strong>\$は含めず</strong>コピペしていき「**Enter**」で実行していく。`start`や`open`はフォルダを開き、`mv`はファイルやフォルダの移動、`mkdir`はフォルダを作成するコマンドとなっている。

<div class="p20">
  
```bash
# Win
# 仮想サーバの階層を開く(スタートメニューに登録)
$ start /c/xampp/htdocs/
# デスクトップのpracticeをhtdocsに移動
$ mv -p ~/Desktop/practice /c/xampp/htdocs/
# 各設定ファイルやフォルダを移動
$ mv ~/Downloads/workspace/win_keybindings.json ~/AppData/Roaming/Code/User/keybindings.json
$ mv ~/Downloads/workspace/win_settings.jsonc ~/AppData/Roaming/Code/User/settings.json
$ mv -p ~/Downloads/workspace/snippets ~/AppData/Roaming/Code/User/
# 拡張機能ファイルを設定
$ mkdir /c/xampp/htdocs/.vscode
$ mv ~/Downloads/workspace/extensions.json /c/xampp/htdocs/.vscode

# Mac
$ open /Applications/MAMP/htdocs/
$ mv -p ~/Desktop/practice /Applications/MAMP/htdocs/
$ mv ~/Downloads/workspace/mac_keybindings.json ~/Library/Application\ Support/Code/User/
$ mv ~/Downloads/workspace/mac_settings.jsonc ~/Library/Application\ Support/Code/User/settings.json
$ mv -p ~/Downloads/workspace/snippets ~/Library/Application\ Support/Code/User/
$ mkdir /Applications/MAMP/htdocs/.vscode
$ mv ~/Downloads/workspace/extensions.json /Applications/MAMP/htdocs/.vscode
```
</div>

<br>

<span class="p20 red">**①**</span>「**htdocs**」フォルダが開いているので前面に表示させる。「**practice**」フォルダを==そのままサイドメニューにドラッグ==し「**クイックスタートメニューに登録**」しておく。

![](https://i.imgur.com/VJokOxK.jpg)

<span class="p20 red">**②**</span> 拡張機能を読み込むため、左サイドの拡張機能アイコンを選択し、上部の検索窓に「**@recommended**」と入力すると、すぐ下に表示される雲形のインストールボタンが表示されるため、そこから==拡張機能の一括インストール==を開始する。

拡張機能インストール済みの一覧は以下のコマンドで確認できる。
<div class="p24">
  
```bash=
$ code --list-extensions
```
</div>

![](https://i.imgur.com/8GvnGSW.jpg)

※ 必要があればVSCdeを再起動して各設定を反映させる。
