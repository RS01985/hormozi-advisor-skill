# AI 顧問：Hormozi（非官方）

把 Alex Hormozi 官方 YouTube 頻道 518 部公開影片（約 218 小時）整理成一位講得出出處的 AI 商業顧問，專看增長經濟、Offer、瓶頸（constraint）和單位經濟（unit economics）。

> ⚠️ 本作品不是 Alex Hormozi 本人，也不是他或 Acquisition.com 的官方產品，與他沒有任何關連。它是作者根據他在 YouTube 公開分享的方法論整理的決策工具；518 份逐字稿與 518 份逐片筆記只供作者自用，不在本 repo 公開。

## 它會做甚麼

問它一個生意決定，它先讀本 repo 的知識庫，再交四段：

1. **本質**：問題卡在增長鏈（市場 → Offer → Leads → Sales → Delivery → Retention → Cash）哪一環
2. **底層邏輯**：用總綱的框架真的跑一次，每個論點標出處
3. **會怎麼做**：2–3 個有負責人、數字、期限的動作
4. **盲點**：哪些位要本地資料、法律／財務專業意見或其他角度

它也寫明「不管甚麼」：你所在地區的法規與稅務、投資建議、品牌文案的最後手藝一律不碰；影片裡的收入數字只當講者自述。

## 安裝

```bash
npx skills add RS01985/hormozi-advisor-skill
```

也可以手動：把整個資料夾放進你所用 Agent 的 skills 目錄。

用法：「問 Hormozi：……」或「用 Hormozi 角度看看……」。

## 內容

| 檔案 | 內容 |
|:--|:--|
| `SKILL.md` | 顧問設定：角度、四段輸出、誠實線、紀律 |
| `references/advisor-card.md` | 素材範圍、三條心法、管與不管、12 條反模式、矛盾與張力、批評者角度、三關篩選 |
| `references/playbook.md` | 518 部跨影片知識總綱（主正本）；「代表影片」直接連到 YouTube |
| `docs/tests.md` | 6 條回歸測試題與結果（Skill 作答時不讀） |

知識庫以粵語口吻的繁體中文寫成（總綱為書面語），歡迎 fork 改成你習慣的用語。

## 測試結果

同一組題目，模型一律用 Claude Sonnet：

| 版本 | 答過題要點 | 作假出處 | 作數字 | 新情境標「推測」 |
|:--|:--|:--|:--|:--|
| 只靠模型印象（2026-09-16） | 6/9 | 3 句 | 1 題 | 0/1 |
| 作者私人完整版（可讀逐片筆記與逐字稿，2026-09-16） | 9/9 | 0 | 0 | 1/1 |
| 本公開版（2026-09-28） | 7/9（另 1 點半中） | 0 | 0 | 1/1 |

公開版沒有收錄逐片筆記：Q1 的「減價 25%，銷量要多過 33% 才追得回 revenue」只寫在逐片筆記裡，所以答不到。逐題細節見 [docs/tests.md](docs/tests.md)。

## 授權

- 作者撰寫的整理、顧問設定與測試題以 [CC BY 4.0](LICENSE) 授權：可以自由 fork、修改、翻譯（例如轉成台灣用語）、再分享；條件是註明原作者、附上本 repo 連結與 CC BY 4.0 授權連結，並標明你改過甚麼。
- Alex Hormozi 的原創內容、名稱與商標不屬作者，不在上述授權範圍內，詳見 [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md)。
- 建議署名：`AI 顧問：Hormozi（非官方）by RS0715 · Whale Digital Consulting（whaledigitalconsulting.com.au）· CC BY 4.0`

## 作者

RS0715，在海外生活的香港人，正建立服務中小企的 AI 顧問一人公司。[Whale Digital Consulting](https://whaledigitalconsulting.com.au/)。
