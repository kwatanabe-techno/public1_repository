#  [ Air ] コーディング規約

## 命名規則

#### 略語

原則、略語を使用しないということになっていますが、一部標準化されている略語があります。

- acc: accessibility（アクセシビリティ）使用例: ButtonAccImpl
- auto: automatic（自動）使用例: autoLayout
- eval: evaluate（評価）使用例: EvalBindingResponder
- impl: implementation（実装）使用例: ButtonAccImpl
- info: information（情報）使用例: GridRowInfo
- num: number（数値）使用例: numChildren
- min: minimum（最小）使用例: minWidth
- max: maximum（最大）使用例: maxHeight
- nav: navigation（ナビゲーション）使用例: NavBar
- regexp: regular expression（正規表現）使用例: RegExpValidator
- util: utility（ユーティリティ）使用例: StringUtil

上記リストには、現在使われているすべての略語が含まれていない可能性があります。 上記に記載のない略語を使用する場合は、あらかじめ既存のソースコードを検証して、すでに同様のものが存在しないかを確認するようにしてください。 存在が確認されなかった略語については、略語使用の適切さについて十分に検討するようにしてください。

#### 型を表す名前

名前の一部として型を含めたい場合は、型を示す単語を名前の末尾に結合します。 ActionScript 1の古い規則であったように、略語の接尾辞（_mcなど）を連結して型を示す方法は使用しないでください。 たとえば、ボーダーのシェイプであればborder_mcではなく、border、borderSkinまたはborderShapeと命名します。<br>オブジェクトに最も適した名前は、その型の名前を大文字・小文字の記述だけ変えて表したものであることが大半です。<br>例: `var button:Button = new Button();`


#### 単語の区切り

識別子に複数の単語が含まれる際の単語区切り表現としては、キャメルケース方式（例: `LayoutManager、measuredWidth`）とアンダースコア（例: `object_proxy`）の２種類を使用しています。<br><br>一部のケースでは複合語を１単語として扱うかどうかについて不整合な箇所があります。<br>例: `dropdown、popUp、pulldown`<br><br>ごくまれに頭字語が２つ連続するようなケースも想定されますが、頭字語の綴りに関しては常に規則を守るようにしてください。 実際に使用されてはいませんが、例としてloadCSSURL()のようなケースが想定されます。 このような名前はできるだけ避けるようにします。


#### パッケージ名

小文字で綴りを開始し、以後の連語はキャメルケース方式で記述します。<br>例: `controls、listClasses`<br>パッケージの名前には、常に、動詞、形容詞または副詞ではなく、名詞または動名詞（動詞に-ingが付いた形）を使用するようにします。<br>同様のアイテムを複数実装するようなパッケージの場合は、そのアイテムを複数形で示す名前を付けるようにします。<br>例: `charts、collections、containers、controls、effects、events、formatters、managers、preloaders、resources、skins、states、styles、utils、validators`など。
特定の概念を実装するパッケージの名前には、動名詞を使用することが一般的です。<br>例: `binding、logging、messaging、printing` 以外の場面では、その「概念の名詞」を使用します。例: `accessibility、core、graphics、rpc`など。
FooBarコンポーネントをサポートするクラス群が含まれたパッケージであれば、fooBarClassesと名付けるようにします。

#### ファイル名

インポート可能なAPIのファイル名には、必ず、その中に含まれるパブリックAPIと同じ名前を付けます。 ただし、インクルードファイルの場合は、この規則に従う必要はありません。<br><br>[Style(...)]メタデータ向けのインクルードファイルの名前は、大文字でその綴りを開始し、以後の連語をキャメルケース方式で記述します。そして、最後の単語を「Styles」にします。<br>例: `BorderStyles.as、ModalTransparencyStyles.asなど`<br><br>個別のアセットファイルの名前は小文字でその綴りを開始し、各単語間にアンダースコアを挿入します。<br>例: `icon_align_left.png`

#### 名前空間名

名前の綴りを小文字で開始し、各単語間にアンダースコアを挿入します。<br>例: `mx_internal、object_proxy`

#### インターフェース名

名前の綴りを「I」で開始し、以後の連語をキャメルケース方式で記述します。<br>例: `IList、IFocusManager、IUID`

#### クラス名

大文字で綴りを開始し、以後の連語をキャメルケース方式で記述します。<br>例: `Button、FocusManager、UIComponent`
- EventのサブクラスをFooBarEventと名付けます。
- ErrorのサブクラスをFooBarErrorと名付けます。
- エフェクトのFooBarに関連付けられたEffectInstanceサブクラスをFooBarInstanceと名付けます。
- F- ormatterのサブクラスをFooBarFormatterと名付けます。
- Va- lidatorのサブクラスをFooBarValidatorと名付けます。
- ス- キニングクラスには、FooBarBackground、FooBarBorder、FooBarSkin、FooBarIcon、FooBarIndicator、FooBarSeparator、FooBarCursorなどの名前を付けます。
- ユーティリティクラスをFooBarUtilと名付けます。（パッケージは複数形ですが、クラスが単数形であるため、FooBarUtilsにはなりません。）
- ベースとなるクラスには、FooBarBase、ComboBase、DateBase、DataGridBase、ListBaseなどを用いるのが一般的です。

#### イベント名

小文字で綴りを始め、以後の連語はキャメルケース方式で記述します。<br>例: `move、creationComplete`

#### スタイル名

小文字で綴りを開始し、以後の連語をキャメルケース方式で記述します。<br> 例: `color、fontSize`

#### プロパティ名(変数及びgetter/setter)

小文字で綴りを開始し、以後の連語をキャメルケース方式で記述します。<br>例: `i、width、numChildren`<br>ループのインデックスにはi、上限値にはnをそれぞれ使用します。 内部ループのインデックスにはj、上限値にはmをそれぞれ使用します。<br>
for (var i:int = 0; i < n; i++)
{
    for (var j:int = 0; j < m; j++)
    {
        ...
    }
}
<br>for-inループの変数には、p（プロパティの頭文字）を使用します。<br>
for (var p:String in o)
{
    ...
}

#### ストレージ変数名

getter/setterのfooのストレージ変数には、_fooという名前を付けます。


#### 定数名

すべて大文字で綴り、各単語間にアンダースコアを挿入します。<br>例: `OFF、DEFAULT_WIDTH`
定数の値がString型の場合は、必ず識別子内の単語を定数の値の単語と一致させます。

#### メソッド名

小文字で綴りを開始し、以後の連語をキャメルケース方式で記述します。<br>例: `measure()、updateDisplayList()`<br>メソッド名には必ず動詞を使用するようにします。
一般的に、パラメータのないメソッドにはgetFooBar()やsetFooBar()といった名前を付けるのではなく、getter/setterとして実装するようにします。 ただし、getFooBar()が大量の演算処理を必要とする「重い」メソッドである場合は、この特徴が明らかになるよう、getterである代わりに、findFooBar()、calculateFooBar()、determineFooBar()といった名前を付けるようにします。<br>クラスがメソッドをオーバーライドし、ベースメソッドを公開し続けたいような場合は、ベース名の頭に「$」が付いた同名のメソッドを実装することで、これが可能になります。 <br>この場合、当該メソッドにはfinalの印を付け、superメソッドの呼び出し以外の機能を含めないようにします。<br><br>
mx_internal final function $addChild(child:DisplayObject):DisplayObject
{
    return super.addChild(child);
}

#### インベントハンドラ名

イベントハンドラには、イベントの種類を示す語句に「Handler」を結合した名前を付けます(HandlerをHに省略も可)。<br>例: `mouseDownHandler() mouseDownH()`
仮にハンドラが、サブコンポーネント（this以外のものなど）によってディスパッチされるイベント用のものである場合は、ハンドラ名の前にサブコンポーネント名を付け、これらをアンダースコアで結合します。
<br>例: `textInput_focusInHandler() textInput_focusInH()`<br>


#### 引数名

各setterの引数には、valueを使用します。<br>
正しい記述例:`public function set label(value:String):void`
謝った記述例:`public function set label(lab:String):void`
謝った記述例:`public function set label(val:String):void`

各イベントハンドラの引数には、（e、evtおよびeventObjではなく）eventを使用します。
例:`protected function set mouseDwonHandler(event:Event):void`

####リソールバンドル名

リソースバンドルに特定のパッケージ用のリソースが含まれている場合は、当該バンドルにパッケージと同じ名前を付けます。<br>例: `controls、{formatters}}、validators`

#### リソースキー名

小文字で綴りを開始し、以後の連語をキャメルケース方式で記述します。<br>例: `pm、dayNamesShort`

<br>
参考URL
	http://www.trick7.com/blog/2008/03/14-131809.php
    https://sourceforge.net/adobe/flexsdk/wiki/Coding%20Conventions-ja/