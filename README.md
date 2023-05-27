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
  A([開始]) --> B[ラーメン食べたい];
  B-->C{お金があるか};
  C--真-->D[ラーメン屋を探す];
  C--偽-->E[自炊する];
  D-->F[よさげなラーメン屋を見つけた];
  F-->G{行く};
  G--真-->H[ラーメンを食べる];
  G--偽-->I{もう一度探す};
  I--真-->D;
  I--偽-->E;
  E-->J([終了]);
  H-->J;
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

```mermaid
sequenceDiagram
    actor 佐藤
    actor 高橋
    actor 山田
    佐藤->高橋: 高橋さん!好きです!
    loop 思考
    高橋->高橋:佐藤君の事が好きなのか?
    Note right of 高橋:高橋は山田の事が好き
    高橋-->>佐藤: ごめんなさい!
    高橋->山田:山田さん、好きです!
    山田-->高橋:私も高橋さんの事が好き!
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
