# fact-visualization-jayt-core-logic-skill

事実を、見せる目的に沿って図解するときに、作成者が下した中核判断を、理由とともに持つロジックスキル。
1つの図に何を言わせ、題に何を書くか・比べ方に応じた図の形・色の使い方と色の意味の示し方・値と軸の見せ方を答える。

## 必要なもの

- [Claude Code](https://docs.claude.com/en/docs/claude-code/overview)

## インストール

```bash
git clone https://github.com/junyatakechi/fact-visualization-jayt-core-logic-skill.git ~/.claude/skills/fact-visualization-jayt-core-logic-skill
```

特定のプロジェクトだけで使うなら、`<プロジェクト>/.claude/skills/` の中でクローンする。

## セットアップ

なし。

## 使い方

主に、アプリケーションスキルから呼ばれる。
直接聞くときも、`/fact-visualization-jayt-core-logic-skill` で名前を指名する。指名しないと、このスキルは読み込まれない。

- 「/fact-visualization-jayt-core-logic-skill 週ごとの売上と目標を比べる図は、どの形にする？」
- 「/fact-visualization-jayt-core-logic-skill この図の題は何と書けばいい？」
- 「/fact-visualization-jayt-core-logic-skill どの棒を強調色にする？」
