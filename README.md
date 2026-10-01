# AI 顧問：Hormozi（非官方）

把 Alex Hormozi 官方 YouTube 頻道 518 部公開影片（約 218 小時）整理成一位說得出出處的 AI 商業顧問，專看增長經濟、Offer、瓶頸（constraint）和單位經濟（unit economics）。

> ⚠️ 本作品不是 Alex Hormozi 本人，也不是他或 Acquisition.com 的官方產品，與他沒有任何關係。它是作者根據他在 YouTube 公開分享的方法論整理的決策工具；510 份字幕逐字稿（另有 8 部官方無字幕）與 518 份逐片筆記只供作者自用，不在本 repo 公開。

## 它會做什麼

問它一個生意決定，它先讀本 repo 的知識庫，再交四段：

1. **本質**：問題卡在增長鏈（市場 → Offer → Leads → Sales → Delivery → Retention → Cash）哪一環
2. **底層邏輯**：用總綱的框架真的跑一次，每個論點標出處
3. **會怎麼做**：2–3 個有負責人、數字、期限的動作
4. **盲點**：哪些地方需要本地資料、法律／財務專業意見，或要換其他角度看

它也寫明「不管什麼」：你所在地區的法規與稅務、投資建議、品牌文案的最後手藝一律不碰；影片裡的收入數字只當講者自述。

## 一般 AI 和掛上這套知識庫，差在哪

同一個模型（Claude Sonnet）、同一題：一邊只憑模型自己對 Hormozi 的印象作答，一邊先讀本 repo 的知識庫再答。

**問：「一個城市的中型餐廳願意花多少錢買 AI 訂位 agent？市場多大？要怎麼定價？」**（原題見 [docs/tests.md](docs/tests.md) Q4）

- 只靠模型印象：直接給出 setup 費、月費和當地櫃檯時薪的具體金額，而且當成事實講。這些數字在 518 部影片裡一個都沒有。
- 掛上知識庫：明講語料沒有本地價錢和市場規模，不給數字，改教你用 value equation、LTGP／CAC 自己算。

**問：「AI 培訓月費會員的流失率上升，團隊想降價 25%，該不該這樣做？」**

- 只靠模型印象：方向沒錯（先不要降價），但說「churn 是 offer 問題，不是價格問題」是 Hormozi 講的。作者用 510 份逐字稿去查，找不到這句話。
- 掛上知識庫（2026-09-28 公開版，Claude Sonnet 5 實際回答節錄）：先指出問題是「還沒診斷流失原因，就想只靠降價解決」，引用 `advisor-card.md §反模式 A1、A2` 和 `playbook.md §三.3`。第一個動作是本週內抽最近流失的 20–30 位會員做訪談，按價格太貴／沒看到結果／沒時間用／服務體驗差／一開始就不是目標客群分類，分類完成前不改價格。

## 安裝

```bash
npx skills add RS01985/hormozi-advisor-skill
```

也可以手動：把整個資料夾放進你所用 Agent 的 skills 目錄。

用法：「問 Hormozi：……」或「用 Hormozi 角度看看……」。

## 台灣用語版

「超級 AI 個體」課程的雷蒙三十把本 repo 改編成台灣用語版，收進課程的 [AI 專家圖鑑](https://ai.lifehacker.tw/ai-experts/#expert-hormozi)：[lifehacker-tw/hormozi-advisor-skill-zh-tw](https://github.com/lifehacker-tw/hormozi-advisor-skill-zh-tw)。習慣台灣用語的讀者，可以直接裝那一版。

## 內容

| 檔案 | 內容 |
|:--|:--|
| `SKILL.md` | 顧問設定：角度、四段輸出、誠實線、紀律 |
| `references/advisor-card.md` | 素材範圍、三條心法、管與不管、12 條反模式、矛盾與張力、批評者角度、三關篩選 |
| `references/playbook.md` | 518 部跨影片知識總綱（主正本）；「代表影片」直接連到 YouTube |
| `docs/tests.md` | 6 條回歸測試題與結果（Skill 作答時不讀） |

知識庫以粵語口吻的繁體中文寫成（總綱為書面語）。習慣台灣用語的話，可以直接用下面的台灣用語版。

## 測試結果

同一組題目，模型用 Claude Sonnet（2026-09-28 公開版為 Claude Sonnet 5；2026-09-16 兩行當日未記錄確切版本）：

| 版本 | 答過題要點 | 作假出處 | 作數字 | 新情境標「推測」 |
|:--|:--|:--|:--|:--|
| 只靠模型印象（2026-09-16） | 6/9 | 3 句 | 1 題 | 0/1 |
| 作者私人完整版（可讀逐片筆記與逐字稿，2026-09-16） | 9/9 | 0 | 0 | 1/1 |
| 本公開版（2026-09-28） | 7/9（另 1 點半中） | 0 | 0 | 1/1 |

公開版沒有收錄逐片筆記：Q1 的「降價 25%，銷量要增加 33% 以上才能把營收追回來」只明寫在逐片筆記，公開總綱沒有；這次答案也沒有自行算出來（其實可由題目直接算：1 ÷ 0.75 − 1 ≈ 33⅓%）。逐題細節見 [docs/tests.md](docs/tests.md)。

## 授權

- 作者撰寫的整理、顧問設定與測試題以 [CC BY 4.0](LICENSE) 授權：可以自由 fork、修改、翻譯（例如轉成台灣用語）、再分享；條件是註明原作者、附上本 repo 連結與 CC BY 4.0 授權連結，並標明你改過什麼。
- Alex Hormozi 的原創內容、名稱與商標不屬作者，不在上述授權範圍內，詳見 [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)。
- 建議署名：`AI 顧問：Hormozi（非官方）by RS0715 · Whale Digital Consulting（whaledigitalconsulting.com.au）· CC BY 4.0`

## 作者

RS0715，在海外生活的香港人，正在建立服務中小企業的 AI 顧問一人公司。[Whale Digital Consulting](https://whaledigitalconsulting.com.au/)。
