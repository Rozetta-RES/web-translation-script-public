# ファイル説明

## ・翻訳スクリプト

ファイル名：rozetta-translate.min.js

本スクリプトの読み込みだけで、サイトを多言語化にすることができます。


## ・翻訳管理ツールスクリプト

ファイル名：rozetta-translate.min.js

開発環境で、本スクリプトを読み込むことで、画面上で翻訳の内容を編集することができます。

**一般ユーザーに公開する際に、必ず読み込まないようにしてください。**




# 使い方

## ・翻訳スクリプトの読み込み方

先ず、jsとcssフォルダをサイトのフォルダにダウンロードしてください。

下記の記述で「翻訳スクリプト」を読み込みます。

```html
<!-- import translation script -->
<script src="https://code.jquery.com/jquery-3.5.1.min.js" integrity="sha256-9/aliU8dGd2tb6OSsuzixeV4y/faTqgFtohetphbbj0=" crossorigin="anonymous" data-no-defer=""></script>
<script src="./js/rozetta-translate.min.js" userKey="YOUR USER KEY" lang="ja" contractId="YOUR CONTRACT ID" accessKey="YOUR ACCESS KEY" secretKey="YOUR SECRET KEY"></script>
```

jqueryが既に読み込んだ場合、二行目のjqueryスクリプトは省略できます。

利用する際に、契約が必要になります。それぞれの要素を入力してください。

    src: スクリプトのパス。実際のプロジェクトに合わせて調整してください。
    userKey：利用者識別キー。情報は弊社に問い合わせしてください。
    contractId: 契約ID。情報は弊社に問い合わせしてください。
    accessKey: アクセスキー。情報は弊社に問い合わせしてください。
    secretKey: シークレットキー。情報は弊社に問い合わせしてください。
    lang: オプション。サイトの元々の言語です。設定しない場合、デフォルトは日本語(ja)になります。





## ・翻訳管理ツールの読み込み方

「翻訳スクリプト」を読み込んだ上で、さらに下記の記述で「翻訳管理ツール」を読み込みます。

```html
<!-- import translation tool script -->
<link rel="stylesheet" href="./css/style.css">
<link rel="stylesheet" href="https://unpkg.com/spectre.css/dist/spectre-exp.min.css">
<link rel="stylesheet" href="https://unpkg.com/spectre.css/dist/spectre-icons.min.css">
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery-csv/1.0.21/jquery.csv.min.js" integrity="sha512-Y8iWYJDo6HiTo5xtml1g4QqHtl/PO1w+dmUpQfQSOTqKNsMhExfyPN2ncNAe9JuJUSKzwK/b6oaNPop4MXzkwg==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>
<script src="./js/rozetta-translate-tool.min.js"></script>
```

    src: スクリプトのパス。実際のプロジェクトに合わせて調整してください。

**一般ユーザーに公開する際に、必ず読み込まないようにしてください。**

