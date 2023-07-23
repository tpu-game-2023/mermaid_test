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
A[開始] --> B[ノード1]
B --> C[ノード2]
C --> D{条件分岐}
D --> |条件A成立| E[ノード3]
D --> |条件A不成立| F[ノード4]
E --> G[ノード5]
F --> G
G --> H[終了]

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
     participant A as  A
    participant B as  B
    participant C as  C

    A ->> A: 自己呼び出し

    A ->> B: メッセージ1
    B ->> A: メッセージ2

    A ->> C: メッセージ3
    C ->> A: メッセージ4

    B ->> C: メッセージ5
    C ->> B: メッセージ6
```

## クラス図

### 条件
- 3つ以上
- 汎化と集約を含むこと
- カッコいいほど高得点

## 解答
```mermaid
classDiagram
  class Person {
    - name: string
    - age: int
    + introduce(): void
  }
  
  class Student {
    - studentId: string
    + study(): void
  }
  
  class Teacher {
    - teacherId: string
    + teach(): void
  }
  
  Person <|-- Student
  Person <|-- Teacher
  
  class University {
    - name: string
    - location: string
    + enrollStudent(student: Student): void
    + hireTeacher(teacher: Teacher): void
  }
  
  Person "1" *-up- "1" University

```
