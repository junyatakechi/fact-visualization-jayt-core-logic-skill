---
name: fact-visualization-jayt-core-logic-skill
description: "文脈: 目的に沿った事実の図解。種類: 中核判断。使う場面: 名前で指名されたときだけ使い、会話の内容からは選ばない。"
metadata:
  skill-version: "0.3.3"
  design-name: "人の判断を切り出すAgent Skillsの設計"
  design-version: "6.0.1"
  design-url: "https://app.notion.com/p/3eaf2fd6925e8102b86fee3b6b3dd5a3"
---

# 索引

| 判断名 | 扱うこと | ファイル | 依存する判断 | 計算 |
|---|---|---|---|---|
| 図のメッセージ | 事実を図解するとき、1つの図に何を言わせ、図の題と図の周りに何を書くか | [message.md](references/message.md) | — | — |
| 形の選び方 | 事実を図解するとき、比べ方に応じて、どの形の図にするか | [chart-form.md](references/chart-form.md) | `message.md` | — |
| 色 | 事実を図解するとき、色をどう使い、色の意味をどう示すか | [color.md](references/color.md) | `message.md` | — |
| 値と軸の見せ方 | 事実を図解するとき、値と軸の目盛りをどう見せるか | [value-labels.md](references/value-labels.md) | — | — |
| 図の示唆 | 事実を図解したとき、図の下に、どんな示唆を、どう書くか | [insights.md](references/insights.md) | `message.md` | — |

# このスキルの設計上の決まりごと

1. このスキルは判断を答えるだけで、判断の対象もデータも持たない。対象の値は、材料の写しとして受け取る。データを取りに行かず、保存もせず、IDも受け取らない。
2. 答える範囲は、聞きたい事を索引の「扱うこと」と照らして決める。索引の「依存する判断」にある判断を、先に出す。
3. 判断ファイルの「求める材料」がそろわなければ答えない。計算がある判断は、`uv run <skill-dir>/scripts/judge.py <判断> <材料.json>` で計算する。<判断> は `references/` のファイル名。依存する判断の材料も、一緒に渡す。
4. 答えは、指定された形にそろえ、理由と組にして返す。
5. 中核判断は、判断ファイルで答えられなければ、一般論で答えず「判断が無い」と返す。「未決」に当たったら、未決であることと、決めるまでの暫定の扱いを含める。一般的な業務知識は、判断ファイルに無いことを一般知識で補ってよい。
