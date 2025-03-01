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

revealjsを利用する為に、source/conf.pyのextensionsリストへ以下追記する

   'sphinx_revealjs',

## スライド作成

### ビルド

ルートディレクトリで以下コマンドを実行

    .\docs\make.bat revealjs

出力される以下ファイルをダブルクリックすれば、ブラウザでプレビューできる

    \docs\build\revealjs\index.html

### デプロイ

※ この設定は最初に行っておけば、以降自動化できる。

まずはPython環境をファイル出力しておく

    uv pip freeze > requirements.txt

対象のリポジトリでsettings - pagesを開いて、Build and deployment の SourceにGithub actionsを選択しておく

    https://github.com/in0ho1no/lt_abt100chal/settings/pages

以下へアクセスしてトークンを用意する

    https://github.com/settings/tokens

実施する操作は以下の通り

- 「Generate new token(Classic)」を押下
- 「Scope」に「Repo」を選択する
- 「Generate Token」を押下する
- 表示されるTokenをコピーする

トークンを設定する

- 該当リポジトリの Settings を開く
- Security - Secrets and variables - Actionsを開く
- Secretsにて「New repository secret」を押下する
- Name: 任意の名称を入力する(LT_ABT100CHAL)
- Secret: 先の手順でコピーしたTokenをペーストする

Github Actionsのワークフローを用意する

    .github\workflows\deploy.yml
