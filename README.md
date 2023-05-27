# 課題
Mermaidを触ってみよう

マークダウンファイルを編集して、Mermaidで図を描いてみよう

# 取り組み方
* 本プロジェクトをforkしてください。
* README.mdを編集して、Mermaidを使いこなしてください
* できたらプルリクエストを出します

# 課題項目
## 流れ図
### 解答
- 五目並べの判定文
```mermaid
flowchart LR;
  Z([開始]) --> A;
  A[/設置/] --上からチェック--> B{マスを確認};
  B -- 真 --> C[/個数カウント増加/];
  B -- 偽 --> D{方向チェック};
  C --> E{個数カウントチェック};
  E -- 1, 2, 3, 4, --> F{一つ先をチェック};
  F --真--> C;
  F --偽--> G[個数カウントリセット];
  G --> D;
  D --右上以外--> I[時計回りで方向切り替え];
  I --> B;
  D -- 右上 --> J(相手ターンへ);
  J --> A;
  E -- 5 --> H{勝敗判定};
  subgraph "勝敗"
   H --自分の勝ち-->K[勝利];
   H --相手の勝ち-->L[敗北];
   K --> M([終了]);
   L --> M;
  end
```

## シーケンス図
### 解答
- 辛い現実
```mermaid
sequenceDiagram
    actor A
    actor B
    actor C
    A->>+B: おはよう！
    B->>-A: おはよう。
    A->>B: 会話している
    B->>A: 会話している
    C->>+B: おはようございます。
    activate C
    activate B
    B->>-C: おはようございます!
    A-->>C: おはよう！
    B->>+C: 会話している
    A-->>C: 話しかけようとしている
    C->>-B: 会話している
    A->>A: 会話に参加出来ない
    A->>A:　（´・ω・｀）
    deactivate B
    deactivate C
```

## クラス図
### 解答
- 人間
```mermaid
classDiagram
   class Human {
    -string Name
    -int Age
    -string Gender
    -bool Health
    +checkHealth(Condition) bool
    }
    
    class Mental{
    -int Value
    -string Condition
    +getValue(Pvalue, Nvalue) int
    get Condition(Value) string
    }
    
    class Positive{
    int Pvalue
    +getPvalue() int
    }

    class Negative{
    int Nvalue
    +getNvalue() int
    }
    
    Human o-- Mental
    Mental <|-- Positive
    Mental <|-- Negative
    Negative <|-- A
    Negative <|-- B
    Negative <|-- C
    Negative <|-- D
    
    
    
```
