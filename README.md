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
subgraph 階層開始
  A[階層を生成] --> B{現在の階層が1}
  B -->|true| C["あらたな冒険者がまた塔を登る……"]
  B -->|false| D {現在の階層を3で割ったあまりは1？}
  D -->|true| E[難易度増加表示]
  D -->|false| F[階数のみの表示]
end
  C --> G["移動する方向を入力してください(テンキー):"]
  E --> G
  F --> G
  
```

## シーケンス図
### 条件
- 3人以上
- メッセージをやり取りしない人がいないように
- 自己呼び出しを含むこと
- カッコいいほど高得点

## 解答
```mermaid
```

## クラス図

### 条件
- 3つ以上
- 汎化と集約を含むこと
- カッコいいほど高得点

## 解答
