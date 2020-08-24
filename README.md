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