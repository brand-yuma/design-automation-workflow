# design-automation-workflow

マーケティングクリエイティブ（LP・バナー等）のUIを生成し、Figmaにエクスポートする自動化ワークフロー。

## 概要

- HTML/CSS で UI を生成（Vite）
- Vitest でテスト実行
- Figma MCP でキャンバスに出力

## セットアップ

```bash
npm install
```

## コマンド

| コマンド | 説明 |
|---|---|
| `npm run dev` | 開発サーバー起動 |
| `npm test` | テスト実行 |
| `npm run build` | 本番ビルド |

## ディレクトリ構成

```
design-automation-workflow/
├── .github/
│   └── workflows/
│       └── ci.yml       # GitHub Actions CI
├── clients/             # クライアント別ブランドガイドライン
│   └── [client-name]/
│       └── .claude/
│           └── rules/
│               └── brand-guideline.md
├── src/                 # ソースファイル
└── dist/                # ビルド成果物（gitignore）
```

## CI/CD

`main` ブランチへのプッシュ・PRで自動実行：

1. **Lint & Test** — Vitest でテスト
2. **Build** — Vite でビルド、成果物を7日間保持
