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
  A[熟睡] --> B[電話が鳴る];
  B --> C([出る]);
  B --> D([出ない]);
  D --> E((二度寝する));
  C --> F[起こしてほしい];
  F --> G((断る));
  F --> H([承諾する]);
  G --> E;
  H -- 起こす --> I[朝ご飯を食べに行こう];
  I --> J([行く]);
  I --> K((行かない));
  E --> L{目が覚める};
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
     actor 花子
  
actor 太郎
花子 ->> 太郎:おはよう
```

## クラス図

### 条件
- 3つ以上
- 汎化と集約を含むこと
- カッコいいほど高得点

## 解答
```mermaid
classDiagram
    キャラクター o-- アイテム
```
