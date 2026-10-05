個人で行うシステム開発（ウォーターフォール）を、工程ごとに進めるための Claude スキル集です。汎用的にプロジェクト開始する際に利用できます。

## スキル一覧

| 工程                                                 | スキル                                                   | 成果物                                 |
| ---------------------------------------------------- | -------------------------------------------------------- | -------------------------------------- |
| システム構想（業界・テーマ／利用者／課題／提供価値） | [sysdev-concept](sysdev-concept/SKILL.md)                   | システム構想書                         |
| 全体ガイド・PJ計画                                   | [sysdev-overview](sysdev-overview/SKILL.md)                 | PJ計画書・トレーサビリティ表           |
| (要求定義)                                           | 省略（要件定義に吸収）                                   | -                                      |
| 要件定義                                             | [sysdev-requirements](sysdev-requirements/SKILL.md)         | 要件定義書                             |
| 全体設計                                             | [sysdev-architecture](sysdev-architecture/SKILL.md)         | 全体設計書                             |
| 基本設計                                             | [sysdev-basic-design](sysdev-basic-design/SKILL.md)         | 基本設計書                             |
| 詳細設計                                             | [sysdev-detailed-design](sysdev-detailed-design/SKILL.md)   | 詳細設計書                             |
| 開発/実装                                            | [sysdev-implementation](sysdev-implementation/SKILL.md)     | ソースコード・実装記録                 |
| 単体テスト                                           | [sysdev-unit-test](sysdev-unit-test/SKILL.md)               | 単体テスト仕様書兼結果                 |
| 結合テスト                                           | [sysdev-integration-test](sysdev-integration-test/SKILL.md) | 結合テスト仕様書兼結果                 |
| システムテスト                                       | [sysdev-system-test](sysdev-system-test/SKILL.md)           | システムテスト仕様書兼結果・完了報告書 |
| (受け入れテスト)                                     | 省略（システムテストのセルフ受け入れチェックで代替）     | -                                      |

## 使い方

開発するリポジトリ（以下「対象リポジトリ」）の `.claude/skills/` に、各スキルへのシンボリックリンクを張ります。対象リポジトリのルートで、次のコマンドを実行してください。

```bash
mkdir -p .claude/skills && for d in ~/Application/skills/sysdev-*; do ln -s "$d" .claude/skills/; done
```

- リンクなので、このリポジトリでスキルを更新すれば、対象リポジトリにもそのまま反映されます。
- 対象リポジトリで「要件定義をしたい」のように話しかけると、対応するスキルが自動で読み込まれ、その工程のタスクと成果物が提示されます。`/sysdev-requirements` のように直接呼び出すこともできます。
- 進め方は、`sysdev-concept` でシステムの概要を決め、`sysdev-overview` でPJ計画を立ててから各工程へ進むのが基本です。
- リンク先は絶対パスです。チームで共有する場合や別のマシンでは、このリポジトリの置き場所に合わせてリンクを張り直してください。
