### 参考サイト
  * [Webまとめ](https://dev.classmethod.jp/etc/drawing_tools/)
  * [オンラインサーバ](http://www.plantuml.com/plantuml/uml/)
### mermaid
  * [公式サイト](https://github.com/mermaid-js/mermaid)
  * [UMLの書き方](http://www.itsenka.com/contents/development/uml/sequence.html)

#### フロー
``` mermaid
graph TD
A[Hard] -->|Text| B(Round)
B --> C{Decision}
C -->|One| D[Result 1]
C -->|Two| E[Result 2]
```

#### シーケンス図
``` mermaid
sequenceDiagram
Alice->>John: Hello John, how are you?
loop Healthcheck
    John->>John: Fight against hypochondria
end
Note right of John: Rational thoughts!
alt  health is bad
    John-->>Alice: Boo!
else health is good
    John-->>Alice: Great!
end
John->>Bob: How about you?
Bob-->>John: Jolly good!
```

#### ガントチャート
``` mermaid
gantt
section Section
Completed :done,    des1, 2014-01-06,2014-01-08
Active        :active,  des2, 2014-01-07, 3d
Parallel 1   :         des3, after des1, 1d
Parallel 2   :         des4, after des1, 1d
Parallel 3   :         des5, after des3, 1d
Parallel 4   :         des6, after des4, 1d
```

#### クラス図
``` mermaid
classDiagram
Class01 <|-- AveryLongClass : Cool
<<interface>> Class01
Class09 --> C2 : Where am i?
Class09 --* C3
Class09 --|> Class07
Class07 : equals()
Class07 : Object[] elementData
Class01 : size()
Class01 : int chimp
Class01 : int gorilla
class Class10 {
  <<service>>
  int id
  size()
}
```

#### 状態遷移図
``` mermaid
stateDiagram
[*] --> Still
Still --> [*]
Still --> Moving
Moving --> Still
Moving --> Crash
Crash --> [*]
```

### 円グラフ
``` mermaid
pie
"Dogs" : 386
"Cats" : 85
"Rats" : 15 
```

### PlantUML
  * シーケンス図
  * ユースケース図
  * クラス図
  * アクティビティ図
  * コンポーネント図
  * 状態遷移図
  * オブジェクト図
  * 配置図
  * タイミング図
  * ワイヤーフレーム
  * アーキテクチャ図
  * 仕様及び記述言語 (SDL)
  * ダイアグラム
  * ガントチャート
  * AsciiMath や JLaTeXMath による、数学的記法
### マインドマップ
  * [Text Mindmap](https://www.text2mindmap.com)
### ネットワーク図
  * [Inkpod](http://inkpod.carabiner.jp)
