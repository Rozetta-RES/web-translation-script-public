# 翻訳スクリプト

ファイル名：rozetta-translate.min.js
バージョン：2.5.1
リンク：https://web-translation.rozetta-api.info/2.5.1/js/rozetta-translate.min.js

一行のJSコードで本スクリプトの読み込みだけで、サイトを多言語化にすることができます。


# 使い方

## ・翻訳スクリプトの読み込み方（ダウンロード）

先ず、jsフォルダの「rozetta-translate.min.js」をダウンロードしてください。

ウェブサイトにアップロードします（ローカルでも可能です）。アップロード先パスをメモしてください。

次に、HTMLファイル（あるいはSPAプロジェクトのエントリーポイントやジェネレータが利用するテンプレートファイル）に下記のスクリプトタグを追記します。生成されたHTMLからスクリプトが参照できるようソースパスにご注意ください。

```html
<!-- import translation script -->
<script src="https://code.jquery.com/jquery-3.5.1.min.js" integrity="sha256-9/aliU8dGd2tb6OSsuzixeV4y/faTqgFtohetphbbj0=" crossorigin="anonymous" data-no-defer=""></script>
<script src="お客様のアップロード先パス/rozetta-translate.min.js" userKey="お客様のユーザーキー" lang="ja" contractId="お客様の契約ID" accessKey="お客様のアクセスキー" secretKey="お客様のシークレットキー"></script>
```

## ・翻訳スクリプトの読み込み方（CDN）

ダウンロードをせず、直接にCDNで読み込むこともできます。

<!-- import translation script -->
```html
<script src="https://code.jquery.com/jquery-3.5.1.min.js" integrity="sha256-9/aliU8dGd2tb6OSsuzixeV4y/faTqgFtohetphbbj0=" crossorigin="anonymous" data-no-defer=""></script>
<script src="https://web-translation.rozetta-api.info/2.5.1/js/rozetta-translate.min.js" userKey="お客様のユーザーキー" lang="ja" contractId="お客様の契約ID" accessKey="お客様のアクセスキー" secretKey="お客様のシークレットキー"></script>
```

jqueryが既に読み込んだ場合、二行目のjqueryスクリプトは省略できます。

利用する際に、契約とキーが必要になります。契約の詳細は弊社に問い合わせください。

それぞれの要素を入力して、すぐにご利用いただけます。


    src: スクリプトのパス。実際のプロジェクトに合わせて調整してください。
    userKey：利用者識別キー。情報は弊社に問い合わせしてください。
    contractId: 契約ID。情報は弊社に問い合わせしてください。
    accessKey: アクセスキー。情報は弊社に問い合わせしてください。
    secretKey: シークレットキー。情報は弊社に問い合わせしてください。
    lang: オプション。サイトの元々の言語です（ISO 639-1）。設定しない場合、デフォルトは日本語(ja)になります。
    isRemoveNewLine: オプション。trueの場合は改行(\n)、タブ(\t)、キャリッジリターン(\r)を取り除きます。falseの場合はそのままにします。設定しない場合、デフォルトはtrueになります。
    ignoreNodes: オプション。JSON形式の配列。指定された部分とその中に含んだ全内容は翻訳されません。複数指定可能、複数の場合一つの条件に満たされると翻訳しません（ORロジック）。タグ、id、class名に適用します。例：ignoreNodes='[{"class": "ignore-btn"}, {"id": "title-984"}, {"tag": "h4"}]'の場合は、「class名にignore-btnがある」、「idがtitle-984」、「<h4></h4>タグ」以内のテキストとその中に含んだ全内容は翻訳されません。
    isApplyResultToSameText: オプション。trueの場合は同じの原文を、html内上から一番目の訳文が適用されます。編集があった場合もすべて一番目の編集結果が適用されます。設定しない場合、デフォルトはfalseになります。
    queryPageKeys: オプション。文字列の配列。クエリパラメータで全く別のページ内容を表示する場合、指定してください。例：ページのURLは「https://sample.com/post?pid=1&key=accesskey」と「https://sample.com/post?pid=2&key=accesskey」がクエリの「pid」でそれぞれ全く違う内容を表示する場合、queryPageKeys='[{"pid"}]'で指定してください。一方、表示内容に影響のないクエリパラメータ「key」は指定しないようにしてください。
    languagesExtension: オプション。文字列の配列。デフォルト以外の言語の追加が可能です。例：languagesExtension='[{"language": "fr", "label": "français", "translatingMessage": "Traduction en cours"}]'で、フランス語の追加ができます。languageはISO 639-1コードで指定してください。"label"は選択メニュー上のテキスト。"translatingMessage"は翻訳中、表示するメッセージです。
    isDynamicTranslate: オプション。trueの場合はページがロード後に表示されるテキストも翻訳されます。デフォルトはfalseになります。
    isIgnorePath: オプション。trueの場合はページに問わず、一致した原文内容が存在すれば、翻訳をかけずにキャッシュで反映します。デフォルトはfalseになります。
    fieldId: オプション。翻訳に適用される分野です。デフォルトは1（一般）です。
    isAllowPathQuery: オプション。trueの場合、URLのパスに言語パラメータ（ISO 639-1）が含んでいる場合、指定の言語で翻訳を適用します。例：「https://www.rozetta-sample.jp/en/page1」がURLの場合、パスにenがあるため、言語は英語で翻訳します。デフォルトはfalseになります。


# FAQ

**・スクリプトを導入するだけで、サイトの多言語化ができますか？**

はい、一般的なサイトであれば、「言語選択のメニュー」と「サイトの文字を抽出して翻訳」が自動にできます。


**・ウェブサイトの外観に合わせて設定したいです。**

はい、できます。それぞれのクラス名のcssを上書きすればよいです。

言語選択UI全体：rozetta-language-selector
選択中言語のハイライト：rozetta-language-selector-selected
選択肢メニュー全体：rozetta-language-selector-menu
選択肢メニューの一要素：rozetta-language-selector-menu-item


**・翻訳されていない箇所があります。/ 翻訳が動作していません。**

ウェブサイトの設計はそれぞれありますので、詳しくは弊社へ問い合わせください。


**・表示する言語を減らしたい。**

CSSでメニューを隠せば減らせます。以下日英のみ表示の例（簡中、繁中、タイを隠す）：
```html
<style>
    /* zh-CN (簡体中国語) */
    .rozetta-language-selector-menu-item:nth-child(3),
    /* zh-TW (繁体中国語) */
    .rozetta-language-selector-menu-item:nth-child(4),
    /* th (タイ語)*/
    .rozetta-language-selector-menu-item:nth-child(5) { display:none; }
</style>
```



# 訳文編集ツールの導入（必要に応じて）

ステーション/開発環境で訳文編集ツールでチェックし、簡単に翻訳内容編集することができます。

編集された結果はそのままに本番環境で反映されます。

英訳で長くなったセンテンスもツールの文字サイズ調整で、外観を維持することができます。

## ・訳文編集ツールスクリプト

ファイル名：rozetta-translate-tool.min.js
バージョン：2.5.0
リンク：https://web-translation.rozetta-api.info/2.5.0/js/rozetta-translate-tool.min.js

cssファイル：style.css
バージョン：2.5.0
リンク：https://web-translation.rozetta-api.info/2.5.0/css/style.css

開発環境で、本スクリプトを読み込むことで、画面上で翻訳の内容を編集することができます。


**一般ユーザーに公開する際に、決して読み込まないようにしてください。**

## ・訳文編集ツールの読み込み方（ダウンロード）

「翻訳スクリプト」を読み込んだ上で、さらに下記の記述で「訳文編集ツール」を読み込みます。

```html
<!-- import translation tool script -->
<link rel="stylesheet" href="./css/style.css">
<link rel="stylesheet" href="https://unpkg.com/spectre.css/dist/spectre-exp.min.css">
<link rel="stylesheet" href="https://unpkg.com/spectre.css/dist/spectre-icons.min.css">
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery-csv/1.0.21/jquery.csv.min.js" integrity="sha512-Y8iWYJDo6HiTo5xtml1g4QqHtl/PO1w+dmUpQfQSOTqKNsMhExfyPN2ncNAe9JuJUSKzwK/b6oaNPop4MXzkwg==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>
<script src="./js/rozetta-translate-tool.min.js"></script>
```

    src: スクリプトのパス。実際のプロジェクトに合わせて調整してください。

**一般ユーザーに公開する際に、決して読み込まないようにしてください。**


## ・訳文編集ツールの読み込み方（CDN）

ダウンロードをせず、直接にCDNで読み込むこともできます。

```html
<!-- import translation tool script -->
<link rel="stylesheet" href="https://web-translation.rozetta-api.info/2.5.0/css/style.css">
<link rel="stylesheet" href="https://unpkg.com/spectre.css/dist/spectre-exp.min.css">
<link rel="stylesheet" href="https://unpkg.com/spectre.css/dist/spectre-icons.min.css">
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery-csv/1.0.21/jquery.csv.min.js" integrity="sha512-Y8iWYJDo6HiTo5xtml1g4QqHtl/PO1w+dmUpQfQSOTqKNsMhExfyPN2ncNAe9JuJUSKzwK/b6oaNPop4MXzkwg==" crossorigin="anonymous" referrerpolicy="no-referrer"></script>
<script src="https://web-translation.rozetta-api.info/2.5.0/js/rozetta-translate-tool.min.js"></script>
```