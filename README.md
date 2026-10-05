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

## 已知問題

`npm audit` 仍有漏洞：`hcaptcha-solver` 依賴已停止維護的 `request`(critical,沒有修正版);puppeteer 要從 19 升到 24 才能清掉其餘的 high,但需要實際登入 Discord 才能驗證，所以沒有升。
