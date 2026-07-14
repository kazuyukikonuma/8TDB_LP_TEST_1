# 引継ぎメモ（HANDOFF）— まずこれを読む

> P14「巧虎雙語點讀圖鑑」LP（分割スクロール・テスト）。スマホ／WEB版で続きを作る用。
> 公開＝`main` にコミット＝GitHub Pages で即反映。

## 0. いまの状態
- **公開中**：https://kazuyukikonuma.github.io/8TDB_LP_TEST_1/ （`main` にコミットで即更新）
- **1ファイル完結**：`index.html`（HTML/CSS/JS 全部）＋ `art/`（画像）。
- **土台**：`kazuyukikonuma/shimajiro-stageplay-digest` の分割スクロールを**忠実コピー**し、文字と画像だけ P14 用に差し替え済。色・フォント・**ページ送りボタン**・cover/outro・演出は shimajiro のまま。
- **画像5枚アップ済**（手繪動畫電影風）：`art/hero.jpg` `mid1.jpg` `mid2.jpg` `mid3.jpg` `ending.jpg`。

## 1. ★ すぐやる修正（TODO・上から順に）
- [ ] **cover / outro の galaxy 演出を消す**（最優先）。暖かい絵の上に**白い流星**と暗い爆発グローが乗っていて変。`index.html` の `<div class="cover" id="cover">` と `<div class="outro" id="outro">` の中の `<div class="burst">` `<div class="glow">` `<div class="meteors">...</div>` を削除（テキスト `cover-inner`・ボタン `cover-cue` は残す）。
- [ ] **mid2 の写真位置**：`mid2.jpg` はやや縦長（3:4）でステージで顔が切れ気味。該当 `<section ... data-bg="art/mid2.jpg" data-pos="center 45%">` の `data-pos` を `center 32%` くらいに（上寄せ）。
- [ ] **トーン調整（任意）**：暗色→明るく等。CSS 冒頭 `:root{ --paper / --black / --gold / --cyan ... }` の色を変える。
- [ ] **参考用 png の整理（任意）**：`art/` の `4books.png` `all.png` `babyS1.png` `book1〜4.jpg` `P14主機.png` は LP 未使用（GPTへの参考写真）。消しても表示に影響なし。

## 2. 構造マップ（どこを直すか）
- **開幕（全画面）**＝`<div class="cover" id="cover" style="...hero.jpg">` … 大標=`.cover-h1`／一句=`.cover-sub`／ボタン=`.cover-cue`。
- **中間3ページ**＝`<main class="scroller">` 内の `<section class="block" data-bg="art/midN.jpg" data-pos="center 45%" data-title="…">` × 3。中の `<h2>`=見出し、`<p>`=本文。`data-pos` で写真の見せる位置を上下調整。上の固定写真は `.stage` がスクロールに同期して切替。
- **結末（全画面）**＝`<div class="outro" id="outro" style="...ending.jpg">` … 大標=`.cover-h1`／一句=`.cover-sub`／ボタン=`.cover-cue`。
- **ページ送りボタン**＝`<div class="pager-nav">`（`#pagerUp` `#pagerDown`）。

## 3. スマホでの直し方
1. GitHub アプリで `index.html` を開く →（鉛筆）編集 → 直す → **Commit → `main`**。
2. 画像差し替え＝`art/` に**同じ名前**でアップ（上書き）＝コード変更不要。
3. コミット＝数十秒で Pages に反映。携帯でリロードして確認。

## 4. 文字（P14 第4回・定稿。画像内には入れない＝オーバーレイ）
- HERO：**當他想再點一次，巧虎就把世界說給他聽** ／ 巧虎＋4本圖鑑，一點就聽見中英雙語、真實音效與唸謠。 ／ ボタン：先聽巧虎怎麼回話
- mid1：**主角不是規格，是會回話的巧虎** ／ 寶寶伸手時，巧虎把聲音帶回來。
- mid2：**四本圖鑑，把今天看得到的世界放進來** ／ 生活、動物、交通工具，約1000個中英詞彙；另附育兒誌。
- mid3：**一點，不只是一個聲音** ／ 中英雙語、真實音效與唸謠，可反覆聽。
- ending：**不是現在就要他記住很多英文，** ／ 是讓他每次把手伸向世界，都聽見一個能和你一起發現的回應。 ／ ボタン：看看完整內容

## 5. 画像サイズ（作り直す時）
- 全画面（hero/ending）＝**1080×2340（9:19.5）**、主役は上〜中央・下1/3は文字用に空ける。
- 中間（mid1-3）＝**1080×1170（12:13）**、下辺は文字帯へグラデで溶ける。
- JPEG・各〜400KB。畫風＝手繪動畫電影風。巧虎IPは官方素材参照のみ・對外前人眼必檢。

## 6. 元ネタ
`kazuyukikonuma/shimajiro-stageplay-digest`（分割スクロールの正本）。
