Text-KAI
--------

ChromeOSでメモ用途で使う場合に、ほぼ純正Chromeappのメモ帳アプリのTextがベストです。
とてもシンプルで使いやすいのですが、どうしても欲しかった機能があります。
それは、「ctrl-h」による「バックスペースキー入力」です。
IMEがオンのときには使えるのですが、オフのときにも同様に使いたかったのです。
そんな動機で改造してみました。
ついでに、「ctrl-m」の「エンターキー入力」、「ctrl-i」の「TABキー入力」も追加するように改造してみました。

流石にこんなものにニーズがないと思うので、Store公開などせずに、
ローカルインストールとして自分用に纏めたパッケージとこのメモを残すだけにします。


インストール方法
------------------


* ダウンロードと展開
  - 下記よりzipファイルをダウンロードして、展開する。
  
* chromeで開発者モードでインストール
  - chrome://extensions/ にアクセス
  - デベロッパーモードをオン
  - 「パッケージ化されていない拡張機能を読み込む」から展開したディレクトリを選択。


オリジナルとの変更点
----------------------

* ショートカットの追加
  - ctrl-h バックスペースキー
  - ctrl-m エンターキー
  - ctrl-i タブキー

* 名前をつけて保存のファイル名日本語対応

* 名称、アイコン
  - 純正のアプリと見分けがつくように、アイコンと名称を変更しました。

* ライブラリの更新
  - CodeMirrorを5.65.11(2022/12/20) にUpdate


今後のアイディア
----------------

* やればできそうなこと
  - キーバインドの追加(Vim、sublimetext、emacs)
  - Codemirrorを６に変更する
  - フォントの変更
* やらないほうがいいこと
  - シンプルに利用できなくなる改造。
* 不明
  - ファイル間のリンク

ひとこと
--------

本来は何かしら理由があり、Chromeappは終了することになったのですが、
利用者からの要望があり、数年レベルでChromeappの終了を延期することになったようです。
たぶん、ChromeOSで使う場合にオフラインで、省メモリで実行できることというのが、便利なんだと思います。
PWAで同様のアプリを探すのも難しいです。だから、そんなに簡単に代替できないないのだと思いました。

延長した終了日が更に伸びて、Chromeappが残り続けると嬉しいです。


ビルドログ
----------


```shell
build.py:179: SyntaxWarning: "is" with a literal. Did you mean "=="?
  if type is 'warning' and not PRINT_THIRD_PARTY_WARNINGS:
Text-KAI-0.7.12
Deleting build/Text-KAI-0.7.12
Deleting build/Text-KAI-0.7.12.zip
Copying README-Text-KAI.md
Copying index.html
Copying css/app.css
Copying css/print.css
Copying css/theme-dark.css
Copying css/theme-default.css
Copying css/theme-light.css
Copying icon/16x16.png
Copying icon/32x32.png
Copying icon/48x48.png
Copying icon/64x64.png
Copying icon/96x96.png
Copying icon/128x128.png
Copying icon/256x256.png
Copying third_party/CodeMirror/lib/codemirror.css
Copying third_party/jquery/jquery-1.8.3.min.js
Copying third_party/material-components-web/material-components-web.min.css
Copying third_party/material-components-web/material-components-web.min.js
Copying third_party/material-design-icons/iconfont/material-icons.css
Copying third_party/material-design-icons/iconfont/MaterialIcons-Regular.woff2
Copying _locales/ja/messages.json
Copying _locales/en/messages.json
Copying _locales/zh_TW/messages.json
Copying _locales/zh_CN/messages.json
Copying _locales/fi/messages.json
Copying _locales/pl/messages.json
Copying _locales/en_GB/messages.json
Copying _locales/sv/messages.json
Copying _locales/ru/messages.json
Copying _locales/fr_CA/messages.json
Copying _locales/es/messages.json
Copying _locales/de/messages.json
Copying _locales/pt_BR/messages.json
Copying _locales/nl/messages.json
Copying _locales/no/messages.json
Copying _locales/ko/messages.json
Copying _locales/es_419/messages.json
Copying _locales/da/messages.json
Copying _locales/fr/messages.json
Copying _locales/it/messages.json
Compiling JavaScript code.
Connecting https://closure-compiler.appspot.com/compile

26 warnings:

js/background_externs.js:10 Bad type annotation. Unknown type FileEntry
 * @param {Array.<FileEntry>} entries

js/background_externs.js:14 Bad type annotation. Unknown type FileEntry
 * @return {Array.<FileEntry>}

js/background_externs.js:21 assignment to property textApp of Window
found   : {}
required: (TextApp|null)
window.textApp = {};

js/util.js:36 Property trigger never defined on $.event
  $.event.trigger('filesystemerror');

js/util.js:41 Bad type annotation. Unknown type FileEntry
 * @param {FileEntry} entry

js/util.js:57 Bad type annotation. Unknown type FileWriter
 * @param {FileWriter} writer

js/util.js:114 inconsistent return type
found   : {
  codemirror: ?,
  textarea: (Element|null)
}
required: {
  codemirror: (Object|null),
  textarea: (HTMLElement|null)
}
missing : []
mismatch: [textarea]
  return {

js/background.js:120 Bad type annotation. Unknown type FileEntry
 * @param {Array.<FileEntry>} toRetain

js/background.js:144 Bad type annotation. Unknown type FileEntry
 * @param {FileEntry} entry

js/background.js:145 Bad type annotation. Unknown type FileEntry
 * @param {function(FileEntry)} callback

js/background_externs.js:486 Bad type annotation. Unknown type FileEntry
/** @type {!FileEntry} */

js/background_externs.js:505 Bad type annotation. Unknown type FileEntry
/** @type {!Array<{entry: !FileEntry, type: (string|undefined)}>|undefined} */

js/background_externs.js:3121 Bad type annotation. Unknown type DirectoryEntry
 * @param {function(!DirectoryEntry)} callback

js/background_externs.js:8290 Bad type annotation. Unknown type FileEntry
/** @type {!Array<!FileEntry>} */

js/background_externs.js:8713 Bad type annotation. Unknown type Entry
 * @param {!Entry} entry The entry to get the display path for. The entry can

js/background_externs.js:8725 Bad type annotation. Unknown type Entry
 * @param {!Entry} entry The entry to get a writable entry for.

js/background_externs.js:8726 Bad type annotation. Unknown type Entry
 * @param {function(!Entry)} callback A success callback.

js/background_externs.js:8734 Bad type annotation. Unknown type Entry
 * @param {!Entry} entry The entry to query writability.

js/background_externs.js:8793 Bad type annotation. Unknown type Entry
 *     function(Entry=, !Array<!FileEntry>=)} optionsOrCallback The

js/background_externs.js:8793 Bad type annotation. Unknown type FileEntry
 *     function(Entry=, !Array<!FileEntry>=)} optionsOrCallback The

js/background_externs.js:8795 Bad type annotation. Unknown type Entry
 * @param {function(Entry=, !Array<!FileEntry>=)=} opt_callback A success

js/background_externs.js:8795 Bad type annotation. Unknown type FileEntry
 * @param {function(Entry=, !Array<!FileEntry>=)=} opt_callback A success

js/background_externs.js:8805 Bad type annotation. Unknown type Entry
 * @param {function(!Entry)} callback A success callback.

js/background_externs.js:8822 Bad type annotation. Unknown type Entry
 * @param {!Entry} entry The entry to regain access to.

js/background_externs.js:9567 Bad type annotation. Unknown type Entry
 * @param {!Entry} fileEntry

js/background_externs.js:9581 Bad type annotation. Unknown type FileEntry
 * @param {!Array<!FileEntry>} fileEntries

Writing build/Text-KAI-0.7.12/js/background.js
Compiling JavaScript code.
Connecting https://closure-compiler.appspot.com/compile
Writing build/Text-KAI-0.7.12/js/all.js
Archiving build/Text-KAI-0.7.12.zip

```


ライセンス
------------

オリジナルのライセンスに準じます
https://raw.githubusercontent.com/diverc/text-app-kai/master/LICENSE.md


以上
