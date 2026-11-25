> Read this in other languages: [English](README.md) | [繁體中文](README-zh-Hant.md)

<div align="center">

# 🤖 歡迎加入 C.K. Robotics！

#### _一起打造機器人，一起學習_ ⚡

[![documentation](https://img.shields.io/badge/Documentation-8A2BE2?style=for-the-badge&logo=readthedocs&logoColor=white)](https://docs.ckrobotics.org/)
[![專案看板](https://img.shields.io/badge/Projects-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/orgs/C-K-Robotics/projects)
![LINE 群組](https://img.shields.io/badge/Community-06C755?style=for-the-badge&logo=line&logoColor=white)

</div>

----

## 🧠 生成式 AI 使用政策與建議

**AI 可以協助機器人程式開發，但上傳程式碼的成員仍須負責理解、審查及測試程式碼。**

> [!WARNING]
> **禁止使用中國開發的 AI 模型及服務，唯一例外是嚴格限定在 localhost 執行的 Qwen。無論遠端或本機，一律禁止使用 DeepSeek**，也不得透過其他供應商或代理工具間接使用。T2 級代理工具同樣禁止使用。

### 1. 模型與供應商

**供應商** **(Provider)** 提供模型；**程式開發代理工具** **(Harness)** 讓模型能夠存取 repository 檔案並執行指令。**Ollama** 與 **vLLM** 是本機推論執行環境，並非模型供應商。

| 供應商／執行方式 | 建議模型 | 建議用途 |
| --- | --- | --- |
| [OpenAI — 遠端](https://developers.openai.com/api/docs/models) | **GPT-6.2 Sol**、GPT-6.2 Astra、GPT-6 Luna | 程式開發**優先使用 Sol**。困難的除錯與設計工作可使用 Astra；範圍小且需求明確的任務可使用 Luna。 |
| [Anthropic — 遠端](https://platform.claude.com/docs/en/models/overview) | **Claude Sonnet 5.5**、Opus 5.5、Fable 5.2、Haiku 5.5 | 日常寫程式**優先使用 Sonnet**。遇到難解問題再使用 Opus；Opus 仍無法解決時，再使用 Fable。Haiku 適合快速、簡單的任務。 |
| [Google — 遠端](https://antigravity.google/docs/models?app=antigravity) | **Gemini 4 Neon**、Gemini 4 Hydrogen、Gemini 4 Carbon | 方案若支援，日常寫程式**優先使用 Neon**。簡單任務或學生帳號無法使用 Neon 時，可用 Hydrogen。最難的問題再用 Carbon。 |
| [OpenAI — 本機](https://developers.openai.com/learn/gpt-oss) | **gpt-oss-20b**；**gpt-oss-120b** | 透過 Ollama 或 vLLM 進行本機實驗，依可用硬體選擇模型。 |
| [Google — 本機](https://gemma.ai/models/gemma-4/) | **Gemma 4**（E2B、E4B、12B、26B A4B、31B） | 透過 Ollama 或 vLLM 在本機執行，依硬體選擇合適的模型大小。 |
| Qwen — **僅限 localhost** | **Qwen 系列**，包含 [Qwen3.8-27B](https://huggingface.co/Qwen/Qwen3.8-27B) | 這是禁止使用中國開發模型的唯一例外。必須透過 Ollama 或 vLLM，完全在自己的電腦上執行推論。 |

**Claude 額度使用建議：** 日常工作使用 Sonnet，難題解決後也請切回 Sonnet。[Opus 消耗的額度較多](https://support.claude.com/en/articles/14552983-models-usage-and-limits-in-claude-code)，預設一直使用 Opus 容易快速耗盡 Pro 額度。[Pro 方案使用 Fable 須另以 usage credits 按用量付費](https://support.claude.com/en/articles/15424964-claude-fable-models-on-your-plan)，不包含在方案原有的使用額度內。

Google 將 Hydrogen 列為標準 Google AI Pro 試用方案可使用的模型，實際使用受服務容量影響。使用一年期學生方案的成員，請在 Antigravity 的模型選單確認。Google 將於 2026 年 11 月 30 日從 Antigravity 移除 Gemini 4 Argon 與 Gemini 3.8 Flash。[Antigravity 方案](https://antigravity.google/docs/plans) · [模型適用方案](https://antigravity.google/docs/models?app=antigravity)

### 2. 程式開發代理工具（Harness）

| 等級 | 工具 | 團隊使用指引 |
| --- | --- | --- |
| **T0 — 建議使用** | [Codex](https://developers.openai.com/api/docs/guides/code-generation) | 使用 OpenAI GPT 模型時的首選工具。 |
| **T0 — 建議使用** | [Claude Code](https://code.claude.com/docs/en/model-config) | 使用 Anthropic Claude 模型時的首選工具。 |
| **T0 — 建議使用** | [Google Antigravity](https://antigravity.google/) | 使用上述 Gemini 模型時的首選工具。 |
| **T1 — 風險自負** | [Pi Coding Agent](https://github.com/earendil-works/pi/tree/main/packages/coding-agent) | 極簡風格的替代工具。使用者須自行負責設定、權限與請求路由。 |
| **T1 — 風險自負** | [OpenCode](https://opencode.ai/docs/models/) | 明確選擇允許的模型與服務端點。不得將請求轉送至遭禁用的中國 AI 服務。 |
| **T2 — 禁止使用** | 中國開發的代理工具、DeepSeek 專用代理工具，以及使用禁用服務的設定 | 不得用於團隊工作。即使搭配原本允許的模型，遭禁用的代理工具仍然禁止使用。 |

**工具獲准使用，不代表它支援的所有供應商、模型、外掛或備援服務都獲准使用。** 傳送團隊工作內容前，請確認實際使用的模型與服務端點，包含任何自動切換的備援服務。

### 3. 使用責任與核准

- **本機推論必須留在本機：** Qwen 必須在同一台電腦上，透過 `localhost` 或回送位址執行。不得使用託管的 Qwen API、遠端推論伺服器、通道轉送或雲端備援。
- **有疑問時請詢問 mentor：** 未列出的模型、不熟悉的模型版本、供應商、代理工具或不確定是否合規的設定，皆須先取得 mentor 核准再使用。核准不構成上述明確禁令的例外。
- **保護團隊資訊：** 將非公開程式碼傳送至遠端服務前，遠端服務與該非公開專案都必須先經 mentor 核准。不得提供憑證、機密資訊或個人資料。
- **對成果負責：** 理解每一項提交的變更，依機器人相關官方或廠商的 documentation 確認 API，並在執行前審查 AI 產生的指令。不要提交自己無法解釋的程式碼。
- **先測試，再上實機：** AI 協助產生的變更，必須先經人工審查，並完成模擬或適用的測試，才能進行機器人實機測試或部署。影響運動、致動器、限制條件或安全的變更，在機器人上執行前，還必須取得 **mentor 核准**。

----

<div align="center">

## 📚 documentation

### [**C-K Robotics documentation 入口**](https://docs.ckrobotics.org/)

_探索機械設計、電機系統、控制與程式設計的學習資源。_

</div>

----

> [!IMPORTANT]
> **內部工作內容請留在團隊內。** 未經團隊負責人核准，不得將非公開 repository、團隊資料或內部文件分享給 C.K. Robotics 以外的人。

----

## 👥 團隊溝通

請透過我們的 **LINE 群組**聯絡團隊負責人與隊友。如果尚未加入，請向 mentor 申請核准與邀請。團隊公告與會議資訊會透過 LINE 發布，請留意群組訊息。
