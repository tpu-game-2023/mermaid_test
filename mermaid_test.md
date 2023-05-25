test mermaid

# 流れ図
## 三目ならべの最善手

```mermaid
flowchart TD;
start([開始]) --> Q1{"先手？"};

subgraph "初期配置"
Q1 -- yes --> C[中心に置く];
Q1 -- no --> D[相手が置くのを待つ];
D --> Q2{"中心が空いてる？"};
Q2 -- yes --> F[中心に置く];
Q2 -- no --> G[右上に置く];
end


```
# シーケンス図



# クラス図
