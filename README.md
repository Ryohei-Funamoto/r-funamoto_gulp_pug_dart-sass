# r-funamoto_gulp_pug_dart-sass
* 当ファイルはPug, Dart Sass対応のGulpファイルです。

## 手順
1. ターミナルを開きます。
2. `npm i`コマンドを実行し、package-lock.jsonとnode_modulesを生成します。
3. `npm run dev`コマンドで開発環境を起動します。
* CSSを圧縮しない
* css.mapを作成する
* メディアクエリをまとめない
4. `npm run prod`コマンドで本番環境用ファイルを出力します。
* CSSを圧縮しない
* css.mapを作成しない
* メディアクエリをまとめる
* 自動キャッシュクリア

## 注意点
* 開発フォルダはsrcです。
* srcフォルダ内のファイルはdistフォルダに吐き出されます。

## Nodeについて
* node v16.14.0にて動作を確認済。

## Sass
* 当ファイルはDart Sass対応ですが、globでまとめられるようにしておりますので、globalフォルダ以外の各フォルダ内のファイルを_index.scssでまとめる必要はございません。
* 当ファイルは、FLOCSS記法に準じたファイル構成になっております。
* globalフォルダには、変数、関数、mixin等が格納されております。
* 各ファイルでglobalフォルダ内の変数等を使用する場合は、@use "global" as *;の記述が必要です。※相対パスで書く必要はございません。
* objectフォルダ内には、component, project, utilityフォルダがあります。
* pageフォルダには、各ページ固有のCSSを定義したファイルを格納します。
* structureフォルダには、JSライブラリ等のCSSを格納します。

## Pug
* src/pug/commonフォルダ内には、ヘッダー、フッター等の共通パーツを格納します。
* src/dataフォルダには、各ページのタイトル、ディスクリプション等を管理しているJSONファイルが格納されております。
* 各ページのファイル(src/pug/index.pug 及び src/pug/**/index.pug)でsrc/pug/common/_layout.pug(レイアウト用テンプレート)を継承し、block pageId(任意のページID)とblock content(ページのコンテンツ)を上書きします。
