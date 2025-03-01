# LT About 100 Challenge

## 環境作成

### Python環境

仮想環境を作成する

    uv venv --python 3.13

パッケージを追加する

    uv pip install Sphinx
    uv pip install sphinx-revealjs

### sphinx環境

実行するコマンドは以下

    sphinx-quickstart docs

順番に質問へ答えたログが以下

    PS D:\work\Py\26lt_read100challenge\lt_abt100chal> sphinx-quickstart docs
    Sphinx 8.2.1 クイックスタートユーティリティへようこそ。

    以下の設定値を入力してください（Enter キーのみ押した場合、
    かっこで囲まれた値をデフォルト値として受け入れます）。

    選択されたルートパス: docs

    Sphinx 出力用のビルドディレクトリを配置する方法は2つあります。
    ルートパス内にある "_build" ディレクトリを使うか、
    ルートパス内に "source" と "build" ディレクトリを分ける方法です。
    > ソースディレクトリとビルドディレクトリを分ける（y / n） [n]: y

    プロジェクト名は、ビルドされたドキュメントのいくつかの場所にあります。
    > プロジェクト名: lt_abt100chal
    > 著者名（複数可）: inoinoino
    > プロジェクトのリリース []: 

    ドキュメントを英語以外の言語で書く場合は、
    言語コードで言語を選択できます。Sphinx は生成したテキストをその言語に翻訳します。

    サポートされているコードのリストについては、
    https://www.sphinx-doc.org/en/master/usage/configuration.html#confval-language を参照してくだ さい。
    > プロジェクトの言語 [en]: ja

    ファイル D:\work\Py\26lt_read100challenge\lt_abt100chal\docs\source\conf.py を作成しています。
    ファイル D:\work\Py\26lt_read100challenge\lt_abt100chal\docs\source\index.rst を作成しています。
    ファイル D:\work\Py\26lt_read100challenge\lt_abt100chal\docs\Makefile を作成しています。      
    ファイル D:\work\Py\26lt_read100challenge\lt_abt100chal\docs\make.bat を作成しています。      

    終了：初期ディレクトリ構造が作成されました。

    マスターファイル D:\work\Py\26lt_read100challenge\lt_abt100chal\docs\source\index.rst を作成して
    他のドキュメントソースファイルを作成します。次のように Makefile を使ってドキュメントを作成します。
    make builder
    "builder" はサポートされているビルダーの 1 つです。 例: html, latex, または linkcheck。       

    PS D:\work\Py\26lt_read100challenge\lt_abt100chal> 
