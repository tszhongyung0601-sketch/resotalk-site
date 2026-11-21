# 共鳴翻譯 ResoTalk 官網首頁

LINE 群組翻譯機器人「共鳴翻譯 ResoTalk」的產品首頁。單一 `index.html`，沒有建置步驟，用任何靜態主機都能放。

正式站：<https://line-translate-bot.jay12c.workers.dev/>

新版預覽（GitHub Pages）：<https://tszhongyung0601-sketch.github.io/resotalk-site/>

## 檔案

```
index.html        整個首頁（HTML、CSS、JS 都在裡面）
assets/           主圖像照片放這裡
  hero-desktop.jpg  橫式 3:2，電腦與平板用
  hero-mobile.jpg   直式 2:3，手機用（沒有的話自動改用橫式）
主圖提示詞.md     主圖像的 ChatGPT 生圖提示詞
```

兩張主圖都是用 ChatGPT 生成的 AI 圖像，不是真實人物。照片檔不存在時，主圖區會顯示深綠色漸層，版面不會壞。

## 本機預覽

```
python -m http.server 8898 --directory .
```

然後開 <http://127.0.0.1:8898/>。

## 頁面區塊

主圖像 → 四個重點 → 翻譯示範（可切換越南文／印尼文／泰文／菲律賓文）→ 特色 → 12 語言國旗牆 → 使用方式與 QR Code → 價格與付款 → 取消與退款政策 → 常見問題 → 公司與聯絡。

錨點沿用舊版：`#intro`、`#features`、`#how`、`#pricing`、`#policy`、`#company`，另外新增 `#demo`、`#languages`、`#faq`。

## 放回 Cloudflare Worker 時要注意

- `index.html` 裡的 JS 與 CSS 沒有使用反引號和 `${}`，可以整份貼進 Worker 的樣板字串。
- 使用說明、服務條款、隱私權政策的連結寫的是正式站完整網址，換網域時要一起改。
- 主圖照片要有地方放：用 Workers 靜態資產，或把 `assets/hero-*.jpg` 的路徑改成圖片的完整網址。
- `<head>` 裡的 `og:image`（分享連結時的預覽圖）目前指向 GitHub Pages 上的主圖，換網域時改成新的完整網址。

## 外部資源

- 字型：Google Fonts（Noto Sans TC、Noto Serif TC）
- 國旗：[flag-icons](https://github.com/lipis/flag-icons) 7.2.3，經 jsDelivr 載入
- QR Code：LINE 官方帳號的官方 QR 圖

## 修改價格或政策

價格、額度、退款政策、公司資訊的文字與舊版完全一致。要改時，請同時改「價格與付款」「取消與退款政策」「常見問題」三個區塊，避免前後不一致。

© 睿索科技有限公司
