# 課題
Mermaidを触ってみよう

マークダウンファイルを編集して、Mermaidで図を描いてみよう

# 取り組み方
* 本プロジェクトをforkしてください。
* README.mdを編集して、Mermaidを使いこなしてください
* できたらプルリクエストを出します

# 課題項目
## 流れ図
### 条件
- 開始と終了ノードをつける
- 条件分岐を組み込む
- 5ノード以上
- カッコいいほど高得点

## 解答
```mermaid
flowchart TD;
  A([熟睡]) --> B{電話が鳴る};
  B --> C[/出る/];
  B --> D[/出ない/];
  D --> E[二度寝する];
  C --> F{起こしてほしい};
  F --> G[/断る/];
  F --> H[/承諾する/];
  G --> E;
  H -- 起こす --> I{朝ご飯を食べに行こう};
  I --> J[/行く/];
  I --> K[/行かない/];
  E --> L([目が覚める]);
  J --> L;
  K --> L;
```

## シーケンス図
### 条件
- 3人以上
- メッセージをやり取りしない人がいないように
- 自己呼び出しを含むこと
- カッコいいほど高得点

## 解答
```mermaid
sequenceDiagram
　　 actor oda as　織田
     actor toy as 豊臣
     actor tok as 徳川
     
oda->>+toy:天下統一したくない？
toy-->>+tok:どう思う？
tok-->>-toy:いいんじゃない？
toy->>-oda:いいですね
oda->>+toy:東とかどう？
toy-->>+tok:東から行きたいって言ってる
tok-->>toy:上杉・武田が元気だからやめたほうがいい
toy-->>tok:殿の言うことを否定するのか
oda->>toy:豊臣？どう思うよ
Note over oda,toy:催促
toy-->>tok:なんて言えばいい？
tok-->>-toy:"西のほうが殿にお似合いです"って言っときな
toy->>-oda:流石は殿です！
oda->>toy:であろう、であろう
tok-->>toy:あーあ
toy-->>tok:仕方がないだろう
toy->>oda:私も東が良いと思っていました！
oda->>toy:ふむ、それなら西から行こう
toy->>oda:え？
```

## クラス図

### 条件
- 3つ以上
- 汎化と集約を含むこと
- カッコいいほど高得点

## 解答
```mermaid
classDiagram
class Subject{
-string 科目名
-int    授業コード
-string 担当教員
+新しい講義を追加する()
+講義を閉講する()
}
class チーム制作1{
-string チーム名 
-int    受講人数
+休講する()
}
class Team{
-int　  チーム人数
-string 制作タイトル
+合否()
}
class Planning{
-int    人数
-string 役割
}
class Design{
-int    人数
-string 役割
}
class Program{
-int    人数
-string 役割
}
class StudentA{
-int    学籍番号
-string 氏名
-string 性別
-int    成績
-int    平均出席率
+出席する()
}
class StudentB{
-int    学籍番号
-string 氏名
-string 性別
-int    成績
-int    平均出席率
+出席する()
}


    Subject "1" <|-- "1..*" チーム制作1
    チーム制作1 "1"　o-- "1..*" Team
    Team "1" <|-- "1..*" Planning 
    Team "1" <|-- "1..*" Design
    Team "1" <|-- "1..*" Program
    Planning　"1" <|-- "1" StudentA:所属する
    Program　"1" <|-- "1" StudentB:所属する
```
