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
  start([開始]) --> A[階層を生成]
subgraph ゲーム
  W -->|"true"| A
  X -->|"true"|G["移動する方向を<br/>入力してください<br/>(テンキー):"]
subgraph 階層開始
  A --> B{"現在の<br/>階層"}
  B -->|1| C["あらたな冒険者が<br/>また塔を登る……"]
  B -->|1以外| D{"現在の階層を<br/>3で割った<br/>あまり"}
  D -->|1| E["難易度増加表示"]
  D -->|1以外| F["階数のみの表示"]
  C -->join{" "}
  E -->join
  F -->join
end

subgraph プレイヤーの行動
  join --> G
subgraph コマンド
  G --> H{"何が入力<br/>された？"}
  H -->| 5           | K{"巻物を<br/>持っている？"}
  K -->|true| L["巻物の使用"]
  K -->|false| NoMakimono["巻物を<br/>持っていません"]
  NoMakimono -->join0{" "}
  H -->|else       | J["行動に失敗"]
  J --> join0
  L --> join0
end
  H -->|2or4or6or8| I["移動先を決定"]
  join0 --> join3
subgraph 移動先処理
  I --> M{"移動先は<br/>エリア内か？"}
  M -->|true| N["移動"]
  M -->|false| CantMove["塔の壁から出ることは出来ません"]
  CantMove --> join1
  N --> O{"移動先は？"}
  O -->|"敵"| P["敵を倒す"]
  O -->|"アイテム"| Q["アイテムを取得"]
  O -->|"瓦礫"|　R["ダメージ"]
end
  O -->|"道"| join1{" "}
  P -->join1
  Q -->join1
  R -->join1
  join1 --> join3{" "}
end

subgraph 敵の行動
  S{"敵は生きて<br/>いるか?"} -->|"true"| T{プレイヤーと<br/>隣接して<br/>いるか?}
  S -->|"false"| join2{" "}
  T -->|"true"| U[攻撃]
  T -->|"false"| V[移動]
  U -->join2
  V -->join2
end
subgraph ターンエンド処理
  W{"階段に到着?"}
  W -->|"false"| X{"HP>0?"}
end
  join3 --> S
  join2 --> W
end
  X -->|"false"| finish(["終了"])
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
