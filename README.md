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
  A([開始]) --> B[/入力/];
  B -->C{判断};
  B -- キャンセル --> G([終了]);
  C -- 真 --> D[[プログラム実行]];
  D --> E[[結果表示]];
  E --> B;
  C -- 偽 --> F[[エラー表示]];
  F --> G;
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
    acter サトモチ
    太郎->>花子: おはよう！
    activate 花子
    花子-->>太郎: おはようございます!
    deactivate 花子
    太郎->>サトモチ: おはよう！
    activate サトモチ
    サトモチ -->>太郎: おはよ～
    deactivate サトモチ
    太郎->>花子: 今どんな気分？
    loop 今日の気分
    　　花子->>花子: ハッピーな気分！
    end
    花子-->>太郎:機嫌がいいよ！
    花子->>サトモチ: 今どんな気分？
    loop 今日の気分
    　　サトモチ->>サトモチ: 疲れてる
    end
    サトモチ-->>花子:ベットに転がりたい気分 
```

## クラス図

### 条件
- 3つ以上
- 汎化と集約を含むこと
- カッコいいほど高得点

## 解答
```mermaid
classDiagram
    サトモチ o-- アイテム
    サトモチ :人間
    サトモチ :１０～２０代
    アイテム :筆箱
    アイテム :眼鏡
    筆箱 *-- 筆記用具
    筆記用具 :鉛筆
    筆記用具 :消しゴム
    筆記用具 :シャープペンシル
```
