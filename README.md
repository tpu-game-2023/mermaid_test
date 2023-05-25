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
graph TB
    A(家を出る) --> B{今日の天気は雨?}
    B -- Yes --> C[家に戻る]
    C --> D[傘を取る]
    D --> E{やっぱり晴れた?}
    E -- Yes --> F[傘を投げ捨てる]
    F --> G[買い物に行く]
    E -- No --> G
    B -- No --> G
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
    actor 三郎
    太郎->>花子: おはよう！
    activate 花子
    花子-->>太郎: おはようございます！
    花子-->>花子: 今日の予定はありますか？
    activate 花子
    花子-->>花子: タスクの進捗はどうですか？
    花子-->>花子: 今日のミーティングの準備は進んでいますか？
    deactivate 花子
    activate 三郎
    花子->>三郎: こんにちは！
    三郎-->>太郎: こんにちは！
    花子-->>太郎: 今日の予定はありますか？
    deactivate 花子
    花子-->>三郎: 太郎さんに聞いてみましょう！
    花子->>太郎: はい、午後から会議があります。
    activate 太郎
    太郎-->>花子: 分かりました。お仕事頑張ってください！
    deactivate 太郎
    花子-->>太郎: ありがとうございます！
    花子-->>三郎: 太郎さんは午後から会議があるそうです。
    activate 三郎
    三郎-->>花子: そうなんですね。お忙しいんですね。
    deactivate 三郎
    花子->>三郎: そうですね。今日は私も仕事が忙しいです。
    activate 三郎
    三郎-->>花子: 頑張ってください！
    deactivate 三郎
    花子-->>太郎: お互い頑張りましょうね！
    activate 太郎
    太郎-->>花子: はい、頑張りましょう！
    deactivate 太郎

```

## クラス図

### 条件
- 3つ以上
- 汎化と集約を含むこと
- カッコいいほど高得点

## 解答
```mermaid
classDiagram
    class キャラクター{
        - 名前 : string
        - レベル : int
        - HP : int
        - 所持アイテム : List<アイテム>
        + ステータスを上げる() : void
        + アイテムを使用する(アイテム) : void
        + 攻撃する(キャラクター) : void
    }
    class アイテム{
        - 名前 : string
        - 効果 : string
    }
    class プレイヤーキャラクター{
        - 経験値 : int
        + 経験値を獲得する(int) : void
        + スキルを使う() : void
    }
    class 敵キャラクター{
        - 弱点 : string
        + 弱点を突く(キャラクター) : void
    }
    class パーティー{
        - メンバー : List<キャラクター>
        + パーティーメンバーを追加する(キャラクター) : void
        + パーティーメンバーを削除する(キャラクター) : void
    }

    キャラクター --|> プレイヤーキャラクター : 継承する
    キャラクター --|> 敵キャラクター : 継承する
    キャラクター --> アイテム : 所持する
    パーティー o-- キャラクター : メンバー

```
