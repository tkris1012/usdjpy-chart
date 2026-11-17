# USD/JPY チャート（iPhone縦画面用ブラウザアプリ）

USD/JPY をリアルタイムで表示する、iPhone縦画面向けのチャートアプリです。

- **上半分**：ローソク足（M1 / M5 / M15 / M30 / H1 / H4 / D1 を切り替え、足確定までの残り時間を表示）
- **下半分**：ティックチャート（直近3000ティック、1分あたりのティック数）
- 時刻はすべて日本時間。週末（NY時間 金曜17:00〜日曜17:00）は「休場中」と表示

## データソース（画面右上の ⚙︎ から設定）
| モード | ティック | 過去足 | 必要なもの |
|---|---|---|---|
| **Finnhub＋Twelve Data（推奨）** | Finnhub WebSocket（OANDA:USD_JPY） | Twelve Data REST | 両方の無料APIキー |
| Twelve Data のみ | Twelve Data WebSocket | Twelve Data REST | Twelve Data APIキー（無料プランでは WebSocket が使えない場合あり） |
| デモ | 擬似データ | 擬似データ | なし |

- APIキーの取得：[Finnhub](https://finnhub.io/register) / [Twelve Data](https://twelvedata.com/register)（どちらも無料登録）
- APIキーは**このリポジトリには含まれません**。iPhoneのブラウザ内（localStorage）にだけ保存されます。
- Twelve Data 無料プランは 1分8回・1日800回まで。過去足は時間足ごとに1回だけ取得し、以降はティックから足を更新します。

## 公開（GitHub Pages）
1. GitHub のリポジトリ画面 → **Settings → Pages**
2. **Source** を「Deploy from a branch」、**Branch** を `main` / `/(root)` にして Save
3. 1〜2分後に `https://<ユーザー名>.github.io/usdjpy-chart/` で開けます
4. iPhone の Safari で開き、**共有 → ホーム画面に追加** で全画面アプリとして使えます

## 構成
```
index.html                         アプリ本体（HTML/CSS/JS を1ファイルに収録）
apple-touch-icon.png               ホーム画面用アイコン
vendor/lightweight-charts/         TradingView Lightweight Charts™ v5.3.0（Apache License 2.0）
```
