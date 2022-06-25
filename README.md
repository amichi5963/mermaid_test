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
flowchart TB;
  start([開始]) --> A[階層を生成]
subgraph ゲーム
  W -->|"true"| A
  X -->|"true"|G["移動する方向を<br/>入力してください<br/>(テンキー):"]
subgraph 階層開始
  A --> B{"現在の<br/>階層"}
  B -->|1| C["あらたな冒険者が<br/>また塔を登る……"]
  B -->|else| D{"現在の階層%3"}
  D -->|1| E["難易度増加表示"]
  D -->|else| F["階数のみの表示"]
  C -->join{" "}
  E -->join
  F -->join
end
  D -->|2| Takara["財宝を入手"]
subgraph 財宝
  Takara -->|薬| Kusuri["HPを回復"]
  Takara -->|薬膳の指輪| Ring["回復量アップ"]
  Takara -->|遠見の眼鏡| Grass["視界アップ"]
  Takara -->|箱付き巻物| Box["巻物の所持上限アップ<br/>巻物入手"]
  Takara -->|鎧|　Armer["防御力アップ"]
  Kusuri --> joinT{" "}
  Ring --> joinT
  Grass --> joinT
  Box --> joinT
  Armer --> joinT
end
  B -->|10| Goal["おめでとう<br/>あなたは塔の10階にたどりついた"]
  Goal -->|冒険を続ける| G
  
subgraph プレイヤーの行動
  join --> G
  joinT -->G
  G --> H{"何が入力<br/>された？"}
  K -->|true| L["巻物の使用"]
  H -->|2or4or6or8| I["移動先を決定"]
  NoMakimono --> J
  H -->|else| J["行動に失敗"]
  J --> join3{" "}
  H -->|5 | K{"巻物を<br/>持っている？"}
subgraph 巻物処理
  K -->|false| NoMakimono["巻物を<br/>持っていません"]
  L --> DelStt[/破壊ループ<br/>Start\]
  DelStt --> Kill["敵を倒す"]
  Kill --> Break["瓦礫を道にする"]
  Break --> For{"視界内全マス<br/>破壊した?"}
  For -->|False| Kill
  For -->|True| DelEnd[\破壊ループ<br/>End/]
end
subgraph 移動先処理
  I --> M{"移動先は<br/>エリア内か？"}
  M -->|true| N["移動"]
  M -->|false| CantMove["塔の壁から出ることは出来ません"]
  N --> O{"移動先は？"}
  O -->|"敵"| P["敵を倒す"]
  O -->|"巻物"| Q["巻物を取得"]
  O -->|"薬"| Heal["HPを回復"]
  O -->|"瓦礫"|　R["ダメージ"]
  O -->|"道"| join1{" "}
  Heal -->join1
  P -->join1
  Q -->join1
  R -->join1
end
  CantMove --> J
  join1 --> join3
  DelEnd --> join3
end

subgraph 敵の行動
  S{"敵は生きて<br/>いるか?"} -->|"true"| EnView{"プレイヤーが<br/>視界内に<br/>いるか?"}
  EnView -->|"true"| T{プレイヤーと<br/>隣接して<br/>いるか?}
  EnView -->|"false"| NoMove["なにもしない"]
  S -->|"false"| NoMove
  NoMove -->join2{" "}
  T -->|"true"| U[攻撃]
  T -->|"false"| V[プレイヤーに近付く移動]
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
  X -->|"false"| death["あなたは力尽き、倒れた"]
  death -->finish(["終了"])
  Goal -->|塔を降りる| finish
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
