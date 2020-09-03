# VFPracticsZone

# tabbedAccount.vfp
●　<Style>は、実際にはVisualforceマークアップではなくCSSマークアップの一部です。
このマークアップでは、inactiveTabとactiveTabという２種類のタブのスタイルが定義されます。

●　<apex:tabPanel> が、タブの生成に使用されます。次の属性の使用方法を確認してください。
 – tabClass 属性: 有効になっているタブの表示に使用されるスタイルクラスを指定します。
 – inactiveTabClass 属性: 無効になっているタブの表示に使用されるスタイルクラスを指定します。

# 標準オブジェクトリストページへのリダイレクト
●　ユーザを標準タブに移動するボタンやリンクの場合、コンテンツをリダイレクトして標準オブジェクトのリストを表示できます。
 -<apex:page action="{!URLFOR($Action.Account.List, $ObjectType.Account)}"/>

# myPage.vfp
●　<apex:inputField> タグは、タグの value 属性を設定することによって、取引先の name 項目にバイン
ドされます。式には、ページのほかの場所に項目の値を表示するためによく使用される {!account.name}
ドット表記が含まれます。
●　<apex:commandButton> タグには、action 属性があります。この属性の値は、標準取引先コントローラ
の save アクションを呼び出します。このアクションは、標準の取引先編集ページの [保存] ボタンと同じ
動作を実行します。

# myPage2.vfp
●　入力項目の表示ラベルの追加とカスタマイズ
● <apex:inputCheckbox>
● <apex:inputField>
● <apex:inputSecret>
● <apex:inputText>
● <apex:inputTextarea>
● <apex:outputField>
● <apex:outputText>
● <apex:selectCheckboxes>
● <apex:selectList>
● <apex:selectRadio>

# カスタム表示ラベルとエラーメッセージ
●　label属性が設定されている場合、項目が必須である時または一意になっている必要がある時などに、この属性はコンポーネントレベルのエラーメッセージで使用されます。
カスタム表示ラベルはカスタムエラーメッセージでは使用されません。
デフォルトのオブジェクト項目の表示ラベルが代わりに使用されます。
label属性を空の文字列に設定すると、デフォルトのオブジェクト項目の表示ラベルはすべてのエラーメッセージで使用されます。

# myPage3.vfp
●　フォームの項目のタブ順序の設定
Visualforce フォームには入力項目をタブで移動する場合の「自然な順序」 (左から右および上から下) が用意されています。
一部のフォームでは、この順序が必ずしも最も効率が良い配置方法、あるいはアクセスしやい配置方法ではない場合があります。
ページの入力コンポーネントおよびその他のコンポーネントで tabIndex および tabOrderHint 属性を使用してこのタブ順序を任意の順序に変更できます。

# VFDashboard.vfp
●　この Visualforce ページを使用するダッシュボードを作成する手順は、次のとおりです。
1. ダッシュボードを表示し、[編集] をクリックします。
2. 任意の列の上部にある [コンポーネントの追加] をクリックします。
3. コンポーネントの種類として [Visualforce ページ] を選択します。
4. 必要に応じて、ダッシュボードコンポーネントの上部に表示するヘッダーを入力します。
5. 必要に応じて、ダッシュボードコンポーネントの下部に表示するフッターを入力します。
6. [Visualforce ページ] ドロップダウンリストから、VFDash を選択します。
7. [保存] をクリックします。

# カスタムオブジェクトの関連リストの表示
●　Visualforce を使用してカスタムオブジェクトとその関連リストを表示するのはとても簡単です。
●　MyChildObject、MyMasterObject、および MyLookupObject という 3 つのカスタムオブジェクトがあったとします。
●　MyChildObject には MyMasterObject との主従関係があります (後者が主)。MyLookupObject にも MyChildObject との参照関係があります。
（列１）
<apex:page standardController="MyMasterObject__c">
	<apex:relatedList list="MyChildObjects__r" />
</apex:page>
（列２）
<apex:page  standardController="Account">
    <apex:relatedList list="contacts" />
</apex:page>

# インライン編集の有効化
インライン編集では、レ
コードの詳細ページで直接、項目値をすばやく編集できます。編集可能なセルには、その上にマウスを置くと鉛筆アイコン（✎）が表示され、編集できないセルの場合は、錠アイコンが表示されます。

# 非同期操作のための状況の提供
部分ページ更新などの Ajax 動作は、ページユーザが作業を進める間にバックグラウンドで発生する非同期イベントです。
使い勝手をよくするために、デザイナーは、現在進行中のバックグラウンドのアクティビティについてユーザに警告する状況要素を追加することがよくあります。

Visualforce は、<apex:actionStatus> タグを使った状況更新をサポートしています。
このタグを使用すると、startText または stopText属性によって、バックグラウンドのイベントの開始時または終了時にテキストを表示できます。
また、さらに上級の開発者であれば、画像やその他のコンポーネントを表示することができます。

# <apex:page> コンポーネントとその属性
<apex:page showHeader="false" applyHtmlTag="false" applyBodyTag="false"
           sidebar="false" standardStylesheets="false" docType="html-5.0">
</apex:page>
-docType="html-5.0" で、ページが最新の HTML5 docType を使用するように設定します。
-applyHtmlTag="false" および applyBodyTag="false" では、ユーザのマークアップで <html> および <body>タグが指定されるため、Visualforce に独自に生成しないように指示します。
(applyHtmlTag または applyBodyTag を false に設定した場合、<apex:page> コンポーネントの title 属性は無視されます。)
-showHeader="false"、sidebar="false"、およびstandardStylesheets="false"属性では、Salesforceユーザインターフェースとビジュアルデザインを Visualforce ページに追加する標準ヘッダー、サイドバー、およびスタイルシートが抑制されます。

# Visualforce PDF 表示の考慮事項および制限
PDF に表示する Visualforce ページを設計する場合、次の点を考慮します。本番環境で使用する前にページのPDF版の形式や外観を必ず確認してください。
(Visualforce PDF 表示サービスの制限は次のとおりです。)
-サポートされている表示サービスは PDF のみです。
-PDF 表示サービスでは PDF バージョン 1.4 が表示されます。
-Visualforce ページを PDF ファイルとして表示する機能は、印刷用にデザインされ、最適化されたページのためのものです。
-PDF ファイルとして表示された Visualforce ページは、ブラウザの設定に応じて、ブラウザに表示されるかダウンロードされます。
特定の動作は、ブラウザ、バージョン、ユーザ設定によって異なり、Visualforce では制御できません。
-PDF 表示サービスはページにマークアップとデータを表示しますが、ページに追加されたリッチテキストエリア項目のコンテンツ内に含まれる書式設定は表示されない可能性があります。
-空白やダッシュなどのブレークポイントがない長いテキスト行は、PDF 表示サービスではラップされません。
これは、非常に長い URL、レジストリエントリなどでよく発生します。
これらの行がページよりも広い場合、ページのコンテンツの幅が PDF ページの幅を超えて拡張されます。
その結果、コンテンツがページの両端からはみ出してしまいます。
-印刷用の書式設定が容易ではないか、入力やボタンなどのフォーム要素が含まれる標準コンポーネント、または書式設定にJavaScriptが必要なコンポーネントは使用しないでください。
-PDF 表示では、JavaScript で表示されるコンテンツはサポートされていません。
-Salesforce モバイルアプリケーションのページでは、PDF 表示はサポートされていません。
-ページで使用するフォントは、Visualforce PDF 表示サービスで使用できる必要があります。Web フォントはサポートされていません。
-PDF ファイルでページのすべてのテキスト (特に日本語などのマルチバイト文字やアクセント記号付きの国際文字)が表示されない場合は、CSSを調整してそれに対応するフォントを使用します。
-インライン CSS スタイルを使用する場合は、API バージョンを 28.0 以降に設定します。また、前の例のように 
<apex:page applyBodyTag="false"> を設定し、有効な静的 <head> および <body> タグをページに追加します。
-PDF ファイル作成時の最大応答サイズは、PDF ファイルとして表示される前で15MB未満です。この制限は、すべてのVisualforce要求の標準制限です。
-生成される PDF ファイルの最大ファイルサイズは、60 MB です
-生成された PDF に含まれるすべての画像の最大合計サイズは 30 MB です。
-PDF 表示では、data: URI スキーム形式で符号化された画像はサポートされていません。
-次のコンポーネントは、PDF として表示するときに 2 バイトのフォントをサポートしません。
	– <apex:pageBlock>
	– <apex:sectionHeader>
	PDF として表示するページでこのようなコンポーネントを使用することはお勧めしません。
-<apex:dataTable>または<apex:pageBlockTable>に表示される<apex:column>コンポーネントがない場合、PDFとしてのページの表示に失敗します。
この問題を回避するには、その子 <apex:column>コンポーネントが表示されない場合にテーブルコンポーネントの rendered 属性を false に設定します。

