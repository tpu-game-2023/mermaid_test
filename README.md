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
   A([開始]) --> B[/技選択/];
   B --> C[マッチ開始];
   C --> D{コイン表裏確認};
   D --表-->E[技威力上昇];
   D --裏--> F{コインを全て使用したか};
   E-->F;
   F--真-->G{技威力が敵よりも大きいか};
   F--偽-->D;
   G--真-->H[敵の技コインを1枚減らす];
   G-->偽-->I[自身の技のコインを1枚減らす];
   H-->J{相手の技のコインが0枚以下};
   I-->K{自身の技のコインが0枚以下};
   J--真-->L[マッチ勝利];
   J--偽-->D;
   K--真-->M[マッチ敗北];
   K--偽-->D;
   L-->N([終了]);
   M-->N;
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
    太郎->>花子: おはよう！
    activate 花子
    花子-->>太郎: おはようございます!
    deactivate 花子
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
