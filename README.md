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
  A(["開始"]) --> B["値の入力"];
  B["値の入力"] --> C{"入力された値が負の値か？"};
  C{"入力された値が\n負の値か？"} --"負の値の場合"--> D["入力された値を表示"];
  C{"入力された値が\n負の値か？"} --"正の値の場合"--> F["入力された値の絶対値を表示"];
  D["入力された値を表示"] --> E["－１を掛ける"];
  E["－１を掛ける"] --> F["入力された値の絶対値を表示"]; 
  F["入力された値の絶対値を表示"] --> G(["終了"]);
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
    actor 田中
    太郎->>花子: おはよう！
    activate 花子
    花子-->>太郎: おはようございます!
    deactivate 花子
    太郎->>田中: おはよう！
    activate 田中
    田中-->>太郎: 今、夜中の９時だぞ？
    deactivate 田中
    花子-->>田中: おはようございます!
    activate 田中
    田中-->田中: （眠い…）
    田中-->>花子: …おやすみ
    deactivate 田中
    

```

## クラス図

### 条件
- 3つ以上
- 汎化と集約を含むこと
- カッコいいほど高得点

## 解答
```mermaid
classDiagram
direction TD
class キャラクター
   <<Interface>> キャラクター
    キャラクター: HP,攻撃力
    キャラクター: 攻撃()
    キャラクター "1" o-- "1..*" アイテム
    アイテム "*" <|-- 剣
    アイテム "*" <|-- 盾
    キャラクター "*" <|-- "1" プレイヤー
    キャラクター "*" <|-- "1..*" 敵
    敵 "*" o-- "1..*" ザコ
    敵 "*" o-- "1" ボス
```
