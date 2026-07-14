# 8TDB_LP_TEST_1 — 巧虎雙語點讀圖鑑 LP（分割スクロール・テスト）

`kazuyukikonuma/shimajiro-stageplay-digest` の分割スクロール設計を**忠実ベース**に、P14「巧虎雙語點讀圖鑑」用へ内容だけ差し替えたテスト LP。色・フォント・ページ送りボタン・cover/outro・演出は shimajiro のまま（トーン調整は指示ベースで）。

## 構成（5画像）
- **開幕**（全画面ヒーロー）＝ `art/hero.jpg`
- **中間3ページ**（上＝固定写真がクロスフェード／下＝文字）＝ `art/mid1.jpg` `mid2.jpg` `mid3.jpg`
- **結末**（全画面ヒーロー）＝ `art/ending.jpg`

## 携帯で作る流れ
1. `art/` に上の5枚を決まった名前でアップ（`art/README.md` 参照・同名で上書き）。
2. `main` にコミット → GitHub Pages が即公開 → 携帯で確認。
3. 直したい所（文字・表示位置 `data-pos`・色等）を伝えれば反映。

## 公開（GitHub Pages）
Settings → Pages → Source: `main` / `/ (root)` → Save。数十秒で `https://kazuyukikonuma.github.io/8TDB_LP_TEST_1/` に公開。

## 中身の直し方（`index.html`）
各場面は1行： `<section class="block" data-bg="art/midN.jpg" data-pos="center 45%" data-title="…">` ＋ 中の `<h2>`（見出し）`<p>`（本文）。`data-pos` で写真の見せる位置を上下に調整。
