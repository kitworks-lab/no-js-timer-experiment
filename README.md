# Zero-JS Focus Timer (Pure HTML + CSS Experiment)

**Live Demo:** https://kitworks-lab.github.io/no-js-timer-experiment/

JavaScript 0行（`<script>` タグ 0個 / インラインイベント属性 0個 / `javascript:` URL 0個）で動く、HTML + CSS だけのカウントダウンタイマー＆モード・テーマ切替UIの実験リポジトリです。

An interactive countdown timer with mode & theme switching built with **0 lines of JavaScript** (0 `<script>` tags, 0 inline event handlers, 0 `javascript:` URLs) — just `index.html` and `style.css`.

---

## 日本語 (JP)

### Chrome DevTools で「JS完全無効」を検証する手順
1. ライブデモを開く: https://kitworks-lab.github.io/no-js-timer-experiment/ （または `index.html` を直接ブラウザで開く）
2. Chrome DevTools を開く（`F12` または `Ctrl+Shift+I` / `Cmd+Option+I`）
3. コマンドメニューを開く（`Ctrl+Shift+P` / `Cmd+Shift+P`）
4. `Disable JavaScript` と入力し、**Debugger: Disable JavaScript** を実行
5. ページをリロードし、右上に `● JS ENGINE: DISABLED` バッジ（`<noscript>` 表示）が出ていることを確認
6. **▶ START TIMER** / **❚❚ PAUSE TIMER**、モード切替（Focus 25:00 / Break 05:00 / Sprint 01:00）、テーマ切替（Obsidian / Paper Ink / Matcha）を操作して動作を確認できます

### 使っている主なCSS機能
- **再生・一時停止**: 隠し `<input type="checkbox">` + `<label>` + `animation-play-state: paused | running`
- **秒カウント表示**: `@property --sec-left`（`<integer>`）+ `@keyframes` + `round()` / `mod()` + `counter()`（`::after` 擬似要素で描画）
- **モード＆テーマ切替**: 隠し `<input type="radio">` + 兄弟セレクタ（`:checked ~ .stage`）+ CSSカスタムプロパティ

### 純CSSの正直な限界
- ページリロードなしでの任意タイミング・リセット
- バックグラウンドタブでの時刻ズレ補正
- `localStorage` 等の永続保存や、OBS / WebSocket との外部連携

---

## English (EN)

### How to Test with JavaScript Completely Disabled (Chrome DevTools)
1. Open the live demo: https://kitworks-lab.github.io/no-js-timer-experiment/ (or open `index.html` locally)
2. Open Chrome DevTools (`F12` or `Ctrl+Shift+I` / `Cmd+Option+I`)
3. Open the Command Menu (`Ctrl+Shift+P` / `Cmd+Shift+P`)
4. Type `Disable JavaScript` and select **Debugger: Disable JavaScript**
5. Reload the page and verify the `● JS ENGINE: DISABLED` badge (rendered via `<noscript>`) appears in the header
6. Click **▶ START TIMER** / **❚❚ PAUSE TIMER**, switch modes (**Focus 25:00 / Break 05:00 / Sprint 01:00**), and switch themes (**Obsidian / Paper Ink / Matcha**)

### Pure-CSS Techniques Used
- **Play / Pause**: Hidden `<input type="checkbox">` + `<label>` toggling `animation-play-state`
- **Live Countdown Digits**: `@property --sec-left` (`<integer>`) animated via `@keyframes`, split into minutes/seconds with CSS `round()` & `mod()`, and rendered using CSS `counter()`
- **Mode & Theme Switching**: Hidden `<input type="radio">` + general sibling selector (`:checked ~ .stage`) + CSS custom properties

### Honest Limitations
- Arbitrary reset without reloading, drift-free wall-clock sync in background tabs, persistent storage, and OBS/WebSocket integration still require JavaScript.

---

## KitWorks Lab

- **Full OBS Widget Live Demos (TokiDock, GoalDock, etc.)**: https://kitworks-lab.github.io/
- **BOOTH (JP)**: https://kitworks.booth.pm/
- **Gumroad (EN / Global)**: https://earnbot7.gumroad.com/
- **YouTube Channel**: https://www.youtube.com/channel/UC_r4xzn2zs3gjbU3rXn3lpA

## License

MIT License — see [LICENSE](LICENSE).
