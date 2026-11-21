# BoboDiscordBot

Discord 機器人與寶可夢自動抓寶腳本(Node.js + discord.js + puppeteer,另有 Python 版本),2022–2023 年的學習研究作品。

## 狀態

已停止維護。用腳本自動操作個人 Discord 帳號(self-bot)違反 [Discord 服務條款](https://discord.com/terms),帳號可能被停權；這裡只保留程式作為紀錄，不建議實際使用。

## 內容

| 路徑 | 內容 |
|---|---|
| `app.js`、`deploy.js` | discord.js 機器人與指令註冊 |
| `auto_catch_javascript_version/` | puppeteer 自動抓寶、孵蛋、打字等腳本;`my-extension/` 是處理 captcha 的瀏覽器擴充;`Test/` 是實驗腳本 |
| `auto_catch_python_version/` | Python 版本 |
| `data/` | 寶可夢資料集與想抓的清單 |

## 執行

```bash
npm install
npm start   # node ./auto_catch_javascript_version/auto_type.js
```

帳號、頻道等設定在各腳本開頭；`Test/` 裡的帳密欄位只是佔位文字。

## 從 puppeteer 19 升上來的注意事項

puppeteer 與 puppeteer-chromium-resolver 已升到 25,宣告需要 Node 22.12 以上；`npm run build` 仍用 `pkg` 打包成 node18 的 exe,沒有測過，很可能跑不起來。以前跑過舊版的電腦，家目錄下會留著 `.pcr-stats.json`,裡面記的是舊版下載的 Chromium(例如 108),新版 puppeteer 連不上它，啟動時會等 30 秒後 timeout。第一次跑新版前先刪掉這個檔(Windows 是 `%USERPROFILE%\.pcr-stats.json`),讓 puppeteer-chromium-resolver 重新下載 Chromium;舊的 `.chromium-browser-snapshots/` 可以一起刪。
