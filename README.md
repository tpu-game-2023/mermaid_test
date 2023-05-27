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
  A([開始]) --> B[商品を受け取る];
  B --> C[商品をスキャンする];
  C --> D[お金を受け取る];
  D --> E{領収書を発行するか};
  E -- 真 --> F[領収書を発行する];
  F --> G[お釣りを渡す];
  E -- 偽 --> H[レシートを発行する];
  H --> G;
  G --> I([終了]);  
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
    actor みなみ
    actor かいと
    actor さちえ
    actor ゆきと
    actor じん
    actor しんぱん
    みなみ->>かいと: わかさぎ
    activate かいと
    かいと-->>みなみ: もう一回！
    deactivate かいと
    activate みなみ
    みなみ->>かいと: わかさぎ
    deactivate みなみ
    activate かいと
    かいと->>さちえ: わかさぎ
    deactivate かいと
    activate さちえ
    さちえ-->>かいと: もう一度！
    deactivate さちえ
    activate かいと
    かいと->>さちえ: わかさぎ
    deactivate かいと
    activate さちえ
    さちえ->>ゆきと: わびさび
    deactivate さちえ
    activate ゆきと
    ゆきと-->>さちえ: ワンモア！
    deactivate ゆきと
    activate さちえ
    さちえ->>ゆきと: わびさび
    deactivate さちえ
    activate ゆきと
    ゆきと->>じん: みやざき
    deactivate ゆきと
    activate じん
    じん-->>ゆきと: 何て？
    deactivate じん
    activate ゆきと
    ゆきと->>じん: みやざき！
    deactivate ゆきと
    activate じん
    じん->>しんぱん: しらさぎ
    deactivate じん
    activate しんぱん
    しんぱん->>みなみ: 「しらさぎ」で合っていますか？
    deactivate しんぱん
    activate みなみ
    みなみ-->>しんぱん: 全然違う！ 
    deactivate みなみ
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
