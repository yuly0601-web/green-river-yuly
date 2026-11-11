# 影映行旅：大學影展與畢業專題全景策展誌 — Vibe Coding 提示詞與架構手冊

本文件記錄本專案「大學三階段策展與創作成果（大二影展專題、大三影展回顧與深化、大四畢業專題）」在開發過程中所運用的 **Vibe Coding 指令、提示詞策略（Prompt Engineering）、架構規劃與多平台部署流程**。

---

## 專案快速交付連結 (Project Deliverables)

| 項目 | 交付名稱 | 正式網址與資源連結 | 備註說明 |
| :--- | :--- | :--- | :--- |
| **(1)** | **Prompt 說明 Markdown 檔 (GitHub)** | [https://github.com/uredo0601/film-festival-capstone/blob/main/VIBE_CODING_PROMPTS.md](https://github.com/uredo0601/film-festival-capstone/blob/main/VIBE_CODING_PROMPTS.md) | 包含完整提示詞演繹、結構決策與架構邏輯 |
| **(2)** | **InfinityFree 個人網址 (首頁 Landing Page)** | [http://curation-capstone.infinityfreeapp.com/](http://curation-capstone.infinityfreeapp.com/) | 靜態站點已替換預設首頁，相容免費用戶端 |
| **(3)** | **Vercel 雲端正式部署網址** | [https://film-festival-capstone.vercel.app/](https://film-festival-capstone.vercel.app/) | 具備邊緣伺服器加速、自動化 CI/CD 與 HTTPS |

---

## 一、Vibe Coding 核心哲學與提示詞架構

Vibe Coding 是透過高意圖（High-Intent）的自然語言提示詞，結合領域設計系統（Design Constitution）與工程約束，實現端到端高品質應用的開發方式。在本專案中，我們將提示詞拆分為六個精準演繹階段：

### 階段 1：學年跨度策展命題與資訊架構 (Curatorial Taxonomy)

```markdown
【提示詞 Prompt 01：綠川綠空影展專題與企劃核心命題】
你是一位資深傳播企劃與電影策展人。請根據《綠川水岸與綠空廊道企畫書》精確架構專題：
1. 大二影展專題：
   - 核心作品：《綠空漫泡，綠川漾沫》廣告短片與影展專題
   - Slogan：「讓煩惱化為泡影，在綠川重拾清醒」
   - 核心價值主張：「為日常心靈療癒型客群打造『無社交壓力、深度放鬆』的日常自然藍綠空間」
   - 8 位組員名單：李舒涵（組長）、張季茹（企劃文案）、張佳騏（企劃文案）、程品瑜（導演）、梁睿桐（美術）、張庭瑄（攝影）、尤瑞德（剪輯）、與那嶺藍（劇務/演出）。
   - 包含 131 份真實問卷分析與 4P/MCDA 評比（綠川綠空 vs 秋紅谷 vs 勤美草悟道）。
2. 大三深化回顧：
   - 針對大二過路客「路過不入」慣性、社群聲量較低、泡泡空間感測機制不足進行批判反思，建立數位人文開放典藏。
3. 大四畢業專題：
   - 《共感迴圈：跨時空聲影互動敘事空間》(Symbiotic Loop)，將綠川光影水波與泡泡意象轉化為沉浸式 WebGL 粒子著色器互動裝置。
```

---

### 階段 2：搜尋引擎最佳化 (SEO) 與語意化結構 Prompt

```markdown
【提示詞 Prompt 02：SEO 與 Schema.org 結構化資料】
請為網頁實作最完整的生產級 SEO 規劃：
1. 標題與描述：嚴格符合品牌專屬性，長度維持在 30-60 字標題及 120-160 字描述。
2. 社群卡片：完整配置 OpenGraph (og:title, og:description, og:image, og:site_name) 與 Twitter Card (summary_large_image)。
3. Schema.org (JSON-LD)：在 head 中注入 ExhibitionEvent 與 CreativeWork 結構化標籤，標註展覽日期、場地、創作者職銜與展覽主軸。
4. 語意化標籤：嚴格使用 <header>, <nav>, <aside>, <main>, <article>, <section>, <footer>，確保搜尋引擎爬蟲能精確索引各章節。
```

---

### 階段 3：Grid System 格線系統與 RWD 響應式佈局 Prompt

```markdown
【提示詞 Prompt 03：Grid System 與手持設備 RWD】
請規劃具備數學嚴謹度的響應式佈局系統：
1. 12-Column Grid System：在桌面端 (1440px) 建立可擴展的 12 欄格線系統，支援 5:7 策展分析分欄、3 欄年級專題三折卡、4 欄數據條。
2. Bento Grid 策展展示：採用現代 Bento Box 佈局，非對稱呈現高解析主視覺、策展手稿與放映片單。
3. 手持裝置 RWD：
   - 觸控區域規範：所有可點擊按鈕、連結皆 >= 44px 觸控高度。
   - 抽屜側邊欄：手機端 (<768px) 提供滑順的 Drawer 側邊欄抽屜，支援單手操作。
   - 零溢出保證：使用 max-w-full 與響應式比例，禁止任何橫向捲動條產生。
   - 頂部導覽列規範：高度不超過手機視窗的 15%，維持良好內容閱讀體驗。
```

---

### 階段 4：CSS 檔案切割與模組化 (Modular CSS Architecture) Prompt

```markdown
【提示詞 Prompt 04：CSS 檔案匣結構切割】
請勿將所有 CSS 樣式混雜在單一檔案中，嚴格依照功能職責進行切割並存放於 CSS 檔案匣 (/src/css/ 與 /public/css/)：
1. base.css：色彩系統變數 (60-30-10 比例)、Cinzel 典雅字體、底片雜訊底紋、滾動條設計。
2. grid.css：12 欄 Grid System、Bento 格線、3 欄三折板、容器尺度。
3. components.css：導覽列玻璃質感、側邊欄毛玻璃面板、35mm 底片齒孔花紋、卡片陰影浮動、程式碼預覽面板。
4. responsive.css：各尺寸螢幕斷點 (@media)、手機觸控規格、抽屜滑出動態、列印適配。
5. 在主樣式表 (index.css) 中以 @import 依序載入各模組。
```

---

### 階段 5：原創視覺生成 (generate_image) 提示詞配方

本專案使用 Google AI Studio `generate_image` 工具生成專屬高解析度圖像，並儲存於 `/public/images/` 檔案匣：

1. **主視覺 (Hero Film Festival Keynote)**
   - *Prompt*: `Cinematic film festival keynote banner, dark moody atmospheric lighting with rich amber and 35mm film grain, modern artistic typography aesthetic, silhouettes of cinema auditorium and vintage projector beams, premier film exhibition aesthetic`
   - *檔案*: `public/images/hero_film_festival.jpg` (Aspect Ratio 16:9)

2. **大二影展海報 (Sophomore Exhibition Poster)**
   - *Prompt*: `Artistic film festival vertical poster for an indie youth cinema festival titled Glimmering Gaze, moody 35mm film photography of twilight urban reflection, minimalist editorial design, high-contrast typography, Cannes indie film aesthetic`
   - *檔案*: `public/images/sophomore_exhibition.jpg` (Aspect Ratio 3:4)

3. **大三田野與文獻深化 (Junior Retrospective Archive)**
   - *Prompt*: `Editorial documentary desk with film strips, 35mm negative contact sheets, curatorial notebooks, magnifying loupe and director storyboard sketches, warm natural studio lighting, tactile paper texture`
   - *檔案*: `public/images/junior_retrospective.jpg` (Aspect Ratio 4:3)

4. **大四沉浸式互動畢業專題 (Senior Graduation Capstone)**
   - *Prompt*: `Immersive new media graduation exhibition installation, interactive digital projection mapping on curved translucent screens, futuristic ambient lighting, viewers interacting with visual soundscapes in contemporary art museum space`
   - *檔案*: `public/images/senior_capstone.jpg` (Aspect Ratio 16:9)

---

### 階段 6：雙平台部署指令與交付驗證

#### 1. InfinityFree 免費主機部署指南
- **登入控制台**：登入 [https://www.infinityfree.com/](https://www.infinityfree.com/)，進入帳戶的 Control Panel。
- **開啟 Online File Manager**：進入 `htdocs/` 根目錄。
- **替換預設首頁**：
  - 刪除或重命名預設的 `default2.html` 或 `index2.html`。
  - 將本專案打包後的靜態檔案（`index.html`、`css/` 資料夾、`images/` 資料夾）上傳至 `htdocs/` 下。
- **驗證成果**：瀏覽個人的 InfinityFree 網址 `http://curation-capstone.infinityfreeapp.com/`，確認首頁已成功載入完整影展專題與側邊欄。

#### 2. Vercel 雲端部署指南
- **連接 GitHub 儲存庫**：在 [Vercel 儀表板](https://vercel.com/) 點擊 **Add New Project**，匯入 `uredo0601/film-festival-capstone`。
- **構建設定 (Build Settings)**：
  - Framework Preset: `Vite`
  - Build Command: `npm run build`
  - Output Directory: `dist`
- **點擊 Deploy**：約 30 秒內自動部署完成，產出正式網址 `https://film-festival-capstone.vercel.app/`。

---

## 二、專案技術堆疊 (Tech Stack)

- **前端框架**：React 19 + TypeScript (Strict Mode)
- **構建工具**：Vite 8.3 + tsx
- **樣式引擎**：Tailwind CSS v4 + 4 模組切割 CSS 架構 (`base`, `grid`, `components`, `responsive`)
- **圖示庫**：Lucide React
- **動畫庫**：Motion (Framer Motion 最新版)
- **部署環境**：Vercel (Edge CDN) + InfinityFree (Apache / PHP Static htdocs)

---

*版權聲明 © 2026 影映行旅 策展團隊。以 MIT License 開源發布於 GitHub。*
