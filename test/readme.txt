expat プラグイン 実機テスト
===========================

startup.tjs は krkrz64.exe（または krkrz.exe）で自動実行される起動スクリプトです。
expat.dll を読み込み、XMLParser を継承したテストパーサでコールバック動作
(startElement/endElement/characterData/comment/cdata) と UTF-8<->UTF-16 変換
(マルチバイト文字)、エラー処理、parseStorage(ファイルパース) を検証します。
同フォルダの test.xml を parseStorage の対象に使います。

実行手順:
  1. expat.dll をビルドし、krkrz64.exe と同じフォルダにコピーする
     （Plugins.link は exe と同じディレクトリを基準に解決する。expat は静的
       リンクのため別途 libexpat.dll 等は不要）。
       例) build/x64-windows/core/plugins/expat/Release/expat.dll を
           build/x64-windows/core/Release/ へコピー
  2. このフォルダ（test）を引数に krkrz64.exe を起動する:
       krkrz64.exe "<このフォルダの絶対パス>" > out.txt 2>&1

判定:
  - 出力の "OK   :" / "FAIL :" 行で判定する（FAIL が無ければ全成功）。
  - 終了コードは SDL/エンジンの shutdown 経路の都合で System.exit の値通りに
    ならないことがあるため、出力行で判断すること。
