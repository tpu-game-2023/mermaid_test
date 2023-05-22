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
flowchart LR;
  A[/開始/] --> B([敵発見])
  B --> C([行動]);
  C -- 逃げる --> D[[逃げ切れなかった]];
  D --> B;
  C -- 戦闘 -->E{勝利};
  E --> F([帰宅]);
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
    actor 太郎
    actor 花子
    actor よしみ
    太郎->>花子: おはよう！
    activate 花子
    花子-->>太郎: おはようございます!
    deactivate 花子
    よしみ->>花子 :How are you today?
    よしみ->>太郎 :How are you today?
    activate　花子
    activate　太郎
    花子->>よしみ:私は元気です。ありがとう。
    太郎->>よしみ:僕は病気だよ。皆勤賞貰いたいからきたよ。
    deactivate　花子
    deactivate　太郎
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
