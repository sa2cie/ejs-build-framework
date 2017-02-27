# Site Basic Framework  (ejs + less/scss)

## はじめに

ejsとless・scssを組み合わせた静的サイト構築フレームワークです。
srcディレクトリ内のファイルをgulpを用いて変換し、buildフォルダへ出力します。
node.jsのバージョンは4系列最新版を利用してください。

## 使用方法

node.jsをインストールします。
node.jsのバージョンは4.xを推奨します（2016/03現在）

package.jsonのnpmモジュールをローカルフォルダへインストールします。

  > npm install

npm startを実行するとファイルがビルドされ、そのまま監視モードになります。

  > npm start

## 動作内容

srcからbuildフォルダへは*.ejsと*.less/scss以外のファイルがコピーされます。
srcフォルダ内でのパスの位置関係を保持したまま、distフォルダにファイルが置かれます。

通常起動時の監視モードではローカルサーバが起動し、localhost:8080でdistフォルダにアクセスできます。
また、初回起動時にはブラウザを開きます。

## npm-scripts

npm-scriptsの中で主要な機能は下記になります。

### npm run ejs

ejsのみ変換を行います。  
_（アンダーバー）が頭に付くファイルはdistフォルダには移りません。  
テンプレートやモジュールファイルとして使用できます。

  > npm run ejs

### npm run less

lessのみ変換を行います。  
_（アンダーバー）が頭に付くファイルはdistフォルダには移りません。  
変換後のファイルはminify化されます。  
デバッグ用にSOURCEMAPが出力されます。

  > npm run less

### npm run scss(sass)

scssのみ変換を行います。  
_（アンダーバー）が頭に付くファイルはdistフォルダには移りません。  
変換後のファイルはminify化されます。
デバッグ用にSOURCEMAPが出力されます。

  > npm run scss

### npm run build

gulp ejs、gulp less、gulp scss、gulp copyを行い、完成状態のファイルをbuildに生成します。  
納品時用オプションの為、SOURCEMAPは出力されません。

  > npm run build

