> Read this in other languages: [English](README.md) | [繁體中文](README-zh-Hant.md)

<div align="center">

# 🤖 Welcome to C.K. Robotics!

#### _Building robots, learning together_ ⚡

[![Documentation](https://img.shields.io/badge/Documentation-8A2BE2?style=for-the-badge&logo=readthedocs&logoColor=white)](https://docs.ckrobotics.org/)
[![Projects](https://img.shields.io/badge/Projects-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/orgs/C-K-Robotics/projects)
![LINE Community](https://img.shields.io/badge/Community-06C755?style=for-the-badge&logo=line&logoColor=white)

</div>

----

## 🧠 Generative AI Usage Policy & Recommendations

**AI can assist with robot programming, but the member submitting the code remains responsible for understanding, reviewing, and testing it.**

> [!WARNING]
> **Chinese-developed AI models and services are banned, with one exception: Qwen running strictly on localhost. DeepSeek is prohibited everywhere, both remotely and locally**, including through another provider or harness. T2 harnesses are also banned.

### 1. Models & Providers

A **provider** supplies the model. A **harness** connects it to repository files and commands. **Ollama** and **vLLM** are local inference runtimes, not model providers.

| Provider / execution | Recommended models | Suggested use |
| --- | --- | --- |
| [OpenAI — remote](https://developers.openai.com/api/docs/models) | **GPT-6.2 Sol**, GPT-6.2 Astra, GPT-6 Luna | **Start with Sol** for programming. Use Astra for difficult debugging and design, or Luna for small, well-defined tasks. |
| [Anthropic — remote](https://platform.claude.com/docs/en/models/overview) | **Claude Sonnet 5.5**, Opus 5.5, Fable 5.2, Haiku 5.5 | **Start with Sonnet** for everyday coding. Escalate to Opus for hard problems, then Fable if Opus still cannot resolve them. Haiku for quick, simple tasks. |
| [Google — remote](https://antigravity.google/docs/models?app=antigravity) | **Gemini 4 Neon**, Gemini 4 Hydrogen, Gemini 4 Carbon | **Start with Neon** for everyday coding when your plan includes it. Use Hydrogen for quick tasks or when Neon is unavailable on your student account. Reserve Carbon for the hardest problems. |
| [OpenAI — local](https://developers.openai.com/learn/gpt-oss) | **gpt-oss-20b**; **gpt-oss-120b** | Local experimentation through Ollama or vLLM. Choose according to available hardware. |
| [Google — local](https://gemma.ai/models/gemma-4/) | **Gemma 4** (E2B, E4B, 12B, 26B A4B, 31B) | Run locally with Ollama or vLLM. Choose a size that fits your hardware. |
| Qwen — **localhost only** | **Qwen series**, including [Qwen3.8-27B](https://huggingface.co/Qwen/Qwen3.8-27B) | The sole exception to the ban on Chinese-developed models. Run inference entirely on your own machine through Ollama or vLLM. |

**Claude usage:** Keep routine work on Sonnet and switch back after resolving a difficult problem. [Opus consumes more quota](https://support.claude.com/en/articles/14552983-models-usage-and-limits-in-claude-code), so using it by default can quickly exhaust your Pro allowance. [Fable on Pro requires pay-as-you-go usage credits](https://support.claude.com/en/articles/15424964-claude-fable-models-on-your-plan); it is not included in the plan's usage limits.

Google lists Hydrogen for standard Google AI Pro trials, with access subject to capacity. Check your Antigravity model picker if you're on the one-year student plan. Google is removing Gemini 4 Argon and Gemini 3.8 Flash from Antigravity on November 30, 2026. [Antigravity plans](https://antigravity.google/docs/plans) · [Model availability](https://antigravity.google/docs/models?app=antigravity)

### 2. Harnesses

| Tier | Harness | Team guidance |
| --- | --- | --- |
| **T0 — Recommended** | [Codex](https://developers.openai.com/api/docs/guides/code-generation) | Preferred harness for OpenAI GPT models. |
| **T0 — Recommended** | [Claude Code](https://code.claude.com/docs/en/model-config) | Preferred harness for Anthropic Claude models. |
| **T0 — Recommended** | [Google Antigravity](https://antigravity.google/) | Preferred harness for the listed Gemini models. |
| **T1 — Use at your own risk** | [Pi Coding Agent](https://github.com/earendil-works/pi/tree/main/packages/coding-agent) | Minimalist alternative. You are responsible for configuration, permissions, and routing. |
| **T1 — Use at your own risk** | [OpenCode](https://opencode.ai/docs/models/) | Explicitly select an allowed model and endpoint. Never route requests to banned Chinese AI services. |
| **T2 — Banned** | Chinese-developed harnesses, DeepSeek-specific harnesses, and configurations using banned services | Prohibited for team work. A banned harness remains banned even when paired with an otherwise allowed model. |

**Harness approval does not approve every provider, model, plugin, or fallback it supports.** Check the actual model and endpoint, including any automatic fallback, before sending team work.

### 3. Responsible Use & Approval

- **Keep local inference local:** Qwen must run on the same machine through `localhost` or a loopback address. No hosted Qwen APIs, remote inference servers, tunnels, or cloud fallback.
- **Ask a mentor when unsure:** Unlisted models, unfamiliar model versions, providers, harnesses, or uncertain configurations require mentor approval before use. Approval does not create an exception to the explicit bans above.
- **Protect team information:** A mentor must approve both the remote service and the private project before private code is sent. Never include credentials, secrets, or personal information.
- **Own the result:** Understand every submitted change, verify APIs against official robotics or vendor documentation, and review generated commands before execution. Do not submit code you cannot explain.
- **Test before hardware:** AI-assisted changes require human review and simulation or applicable tests before physical-robot testing or deployment. Changes affecting motion, actuators, limits, or safety also require **mentor approval** before they run on the robot.

----

<div align="center">

## 📚 Documentation

### [**C-K Robotics Documentation Portal**](https://docs.ckrobotics.org/)

_Explore learning resources for mechanical design, electrical systems, and control & programming._

</div>

----

> [!IMPORTANT]
> **Keep internal work within the team.** Don't share private repositories, team data, or internal documents outside C.K. Robotics without approval from a team lead.

----

## 👥 Team Communication

Use our **LINE group** to reach team leads and teammates. If you haven't joined yet, ask a mentor for approval and an invitation. Check LINE for team announcements and meeting updates.
