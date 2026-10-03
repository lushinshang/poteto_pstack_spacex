# 米其林廚房：Poteto 讓 agent 自己把 PR 合進主分支的做法

Matt Pocock 在直播裡訪談 pstack 作者 Poteto（Cursor／SpaceXAI）的深度導讀。

網頁：https://lushinshang.github.io/poteto_pstack_spacex/

## 200字介紹

Poteto 在 X 上說，她上個月把約 2,000 至 2,500 個 PR 送進 production（本人自報）。Matt Pocock 在直播裡追問她怎麼做到。她的起點，是發現自己成了 agent 與 Chrome DevTools 之間的「肉體代理人」，於是先給 agent 手和眼，也就是驗證 skill 與確定性腳本，再把重複出現的錯誤變成 lint 規則，整理環境。接著用外迴圈（Slack、issue 帶來的新資訊）與內迴圈（coordinator 派工給 agents），讓 agent 自己取得背景，最後以抽樣取代逐一把關，隔天翻 commit 歷史，發現問題就改環境。單向門怎麼辦？她說答案取決於領域能不能被驗證。本文把訪談內容、官方資料與導讀者的整理分開標示。

## 檔案

| 檔案 | 說明 |
|---|---|
| `index.html` | 單檔網頁，可直接用瀏覽器開啟 |
| `poteto_pstack_spacex.md` | 深度導讀 Markdown 原稿 |
| `share_post.md` | 純文字社群分享文（約 220 字） |
| `images/web/` | 全景圖與兩張章節配圖（WebP，各有桌面 16:9 與手機 9:16） |
| `images/hero/og_1200x630.png` | 連結分享預覽用的封面圖 |

## 原始資料

- 影片：[LIVE: Poteto (creator of pstack) on shipping 1,000's of PR's a month at SpaceX](https://www.youtube.com/watch?v=MN9dGgmLyso)（Matt Pocock 頻道，約 1 小時 7 分鐘，2026-10-03）
- 逐字稿：自動轉寫的字幕檔，有誤聽，專有名詞已依官方資料校正；字幕檔本身未隨本 repo 公開。

## 重要來源

- 官方與第一手（皆於 2026-10-03 讀取）：
  - [pstack（cursor/plugins）](https://github.com/cursor/plugins/tree/main/pstack)：README、`plugin.json`、LICENSE（MIT），v0.15.6
  - [Cursor is now a part of SpaceX](https://cursor.com/blog/joining-spacex)（2026-08-14）
  - [Cursor Projects changelog](https://cursor.com/changelog/projects)（2026-09-10）
  - [Introducing Grok Bot](https://x.ai/news/introducing-grok-bot)（2026-08-11）、[文件](https://docs.x.ai/grok-bot/overview)、[使用案例](https://docs.x.ai/grok-bot/use-cases)
  - [Cursor Compile London 議程](https://cursor.com/compile/london)
  - [karpathy/autoresearch](https://github.com/karpathy/autoresearch)、[Bend](https://github.com/bendlang/bend)、[mattpocock/skills](https://github.com/mattpocock/skills)、[poteto/noodle](https://github.com/poteto/noodle)
- 未能直接核對：[Poteto 的 X 貼文](https://x.com/poteto/status/2102050467505430555)（X 頁面需登入；標題與日期來自搜尋結果）。

## 重要限制

- 「約 2,000 至 2,500 個 PR」是本人自報，沒有外部稽核；貼文標題寫 2,500，議程標題寫 2,000，訪談中 Poteto 自己也說「2000 or however many」。
- 文中時間連結取自字幕檔，與影片播放位置可能略有出入。
- 影片畫面：全片只有兩人視訊對談，沒有螢幕分享（單方查證，未全面核對）。
- 圖片為 AI 生成的示意圖，內容只用文章已有的資訊。
- 本頁非 Poteto、Matt Pocock、Cursor 或 SpaceXAI 官方內容。
