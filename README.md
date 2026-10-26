<a id="top"></a>

<p align="center">
  <img src="assets/banner.svg" alt="Awesome AI Red Team — offensive AI security for practicing red teamers" width="100%">
</p>

<h1 align="center">🔴 Awesome AI Red Team</h1>

<p align="center">The operator's map for offensive AI security. Scanners, jailbreaks, agent and MCP attacks, RAG poisoning, supply chain, and labs you can actually run.</p>

<p align="center">
  <a href="https://awesome.re"><img src="https://awesome.re/badge.svg" alt="Awesome"></a>
  <a href="#contents"><img src="https://img.shields.io/badge/resources-364-b91c1c?style=flat-square" alt="364 resources"></a>
  <a href="#contents"><img src="https://img.shields.io/badge/categories-32-8250df?style=flat-square" alt="32 categories"></a>
  <a href="https://github.com/BerSecHub/awesome-ai-red-team/stargazers"><img src="https://img.shields.io/github/stars/BerSecHub/awesome-ai-red-team?style=flat-square&logo=github" alt="Stars"></a>
  <a href="LICENSE"><img src="https://img.shields.io/github/license/BerSecHub/awesome-ai-red-team?style=flat-square" alt="License"></a>
  <a href="https://github.com/BerSecHub/awesome-ai-red-team/commits/main"><img src="https://img.shields.io/github/last-commit/BerSecHub/awesome-ai-red-team?style=flat-square" alt="Last commit"></a>
  <a href="https://github.com/BerSecHub/awesome-ai-red-team/actions/workflows/links.yml"><img src="https://github.com/BerSecHub/awesome-ai-red-team/actions/workflows/links.yml/badge.svg" alt="Link check"></a>
</p>

**364 hand-picked resources across 32 categories.** Curated by [Rafael Gacek](https://bersec.me) — offensive-AI / red-team operator. Every link earns its place: best-in-class, current, no SEO filler. Defense shows up only as **bypass targets**.

⭐ marks the entry to open first in that category.

> ⚠️ **Authorized use only.** Everything here is for red-team engagements, security research, and CTFs you have permission to run.

### Why this list?

Most "AI security" lists are academic paper dumps or vendor brochures. This one is built by an operator, for operators — weighted toward **things you actually run**: scanners, jailbreak frameworks, payload crafters, agentic/MCP exploits, offensive LLMs, and labs. If you attack, break, or defend AI systems, this is the map.

---

## Start here

One afternoon, in this order. Names point at the section that holds the link — each URL lives in exactly one place.

1. **Learn the map.** Frameworks: OWASP Top 10 for LLM Applications, OWASP Top 10 for Agentic Applications (2026), MITRE ATLAS. If the target uses tools, the Agentic Top 10 is the scope doc.
2. **Break one thing by hand.** Labs: Gandalf, then PortSwigger's Web LLM labs or HackMerlin.
3. **Run a scanner.** Tools: garak against a model you control, or promptfoo if the prompt lives in a repo. PyRIT when you need multi-turn (Crescendo, TAP, Skeleton Key).
4. **Read one production chain.** Prompt Injection: EchoLeak (CVE-2025-32711). Then People: Johann Rehberger.

**Leave these open**

- **Recon** — LLMmap and leaked system prompts, both under Tools and Prompt Injection.
- **Payloads** — L1B3RT4S, PayloadsAllTheThings, and Parseltongue.
- **Agents and MCP** — Snyk Agent Scan, Damn Vulnerable MCP Server, AgentDojo.
- **The integration, not the base model** — indirect injection, RAG, memory poisoning, coding-agent context. A refusal on a naked prompt is not a finding.
- **Close the report** — an ATLAS technique, the matching Top 10 id, an AIVSS score, and the bounty program's actual scope.
- **Maps** — Tools by phase, the technique cheat sheet, and the MCP test checklist, below. They name a resource. The URL stays in one category.

<p align="right"><a href="#top">↑ back to top</a></p>

## Run an engagement

Default order on an authorized target. Skip a step only when the rules of engagement put that layer out of scope.

1. **Scope.** Frameworks. Name the system: chat, RAG, agent, coding assistant, or raw model API. Write the rules before you send a payload. Agents get the Agentic Top 10. A raw model API still includes extraction and membership inference.
2. **Recon.** Fingerprint the model (LLMmap, in Tools). Pull public system prompts and known jailbreaks (Prompt Injection). Inventory agents, MCP servers, and skills (Agentic & MCP, Agent Skills).
3. **Model layer.** Jailbreak Frameworks and Tools. Direct injection, one multi-turn orchestrator, and an obfuscation pass against whatever classifier sits in front. Score with StrongREJECT (Benchmarks), not with "it said something."
4. **Integration layer.** This is where the report comes from. Untrusted content the model will read, a privilege the agent holds, and a way out. Work indirect injection, RAG, memory poisoning, MCP and tool poisoning, computer-use, and coding-agent context. EchoLeak is the shape: retrieval, then a markdown exfil sink.
5. **Supply chain and infra.** MLSecOps when you can touch weights or pickles. Cloud, Inference & LLMjacking for keys, dashboards, and gateways — Ray, Ollama, LiteLLM. A stolen cloud key that spends someone else's quota is a finding even when the prompt filter holds.
6. **Report.** Map the chain to MITRE ATLAS and the right Top 10 item. Score it with AIVSS, plus the client's scale if they have one. Read Microsoft's writeup of 100 GenAI red teams before you draft the narrative. Check Bug Bounty scope: several programs pay for agent hijacks and refuse a bare jailbreak.

<p align="right"><a href="#top">↑ back to top</a></p>

<a id="map-tools-by-phase"></a>

## Tools by phase

Default loadout on an authorized target. Skip a row when the rules of engagement put that layer out of scope. Every name has one entry below.

| Phase | Open |
| --- | --- |
| Scope | OWASP Top 10 for LLM Applications, OWASP Top 10 for Agentic Applications, MITRE ATLAS, NIST AI 100-2, AIVSS |
| Recon | LLMmap, CL4R1T4S, Snyk Agent Scan |
| Model | garak, PyRIT, FuzzyAI, Inspect |
| Integration | AgentDojo, PoisonedRAG, Damn Vulnerable MCP Server, RedTeamCUA |
| Supply chain and infra | Fickling, ModelScan, picklescan, Probllama, ShadowRay |
| Report | The matching ATLAS technique and Top 10 id, an AIVSS score, Microsoft's writeup of 100 GenAI red teams |

<p align="right"><a href="#top">↑ back to top</a></p>

<a id="map-technique-cheat-sheet"></a>

## Technique cheat sheet

One place to remember which resource carries the technique. The link goes to the section. The URL of the resource itself lives only there.

| Technique | Open first | Section |
| --- | --- | --- |
| Direct jailbreak | Crescendo, PAIR, Many-shot | [Jailbreak methods](#-jailbreak-frameworks--methods) |
| Indirect injection | EchoLeak, Greshake | [Prompt injection](#-prompt-injection--jailbreaks) |
| Obfuscation and smuggling | Parseltongue, TokenBreak | [Obfuscation](#-payload-obfuscation--token-smuggling) |
| Tool poisoning | Invariant's disclosure, MCPTox, Damn Vulnerable MCP | [Agentic and MCP](#-agentic--mcp-security) |
| MCP rug pull and client RCE | MCPoison, CurXecute, mcp-remote, MCP Inspector | [Coding assistants](#️-coding-assistant--agent-attacks) · [Agentic and MCP](#-agentic--mcp-security) |
| Agent-to-agent | A2ABreak | [Agentic and MCP](#-agentic--mcp-security) |
| Computer-use and browser agents | ZombAIs, pop-up attack, RedTeamCUA | [Computer-use](#computer-use-browser-agents) |
| RAG poisoning | PoisonedRAG, AgentPoison, Phantom | [RAG](#-rag--vector-db-security) |
| Memory poisoning | Sleeper Memory Poisoning, eTAMP | [Memory](#-memory-poisoning--persistent-agent-state) |
| Model supply chain | Sleepy Pickle, nullifAI, Safetensors conversion hijack | [Supply chain](#-mlsecops--model-supply-chain) |
| Image and audio jailbreaks | FigStep, AdvWave. Sirens' Whisper is in [Deepfake](#-deepfake--voice-offense) | [Multimodal](#️-multimodal--vision--audio-attacks) |
| LLMjacking and exposed inference | Sysdig's LLMjacking report, Probllama | [Cloud](#️-cloud-inference--llmjacking) |

<p align="right"><a href="#top">↑ back to top</a></p>

<a id="map-mcp-agent-checklist"></a>

## MCP and agent test checklist

Walk this on any authorized agent that can call tools. A refusal on a naked prompt is not a finding.

- [ ] Inventory every MCP server, skill, and connector the agent can call. Snyk Agent Scan or Cisco MCP Scanner.
- [ ] Read the whole tool definition: description, input schema, output schema, annotations. A hidden instruction in any of those is tool poisoning. OWASP MCP Cheat Sheet and MCPTox.
- [ ] Re-read the definition after approval. A changed command or description is a rug pull. MCPoison is that bug on Cursor.
- [ ] Treat tool results, resources, and prompts as untrusted content.
- [ ] Before you connect a second server, ask what it can make the first server do. The WhatsApp MCP writeup is tool shadowing.
- [ ] Name the flow before you call it a finding: untrusted input, a private-data tool, and a sink. The GitHub MCP post is the shape. The lethal trifecta is the rule.
- [ ] Check whether model output can write `mcp.json` or start a new server. CurXecute is that chain.
- [ ] Version-check mcp-remote (CVE-2025-6514, fixed in 0.1.16) and MCP Inspector (CVE-2025-49596, fixed in 0.14.1).
- [ ] Write down the OAuth scopes. A full mailbox or repo scope is the privilege the injection inherits.
- [ ] If agents delegate to agents, test A2A the way A2ABreak does: unattested Agent Cards, context-id injection, credentials forwarded across hops.
- [ ] Read `SKILL.md`, helper files, `.cursorrules`, and `copilot-instructions.md`. Rules File Backdoor and SkillJect live on this surface.
- [ ] Ask what the agent will still believe next session. A memory write from untrusted content is the persistence step.

<p align="right"><a href="#top">↑ back to top</a></p>

---

## Contents

<p align="center">
  <a href="#start-here">Start here</a>
  ·
  <a href="#run-an-engagement">Run an engagement</a>
  ·
  <a href="#map-tools-by-phase">Tools by phase</a>
  ·
  <a href="#map-technique-cheat-sheet">Technique cheat sheet</a>
  ·
  <a href="#map-mcp-agent-checklist">MCP test checklist</a>
</p>

| Attack the model | Attack the system | Practice and field |
| --- | --- | --- |
| [Frameworks](#-frameworks-standards--taxonomies) | [Agentic and MCP](#-agentic--mcp-security) | [Labs and CTFs](#️-labs-ctfs--challenges) |
| [Tools and scanners](#️-llm-red-team-tools--scanners) | [Computer-use and browser](#computer-use-browser-agents) | [Benchmarks](#-benchmarks--datasets) |
| [Hack with AI](#-ai-augmented-offense-hack-with-ai) | [Memory poisoning](#-memory-poisoning--persistent-agent-state) | [Bug bounty](#-bug-bounty--disclosure) |
| [Offensive models](#-offensive--uncensored-models) | [Coding assistants](#️-coding-assistant--agent-attacks) | [Courses](#-courses--certifications) |
| [Prompt injection](#-prompt-injection--jailbreaks) | [Agent skills](#-agent-skills--tool-supply-chain) | [Books](#-books) |
| [Jailbreak methods](#-jailbreak-frameworks--methods) | [RAG and vector DB](#-rag--vector-db-security) | [People](#-people--blogs-to-follow) |
| [Obfuscation](#-payload-obfuscation--token-smuggling) | [Cloud and LLMjacking](#️-cloud-inference--llmjacking) | [Communities](#️-communities--conferences) |
| [Multimodal and voice](#️-multimodal--vision--audio-attacks) | [AI malware](#-ai-malware--self-propagating) | [Talks](#-talks) |
| [Classic adversarial ML](#-adversarial-ml-classic-model-attacks) | [Deepfake and voice](#-deepfake--voice-offense) | [Newsletters](#-newsletters--podcasts) |
| [Extraction and privacy](#-model-extraction-inversion--membership-inference) | [Data poisoning](#️-data-poisoning--backdoors) | [Other lists](#-awesome-lists--curations) |
| [Model supply chain](#-mlsecops--model-supply-chain) |  | [Vendors](#-vendor--market-landscape) |

<p align="right"><a href="#top">↑ back to top</a></p>

## 🎯 Frameworks, Standards & Taxonomies

The maps you scope, threat-model, and write reports against.

- ⭐ **[OWASP Top 10 for LLM Applications (2025)](https://genai.owasp.org/llm-top-10/)** — Definitive risk taxonomy for LLM apps. Baseline for scoping any engagement.
- ⭐ **[OWASP Top 10 for Agentic Applications (2026)](https://genai.owasp.org/resource/owasp-top-10-for-agentic-applications-for-2026/)** — The scope doc once the target plans and uses tools: goal hijack, tool misuse, identity abuse, supply chain, unexpected code exec, memory poisoning, inter-agent traffic, cascading failure, trust abuse, rogue agents.
- **[OWASP LLM AI Security & Governance Checklist](https://genai.owasp.org/resource/llm-applications-cybersecurity-and-governance-checklist-english/)** — Checklist v1.1 for leaders scoping LLM cybersecurity and governance. Client-facing framing.
- ⭐ **[MITRE ATLAS](https://atlas.mitre.org/)** — Adversary TTP matrix for ML/AI. The ATT&CK of AI.
- **[Zenity GenAI Attacks Matrix (ttps.ai)](https://ttps.ai/)** — Living matrix of real-world GenAI/agent attack techniques; feeds MITRE ATLAS.
- **[NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)** — The governance framework. Compliance language clients already speak.
- **[NIST AI 100-2e2023](https://csrc.nist.gov/pubs/ai/100/2/e2023/final)** — Adversarial-ML taxonomy: evasion, poisoning, privacy, and misuse, in the words a NIST-minded reader expects in the report.
- **[NIST AI 600-1 — Generative AI Profile](https://www.nist.gov/publications/artificial-intelligence-risk-management-framework-generative-artificial-intelligence)** — The GenAI profile on the AI RMF. Cite it when the report has to use the generative-AI control language.
- **[NCSC — Guidelines for secure AI system development](https://www.ncsc.gov.uk/collection/guidelines-secure-ai-system-development)** — Joint NCSC and CISA guidance for providers: secure design, development, deployment, and operation. The baseline when the client builds the system.
- **[Google SAIF](https://saif.google/)** — Secure AI Framework: design/build/deploy principles + risk self-assessment.
- **[Coalition for Secure AI (CoSAI)](https://www.coalitionforsecureai.org/)** — OASIS-backed coalition + workstreams on agentic security, supply chain, defender frameworks.
- **[OWASP ML Security Top 10](https://mltop10.info/)** — Classic (non-LLM) ML risks: poisoning, inversion/extraction, adversarial examples.
- **[OWASP AI Exchange](https://owaspai.org/)** — 300+ page living reference mapping AI threats to controls and standards (ISO/IEC, EU AI Act).
- **[CSA MAESTRO](https://cloudsecurityalliance.org/blog/2025/02/06/agentic-ai-threat-modeling-framework-maestro)** — 7-layer threat-modeling method for agentic systems.
- **[MIT AI Risk Repository](https://airisk.mit.edu/)** — Living catalog of AI risks with causal and domain taxonomies.
- **[OWASP AIVSS — AI Vulnerability Scoring System](https://vineethsai.github.io/aivss/)** — Emerging CVSS-equivalent for scoring AI/agentic vulns. Rate findings consistently in reports.
- **[OWASP GenAI Red Teaming Guide](https://genai.owasp.org/resource/genai-red-teaming-guide/)** — Engagement structure across model, implementation, infrastructure, and runtime. The test-plan skeleton, not a payload list.
- **[Lessons from red teaming 100 GenAI products (Microsoft)](https://www.microsoft.com/en-us/security/blog/2025/01/13/3-takeaways-from-red-teaming-100-generative-ai-products/)** — What Microsoft's AI red team actually found across 100 products, and how they wrote it up. Read it before you file the report.
- **[EU AI Act](https://artificialintelligenceact.eu/)** — The regulation reshaping AI risk/compliance in the EU. Know it for client engagements.
- **[Code of Practice for General-Purpose AI](https://artificialintelligenceact.eu/introduction-to-code-of-practice/)** — Plain-language walkthrough of the GPAI Code of Practice, on the same explainer as the Act entry. Read it when the client asks what the Act expects you to test.

<p align="right"><a href="#top">↑ back to top</a></p>

## 🛠️ LLM Red-Team Tools & Scanners

The frameworks you actually run against a target.

| You have | Run |
| --- | --- |
| A model or API you can probe | **garak**, or **Augustus** for a single Go binary |
| Multi-turn work (Crescendo, TAP, Skeleton Key) | **PyRIT** |
| Prompts in a repo, or a CI gate | **promptfoo**, or **RAMPART** for agent cross-injection |
| An agent graph to map before a payload | **Agentic Radar**, **AI-Infra-Guard** |
| A rerunnable eval with scorers and sandboxes | **Inspect** |
| Black-box fuzzing across providers | **FuzzyAI** |

Names point at the entries below. MCP inventory is **Snyk Agent Scan**, in Agentic & MCP.

- ⭐ **[garak (NVIDIA)](https://github.com/NVIDIA/garak)** — *The* LLM vuln scanner. 120+ probes; broadest automated base-model coverage; now includes agentic probing.
- ⭐ **[PyRIT (Microsoft)](https://github.com/microsoft/PyRIT)** — Multi-turn orchestrators — Crescendo, TAP, Skeleton Key. Actively maintained; this is the harness those three attacks ship in.
- **[Inspect (UK AI Security Institute)](https://github.com/UKGovernmentBEIS/inspect_ai)** — Eval harness: datasets, agents, tools, MCP, sandboxes, and scorers. Use it when the engagement needs a rerunnable eval, not a one-off jailbreak script.
- **[Promptfoo](https://github.com/promptfoo/promptfoo)** — Dev-loop red teaming + evals. Auto-generates attack cases; CI/CD regression testing. Ships a Pliny plugin.
- **[DeepTeam](https://github.com/confident-ai/deepteam)** — 50+ vulnerabilities, 20+ research-backed attacks (single & multi-turn). Pairs with DeepEval.
- **[Giskard](https://github.com/Giskard-AI/giskard-oss)** — Open-source LLM & ML testing: injection, harmful output, hallucination, bias.
- **[Spikee (Reversec)](https://github.com/ReversecLabs/spikee)** — Simple Prompt Injection Kit for Evaluation & Exploitation. Modular.
- **[Broken Hill (Bishop Fox)](https://github.com/BishopFox/BrokenHill)** — Productionized GCG attack tool; transferable jailbreak suffixes on a single RTX 4090. Repo quiet since late 2024.
- **[promptmap (utkusen)](https://github.com/utkusen/promptmap)** — Automated injection scanner. White-box & black-box (HTTP endpoint) modes.
- **[Agentic Security (msoedov)](https://github.com/msoedov/agentic_security)** — Open-source agentic LLM vuln scanner: multi-step jailbreaks, multimodal, fuzzing, RL-based probes.
- **[Prompt Fuzzer (ps-fuzz)](https://github.com/prompt-security/ps-fuzz)** — Harden your system prompt: 16 attacks × 16 providers, plus a playground.
- **[Agentic Radar (SplxAI)](https://github.com/splx-ai/agentic-radar)** — Static scanner for agentic workflows; maps tools/MCP to OWASP risks + adversarial test mode.
- **[FuzzyAI (CyberArk)](https://github.com/cyberark/FuzzyAI)** — Fuzzing framework with 20+ techniques (ASCII smuggling, ManyShot, Crescendo, genetic) across providers.
- **[AI-Infra-Guard (Tencent)](https://github.com/Tencent/AI-Infra-Guard)** — Full-stack AI red-team platform: agent scan, MCP/skills scan, AI-infra vuln scan, web fingerprinting, jailbreak eval. Open source.
- **[Repello ARTEMIS](https://repello.ai/)** — Automated red teaming with 1200+ attack vectors across text/image/audio + agent red teaming (commercial).
- **[Augustus (Praetorian)](https://github.com/praetorian-inc/augustus)** — Go single-binary LLM vuln scanner — 210+ probes / 47 attack categories across 28 providers. Garak-class coverage, way faster.
- **[Redamon](https://github.com/samugit83/redamon)** — Agentic meta-framework: runs garak + PyRIT + Giskard + promptfoo, scores ASR, writes OWASP-LLM/ATLAS-mapped findings.
- **[RAMPART (Microsoft)](https://www.microsoft.com/en-us/security/blog/2026/05/20/introducing-rampart-and-clarity-open-source-tools-to-bring-safety-into-agent-development-workflow/)** — Pytest-native agentic red teaming on PyRIT — cross-prompt-injection tests gated in CI/CD. MIT.
- **[LLMmap — model fingerprinting](https://github.com/pasquini-dario/LLMmap)** — Recon: identify the exact LLM behind an app/endpoint — 42 versions at 95%+ in ~8 queries. Know your target before you swing.
- **[Rigging (Dreadnode)](https://github.com/dreadnode/rigging)** — Lightweight agent + tool-calling harness for orchestrating offensive LLM experiments. Great for custom attack chains.
- **[Plexiglass](https://github.com/w4-advisory/plexiglass)** — Security toolbox for testing & safeguarding LLMs — adversarial prompts, toxicity, jailbreak checks.
- **[WhistleBlower](https://github.com/Repello-AI/whistleblower)** — Infers a target agent's hidden system prompt from its outputs. System-prompt extraction on tap.

<p align="right"><a href="#top">↑ back to top</a></p>

## 🦾 AI-Augmented Offense (hack WITH AI)

The force multiplier. Where offense is heading — and the moat you're building.

- ⭐ **[XBOW](https://xbow.com/)** — Autonomous pentester that reached #1 on HackerOne, with 1,500+ reproducible exploits on production targets.
- ⭐ **[PentestGPT](https://github.com/GreyDGL/PentestGPT)** — LLM-guided pentest framework; multi-model. Web, pwn, crypto, priv-esc, CTF.
- **[CAI — Cybersecurity AI (Alias Robotics)](https://github.com/aliasrobotics/cai)** — Bug-bounty-ready agent framework: agents, tools, handoffs, tracing, HITL. Archived August 2026 — still the reference codebase.
- **[HackingBuddyGPT](https://github.com/ipa-lab/hackingBuddyGPT)** — LLMs that execute shell in a sandbox and decide next move. 83% Linux priv-esc with guidance.
- **[Nebula (BerylliumSec)](https://github.com/berylliumsec/nebula)** — AI pentest assistant in the CLI: recon, notes, vuln analysis with local Llama/Mistral.
- **[Vulnhuntr (Protect AI)](https://github.com/protectai/vulnhuntr)** — Zero-shot vuln discovery: LLM traces full call chains input→sink in Python. Found real 0-days. Repo quiet since early 2025.
- **[Awesome AI Hacking Agents](https://github.com/EvanThomasLuke/Awesome-AI-Hacking-Agents)** — Curated list of autonomous AI hacking agents & frameworks.
- **[Cyber-AutoAgent](https://github.com/westonbrown/Cyber-AutoAgent)** — Autonomous cyber agent (recon→exploit) on open frameworks. Archived November 2025; still useful code to study.
- **[HexStrike AI](https://github.com/0x4m4/hexstrike-ai)** — MCP server wiring LLMs (Claude/GPT/Copilot) to 150+ security tools for autonomous pentest, vuln discovery, bounty automation.
- **[PentAGI](https://github.com/vxcontrol/pentagi)** — Fully autonomous multi-agent pentest system in Docker sandboxes (32k+ stars).
- **[Strix](https://github.com/usestrix/strix)** — Autonomous agent that simulates a human attacker and proves findings with working PoC exploits.
- **[FuseAI](https://getfuseai.com/)** — Multi-agent AI platform for automated pentest & vuln management. Chains agents across recon→exploit→report.
- **[pentest-ai (0xSteph)](https://github.com/0xsteph/pentest-ai)** — AI pentest and bounty tool: the model investigates, and an independent oracle only keeps findings it can replay. CLI, MCP, and CI. Bring-your-own-LLM.
- **[The AI Offensive Security Boom (70 tools)](https://hadrian.io/blog/the-ai-offensive-security-boom-seventy-tools-in-eighteen-months)** — Landscape survey: 70 offensive-AI tools in 18 months.
- **[Agentic Bug Hunter (awarexone)](https://github.com/awarexone/Agentic-Bug-Hunter)** — Terminal bounty hunter: recon through report from the CLI. The Claude Code hunting harness.
- **[pentest-agents (H-mmer)](https://github.com/H-mmer/pentest-agents)** — 50-agent bounty framework across Claude Code / Codex / Gemini / Cursor / Windsurf / Copilot — Burp MCP, FAISS writeup search, per-run cost tracking.
- **[Transilience communitytools](https://github.com/transilienceai/communitytools)** — Open Claude Code skills, agents & slash-commands for AI pentest. Skills-only, no fine-tune — transfers across models.
- **[Burp Suite MCP (PortSwigger)](https://github.com/PortSwigger/mcp-server)** — Official MCP server exposing Burp to an LLM agent (works with Community). Wire your agent straight into the proxy.
- **[Playwright MCP (Microsoft)](https://github.com/microsoft/playwright-mcp)** — The browser-automation MCP agents wire in to drive a real browser — clicks, DOM, network — for agentic web attacks.
- **[Decepticon (BitterSecurity)](https://github.com/BitterSecurity/Decepticon)** — Autonomous red-team agent running full chains — recon → exploit → privesc → lateral → C2 — with Ghidra-MCP / BloodHound / Sliver specialists. 102/104 on the XBOW validation bench.

<p align="right"><a href="#top">↑ back to top</a></p>

## 🧬 Offensive & Uncensored Models

Local, low-refusal firepower. For authorized engagements — run it on your box.

- ⭐ **[WhiteRabbitNeo](https://huggingface.co/WhiteRabbitNeo)** — Offensive-tuned, low-refusal security LLM (8B/70B, Llama-3.1). Built for red/blue infosec workflows. Your local pair-hacker.
- **[Foundation-Sec-8B (Cisco)](https://huggingface.co/fdtn-ai/Foundation-Sec-8B)** — Cisco Foundation AI's cybersecurity base model: Llama-3.1-8B continued-pretrained on threat intel, vulnerability databases, and incident-response text.
- **[huihui_ai — abliterated models (Ollama)](https://ollama.com/huihui_ai)** — Pull-and-run collection of refusal-removed models locally.
- **[Dolphin / uncensored (cognitivecomputations)](https://huggingface.co/cognitivecomputations)** — Long-running uncensored fine-tune line; solid no-refusal base for tooling.
- **[UNST33R](https://unst33r.si/)** — Hosted uncensored and abliterated open-weight LLMs (GLM-5.3, DeepSeek-V4.1-Flash) behind one OpenAI-compatible endpoint, for when you can't run it on your box. Paid, authorized-use only.

<p align="right"><a href="#top">↑ back to top</a></p>

## 🤖 Agentic & MCP Security

Where the 2026 attack surface actually lives: tools, memory, MCP, autonomy.

- **[AgentDojo (ETH SPY Lab)](https://github.com/ethz-spylab/agentdojo)** — Dynamic benchmark/environment for injection attacks & defenses on tool-using agents.
- ⭐ **[Damn Vulnerable MCP Server](https://github.com/harishsg993010/damn-vulnerable-MCP-server)** — Tool poisoning, rug pulls, tool shadowing, indirect injection, excessive permissions.
- **[Damn Vulnerable LLM Agent (Reversec)](https://github.com/ReversecLabs/damn-vulnerable-llm-agent)** — ReAct/LangChain agent for practicing injection on tool-use chains.
- **[Damn Vulnerable AI Agent](https://github.com/opena2a-org/damn-vulnerable-ai-agent)** — Vulnerable agent platform for hands-on testing.
- **[Invariant Labs](https://invariantlabs.ai/)** — Tool-poisoning disclosures, agent guardrails, and MCP security tooling research.
- **[SuperClaw](https://github.com/SuperagenticAI/superclaw)** — Scenario-driven, behavior-first red teaming for autonomous agents. Generates adversarial scenarios, scores vs security contracts. pip install.
- ⭐ **[Snyk Agent Scan (formerly MCP-Scan)](https://github.com/snyk/agent-scan)** — Invariant's MCP scanner, renamed under Snyk. Inventory agents, MCP servers, and skills; flag tool poisoning, rug pulls, toxic flows, and secrets. The MCP audit standard.
- **[MCP Injection Experiments](https://github.com/invariantlabs-ai/mcp-injection-experiments)** — Working PoCs that exfiltrate SSH keys/config from Claude Desktop and Cursor via tool poisoning. Copy-paste attack lab. PoC repo last touched April 2025.
- **[The Lethal Trifecta (Simon Willison)](https://simonwillison.net/series/prompt-injection/)** — Private data + untrusted content + exfiltration = the core agentic exploit class.
- **[Promptware — "Invitation Is All You Need"](https://arxiv.org/abs/2508.12175)** — Practical, in-production attacks on LLM assistants via calendar invites, emails, and shared docs. Injection as a delivery mechanism against real deployed agents.
- **[MUZZLE](https://arxiv.org/abs/2602.09222)** — Adaptive agentic red-teaming: watches an agent's trajectory, finds high-salience injection surfaces, generates context-aware payloads — found 37 new attacks incl. cross-app injection. Attack generation, not fixed payloads.
- **[Cisco MCP Scanner](https://github.com/cisco-ai-defense/mcp-scanner)** — Vendor-grade MCP supply-chain scanner: YARA + LLM-as-judge + pip-audit + VirusTotal, CLI/REST, offline static JSON scan. Vet the tools your agent can call.
- **[MCP tool poisoning (Invariant Labs)](https://invariantlabs.ai/blog/mcp-security-notification-tool-poisoning-attacks)** — The disclosure that named the attack: instructions in the tool description, visible to the model and not the user. Read it, then run the PoCs in MCP Injection Experiments.
- **[GitHub MCP private-repo exfil (Invariant Labs)](https://invariantlabs.ai/blog/mcp-github-vulnerability)** — A public issue injects an agent that can read a private repo, and the leak leaves as a public pull request. The toxic-flow pattern.
- **[WhatsApp MCP tool shadowing (Invariant Labs)](https://invariantlabs.ai/blog/whatsapp-mcp-exploited)** — A second, untrusted MCP server steers the agent into walking WhatsApp history out through the trusted server. Cross-server shadowing.
- **[MCPTox](https://arxiv.org/abs/2508.14925)** — Tool-description poisoning measured on 45 live MCP servers and 353 real tools. o1-mini followed the poisoned metadata 72.8% of the time. Score an agent with it.
- **[OWASP MCP Security Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/MCP_Security_Cheat_Sheet.html)** — Short MCP review: schema integrity, rug pulls, shadowing, confused deputy, over-scoped tokens. Walk it on every server you connect.
- **[SlowMist MCP Security Checklist](https://github.com/slowmist/MCP-Security-Checklist)** — Longer MCP audit checklist. Use it when the OWASP sheet is too thin for a full server review.
- **[mcp-remote command injection (JFrog)](https://jfrog.com/blog/2025-6514-critical-mcp-remote-rce-vulnerability/)** — CVE-2025-6514. mcp-remote 0.0.5–0.1.15 runs a command from an untrusted MCP authorization URL. Fixed in 0.1.16. Check the version before a remote proxy is in scope.
- **[MCP Inspector RCE (Tenable)](https://www.tenable.com/blog/how-tenable-research-discovered-a-critical-remote-code-execution-vulnerability-on-anthropic)** — CVE-2025-49596. Inspector before 0.14.1 did not authenticate the browser UI to the local proxy, so a malicious site could launch stdio commands.
- **[A2ABreak](https://arxiv.org/abs/2609.10871)** — Eleven breaks in the Agent2Agent spec a compliant peer can exploit: unattested skill claims, context-id injection, credentials lost across delegation hops. The A2A test plan.

<p align="right"><a href="#top">↑ back to top</a></p>

<a id="computer-use-browser-agents"></a>

## 🖱️ Computer-Use & Browser Agents

The agent is driving a real desktop or browser. Injection arrives as pixels, pages, and pop-ups, and the impact is a click, a shell, or an exfil.

Also scored elsewhere: VPI-Bench (Multimodal), WASP and OS-Harm (Benchmarks). Agentic-browser field notes: Brave and Guardio (People).

- ⭐ **[ZombAIs (Embrace The Red)](https://embracethered.com/blog/posts/2024/claude-computer-use-c2-the-zombais-are-coming/)** — Indirect prompt injection against Claude's computer-use agent that ends in a payload and command-and-control. The end-to-end chain.
- **[Attacking computer agents via pop-ups](https://arxiv.org/abs/2411.02391)** — On-screen pop-ups that vision-language computer agents click. 86% average click-through in OSWorld and VisualWebArena. Code is SALT-NLP/PopupAttack, quiet since late 2024.
- ⭐ **[RedTeamCUA](https://github.com/OSU-NLP-Group/RedTeamCUA)** — ICLR 2026 oral. Hybrid web-and-OS sandbox plus RTC-Bench for indirect injection against computer-use agents. Use it when the attack has to leave the browser and touch the desktop.
- **[OSWorld](https://github.com/xlang-ai/OSWorld)** — The desktop lab those attacks need: real applications, screenshot in, action out. NeurIPS 2024 benchmark, still maintained. Stand up a computer-use target you control.

<p align="right"><a href="#top">↑ back to top</a></p>

## 🧠 Memory Poisoning & Persistent Agent-State

The 2026 frontier. Don't jailbreak the model — poison its persistent state, then let normal retrieval, personalization, or tool-selection turn that into future behavior. One write, many sessions.

- ⭐ **[Sleeper Memory Poisoning (Hidden in Memory)](https://arxiv.org/abs/2605.15338)** — 2026's headline agent attack: one poisoned doc writes a dormant false "memory" that fires in later sessions — 99.8% insertion on GPT-5.5. Injection goes from one-shot to persistent.
- **[Poison Once, Exploit Forever (eTAMP)](https://arxiv.org/abs/2604.02623)** — Web agent stores a contaminated trajectory from a manipulated page, then retrieves it on a different site/task later. Cross-session memory poisoning, no direct memory access.
- **[MemMorph](https://arxiv.org/abs/2605.26154)** — Tool hijacking via memory poisoning: benign-looking records make the agent "infer" the attacker's preferred tool — up to 85.9% from 3 injected records.
- **[Visual Inception](https://arxiv.org/abs/2604.16966)** — Multimodal memory poisoning: user-uploaded images with semantic triggers steer an agentic recommender's later planning (~85% goal-hit).
- **[MPBench — Memory Poisoning Benchmark](https://arxiv.org/abs/2606.04329)** — Systematic study of how untrusted input becomes trusted memory: 4 memory-write channels, 9 structural weaknesses. The map for the memory-poisoning attack class.

<p align="right"><a href="#top">↑ back to top</a></p>

## 🖥️ Coding-Assistant & Agent Attacks

Copilots and coding agents run with your privileges — poison the context, own the shell.

- **[TrustFall — 1-click RCE (Adversa)](https://adversa.ai/blog/trustfall-coding-agent-security-flaw-rce-claude-cursor-gemini-cli-copilot/)** — Folder-trust abuse: a malicious repo spawns unsandboxed code on Claude Code, Cursor, Gemini CLI, Copilot with one keypress.
- ⭐ **[IDEsaster (MaccariTA)](https://maccarita.com/posts/idesaster/)** — Prompt injection plus ordinary IDE features: 24 CVEs across Cursor, Copilot, Windsurf, Roo Code, Junie, Cline, and others. A poisoned repo becomes secret theft or RCE.
- ⭐ **[CurXecute (Aim Labs)](https://www.catonetworks.com/blog/curxecute-rce/)** — CVE-2025-54135. Indirect prompt injection rewrites Cursor's `mcp.json` and the new MCP server starts before the user can reject the edit. Fixed in 1.3.9.
- **[MCPoison (Check Point)](https://research.checkpoint.com/2025/cursor-vulnerability-mcpoison/)** — CVE-2025-54136. Cursor trusted an MCP entry by name, so a later change to the command ran without a new approval. Fixed in 1.3.
- **[CamoLeak (Legit Security)](https://www.legitsecurity.com/blog/camoleak-critical-github-copilot-vulnerability-leaks-private-source-code)** — GitHub Copilot Chat leaked private code via remote prompt injection and a CSP bypass through GitHub's own image proxy (CVSS 9.6). GitHub's fix was to stop rendering those images.
- **["Your AI, My Shell"](https://arxiv.org/abs/2509.22040)** — Systematic study of prompt-injection → shell on agentic AI editors. 85%+ success with adaptive attacks.
- **[Prompt Injection on Agentic Coding Assistants](https://arxiv.org/abs/2601.17548)** — Vulnerability analysis across skills, tools, and MCP ecosystems.
- **[CSA — AI Coding Assistants as Attack Surface](https://labs.cloudsecurityalliance.org/research/csa-research-note-ai-coding-assistant-attack-surface-2026040/)** — Practitioner note: code, skills, and secrets as entry points.
- **[Hacking Auto-GPT → Docker escape (RCE)](https://positive.security/blog/auto-gpt-rce)** — Indirect prompt injection into an autonomous agent → arbitrary code exec → container escape. Classic agent-RCE chain.
- **[AIShellJack — "Attacker's Shell"](https://arxiv.org/abs/2605.25871)** — 314 payloads / 70 MITRE ATT&CK techniques against Cursor & Copilot workflows: 41–84% success. Injection → file access, cred discovery, command exec.
- **[GitInject](https://arxiv.org/abs/2606.09935)** — Prompt injection in AI-powered GitHub CI/CD pipelines — tests real Actions permission boundaries, runner state, and token exposure, not toy tool calls.
- **[Are AI-Assisted Dev Tools Immune to Prompt Injection?](https://arxiv.org/abs/2603.21642)** — Empirical tool-poisoning test across Claude Desktop/Code, Cursor, Cline, Continue, Gemini CLI, and Langflow. Spoiler: no.
- **[Month of AI Bugs](https://monthofaibugs.com/)** — Rehberger's index of production computer-use and coding-agent bugs from August 2025. Open it when you want the chains, then the single-CVE writeups.

<p align="right"><a href="#top">↑ back to top</a></p>

## 🧩 Agent Skills & Tool Supply-Chain

Skills and tools are natural-language instructions bundled with executable code — a supply-chain surface hiding in plain sight, especially for coding agents.

- ⭐ **[Rules File Backdoor (Pillar Security)](https://www.pillar.security/blog/new-vulnerability-in-github-copilot-and-cursor-how-hackers-can-weaponize-code-agents)** — Invisible-Unicode instructions in `.cursorrules` / `copilot-instructions.md` → the AI writes backdoors and hides its own logs.
- **[SkillJect](https://arxiv.org/abs/2602.14211)** — Automates skill-based prompt injection for skill-enabled agents: hides payloads in helper files and rewrites SKILL.md so execution reads as a normal prerequisite.
- ⭐ **["Do Not Mention This to the User" (USENIX Sec'26)](https://arxiv.org/abs/2602.06547)** — In-the-wild study of 98,380 agent skills: 157 confirmed malicious, 632 vulns across 13 techniques. The skill ecosystem is a live supply-chain surface.
- **[MalSkillBench](https://arxiv.org/abs/2606.07131)** — Runtime-verified benchmark of malicious agent skills; code-injection skills verify more reliably than prompt-injection ones — scanners must reason over intent + code + instructions jointly.
- **[awesome-agent-skills-security](https://github.com/LLMSecurity/awesome-agent-skills-security)** — Curated attacks/defenses/benchmarks for agent tool-use & skill ecosystems.
- **[Agent Audit](https://github.com/HeadyZhang/agent-audit)** — Static scanner for agent code + MCP configs: 66 rules mapped to OWASP Agentic Top 10 (tool poisoning, shadowing, rug pulls, unsafe inputs, secrets) → SARIF / GitHub code-scanning.
- **[Skill-Inject](https://arxiv.org/abs/2602.20156)** — Benchmark measuring agent vulnerability to malicious/compromised skill files — the supply-chain surface for Claude Code / Codex-style skill ecosystems.

<p align="right"><a href="#top">↑ back to top</a></p>

## 💉 Prompt Injection & Jailbreaks

The core offensive discipline. Read the theory, steal the payloads.

- **[Simon Willison — Prompt Injection series](https://simonwillison.net/tags/prompt-injection/)** — Canonical writing on injection & the "lethal trifecta." Start here.
- ⭐ **[L1B3RT4S (Pliny)](https://github.com/elder-plinius/L1B3RT4S)** — Living collection of working jailbreak prompts per vendor. The reference corpus.
- **[CL4R1T4S (Pliny)](https://github.com/elder-plinius/CL4R1T4S)** — Extracted/leaked system prompts for major AI products. Recon gold.
- **[Prompt Hacking Resources (PromptLabs)](https://github.com/PromptLabs/Prompt-Hacking-Resources)** — Curated hub of red-teaming, jailbreaking, and injection resources.
- **[LLM Hacker's Handbook (Forces Unseen)](https://github.com/forcesunseen/llm-hackers-handbook)** — Practical, non-academic guide: fundamentals, injection, offense, defense. Repo quiet since 2023.
- **[greshake/llm-security](https://github.com/greshake/llm-security)** — "Not what you've signed up for" — the seminal indirect prompt-injection PoCs.
- **[Indirect Prompt Injection (Greshake et al.)](https://arxiv.org/abs/2302.12173)** — The paper behind that PoC. Indirect injection against real LLM-integrated apps, which is the pattern every copilot copied.
- ⭐ **[EchoLeak (Aim Labs / Cato)](https://www.catonetworks.com/blog/breaking-down-echoleak/)** — Zero-click Microsoft 365 Copilot chain, CVE-2025-32711: one email, RAG retrieval across the tenant, markdown-image exfil. The production indirect-injection report.
- **[Learn Prompting — Prompt Hacking](https://learnprompting.org/docs/prompt_hacking/introduction)** — Structured intro to injection/jailbreak/leaking.
- **[Arcanum Prompt Injection Taxonomy](https://github.com/Arcanum-Sec/arc_pi_taxonomy)** — Jason Haddix's structured classification of injection attack types (the `arc_pi_taxonomy` repo).
- **[PIPE — Prompt Injection Primer for Engineers](https://github.com/jthack/PIPE)** — Compact, practical primer on prompt injection for builders and red teamers. Repo quiet since 2023.
- **[CPH-SEC AI/LLM Red Team Field Manual](https://cph-sec.gitbook.io/ai-llm-red-team-handbook-and-field-manual/chapter_14_prompt_injection)** — 46-chapter AI red-team handbook + field manual (GitBook). Ch. 14 is the full direct/indirect prompt-injection playbook.
- **[PayloadsAllTheThings — Prompt Injection](https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/Prompt%20Injection)** — The classic payload bible now has a prompt-injection section. Starting points + bypasses.
- **[SecLists](https://github.com/danielmiessler/SecLists)** — The tester's wordlist companion — fuzzing payloads to feed your injection/fuzzing harness.
- **[The Big Prompt Library](https://github.com/0xeb/TheBigPromptLibrary)** — Huge collection of system prompts, jailbreaks, and protection prompts across ChatGPT/Copilot/Claude/Gemini. Recon + payload mine.
- **[Ignore Previous Prompt (Perez & Ribeiro)](https://arxiv.org/abs/2211.09527)** — The paper that put "prompt injection" on the map. Foundational reading.
- **[PALLMs — Payloads for Attacking LLMs](https://github.com/mik0w/pallms)** — Ready-to-fire payload collection for LLM attacks. Grab-and-go.
- **[Indirect Prompt Injection in the Wild](https://arxiv.org/abs/2604.27202)** — Scanned 1.2B URLs / 24.8M hosts: 15.3K validated indirect injections on 11.7K pages — ~70% hidden in non-rendered HTML (headers, comments, metadata). The threat is already live on the web.
- **[Prompt Injection 2.0: Hybrid AI Threats](https://arxiv.org/abs/2507.13169)** — Reframes agent attacks as combinations of prompt injection with XSS, CSRF, tool use, worms, and multi-agent behavior — not isolated prompt tricks.

<p align="right"><a href="#top">↑ back to top</a></p>

## 🧨 Jailbreak Frameworks & Methods

Attack-technique implementations — when a scanner isn't enough and you need the actual method.

- **[Many-shot jailbreaking (Anthropic)](https://www.anthropic.com/research/many-shot-jailbreaking)** — Hundreds of in-context harmful Q&A pairs walk a model past alignment. No gradients, no suffix, just a long prompt.
- ⭐ **[Crescendo](https://arxiv.org/abs/2404.01833)** — Multi-turn jailbreak that starts benign and escalates. This is the attack PyRIT's Crescendo orchestrator implements.
- **[Skeleton Key (Microsoft)](https://www.microsoft.com/en-us/security/blog/2024/06/26/mitigating-skeleton-key-a-new-type-of-generative-ai-jailbreak-technique/)** — One prompt that asks the model to "augment" rather than refuse, then stamps later answers with a warning. A policy bypass, not a suffix.
- **[TAP — Tree of Attacks with Pruning](https://arxiv.org/abs/2312.02119)** — An attacker model branches jailbreaks and drops the ones an evaluator rejects. Black-box and query-efficient; PyRIT ships it.
- **[Simple adaptive attacks (Andriushchenko et al.)](https://arxiv.org/abs/2404.02151)** — Breaks leading safety-aligned models, and a lot of published defenses, with straightforward adaptive search. A guardrail paper with no adaptive attack is not a result.
- **[EasyJailbreak](https://github.com/EasyJailbreak/EasyJailbreak)** — Unified framework: 11 classic attacks (AutoDAN, PAIR, GPTFuzz, DeepInception…) via Selector/Mutator/Constraint/Evaluator.
- **[GPTFuzz](https://github.com/hubertyoo/GPTFuzz)** — AFL-inspired black-box jailbreak fuzzer; auto-generates jailbreak templates from seeds.
- **[Open-Prompt-Injection](https://github.com/liu00222/Open-Prompt-Injection)** — USENIX Sec'24 benchmark: 5 injection attacks × 10 defenses × 10 LLMs × 7 tasks.
- **[HouYi](https://github.com/LLMSecurity/HouYi)** — Automated black-box prompt-injection framework for LLM-integrated apps.
- **[JailbreakZoo](https://github.com/Allen-piexl/JailbreakZoo)** — Catalog of jailbreak methods and papers for LLMs and multimodal models. Repo quiet since 2024.
- **[ArtPrompt (ASCII-art jailbreak)](https://github.com/uw-nsl/ArtPrompt)** — ACL'24 — encode blocked words as ASCII art to slip past alignment. Cheap, black-box.
- **[AutoDAN-Turbo](https://github.com/SaFo-Lab/AutoDAN-Turbo)** — ICLR'25 — lifelong agent that self-discovers jailbreak strategies from scratch.
- ⭐ **[PAIR — Jailbreaking in 20 Queries](https://github.com/patrickrchao/JailbreakingLLMs)** — Attacker-LLM iteratively refines a jailbreak against a black-box target; breaks GPT-4 in <20 queries. The efficient classic.
- **[MasterKey](https://arxiv.org/abs/2307.08715)** — Automated jailbreaks that transferred across multiple production LLM chatbots. Use it when the target is a vendor API and its filter, not a local weight file.
- **[Best-of-N Jailbreaks](https://arxiv.org/abs/2412.03556)** — Black-box: sample many augmented prompts, keep the ones that slip through. Dead simple, brutally effective across modalities.
- **[Jailbroken: How Does LLM Safety Training Fail?](https://arxiv.org/abs/2307.02483)** — Why aligned models break — competing objectives & mismatched generalization. The mental model behind most jailbreaks.
- **[CipherChat](https://github.com/RobustNLP/CipherChat)** — Jailbreak via ciphers — GPT-4 is "too smart to be safe": encode the chat, bypass the filter.
- **[DeepInception](https://github.com/tmlr-group/DeepInception)** — Nested-scene "hypnosis" jailbreak — wrap the ask in a story-within-a-story to erode refusals. Research code, quiet since early 2024.
- **[ReNeLLM — nested jailbreak](https://github.com/NJUNLP/ReNeLLM)** — "Wolf in sheep's clothing": generalized prompt rewriting + scenario nesting. Cheap and effective.

<p align="right"><a href="#top">↑ back to top</a></p>

## 🐍 Payload Obfuscation & Token Smuggling

Where nobody's looking. Beat filters that only read plaintext — encode, hide, and smuggle.

- ⭐ **[P4RS3LT0NGV3 / Parseltongue (Pliny)](https://elder-plinius.github.io/P4RS3LT0NGV3/)** — The payload crafter. Encode/mutate text into leetspeak, base64, runes, invisible Unicode, variation selectors — plus "tokenade" grenades that explode into thousands of tokens.
- **[P4RS3LT0NGV3 — source](https://github.com/elder-plinius/P4RS3LT0NGV3)** — Repo: universal text transformation, encoding/decoding, promptcrafting.
- **[Parseltongue (BASI Labs) — browser extension](https://github.com/BASI-LABS/parseltongue)** — Real-time tokenization viz + text conversion (binary/base64/leetspeak/unicode). Live crafting inside the target UI. Extension quiet since early 2025.
- **[Emoji Smuggler (Paul Butler)](https://emoji.paulbutler.org/)** — Hide arbitrary text inside a single emoji via Unicode variation selectors. Invisible-instruction channel.
- **[OpenAI Tokenizer](https://platform.openai.com/tokenizer)** — See exactly how a payload tokenizes. Essential for building smuggling / token-expansion attacks.
- **[Cryptex OSS](https://github.com/m4xx101/cryptex-oss)** — 159 transforms, 36 mutators, 26 tool surfaces, and 19 red-team labs, plus one-shot Campaign mode with an ASR report. MIT.
- **[Data Exfiltration Attacks (Simon Willison)](https://simonwillison.net/tags/exfiltration-attacks/)** — Curated running log of zero-click exfil via markdown-image rendering + ASCII/Unicode smuggling. The other half of obfuscation: getting data OUT.
- **[Invisible Unicode Tags Playground (jthack)](https://josephthacker.com/invisible_prompt_injection)** — Convert text to invisible Unicode tag characters to smuggle hidden instructions past filters and humans.
- **[ASCII→Unicode Reducer (jthack)](https://josephthacker.com/unicode_reducer)** — Re-encode ASCII as compact Unicode lookalikes to defeat brittle string filters.
- **[TokenBreak](https://arxiv.org/abs/2506.07948)** — Token-manipulation smuggling past text-classifier guards: perturb text so the BPE/WordPiece guard misclassifies while the main model (and humans) still recover the meaning.
- **[PUZZLED](https://arxiv.org/abs/2508.01306)** — Mask harmful keywords as anagrams / crosswords / word-search — the model's own reasoning reconstructs the instruction, so raw-prompt scanners miss it. 88.8% ASR across 5 LLMs.
- **[Controlled-Release Prompting](https://arxiv.org/abs/2510.01529)** — Exploits the cheap-guard vs strong-model split: encode intent so the lightweight prompt guard can't decode it but the main LLM can. The resource-asymmetry bypass.

<p align="right"><a href="#top">↑ back to top</a></p>

## ☁️ Cloud, Inference & LLMjacking

Where AI meets your cloud-security edge. SSRF a model endpoint, steal the token, ride the quota — or just hit the inference server that was never meant to face the network.

- **[HackTricks — Cloud SSRF → metadata creds](https://hacktricks.wiki/pentesting-web/ssrf-server-side-request-forgery/cloud-ssrf.html)** — SSRF an AI web app → hit the metadata service → steal the service-account token. AWS/Azure/GCP.
- **[Unit 42 — Autonomous AI attacks the cloud](https://unit42.paloaltonetworks.com/autonomous-ai-cloud-attacks/)** — Building an autonomous multi-agent cloud-offense system: recon → SSRF → token theft → lateral.
- **[Unit 42 — Attacking Bedrock multi-agent apps](https://unit42.paloaltonetworks.com/amazon-bedrock-multiagent-applications/)** — Abusing Amazon Bedrock multi-agent deployments. Concrete agentic-cloud tradecraft.
- **[Why Attackers Target AWS Bedrock (Vectra)](https://www.vectra.ai/resources/threat-briefing-why-attackers-target-aws-bedrock)** — LLMjacking + Bedrock abuse: stolen creds → invoke hosted models on the victim's bill.
- ⭐ **[LLMjacking (Sysdig)](https://www.sysdig.com/blog/llmjacking-stolen-cloud-credentials-used-in-new-ai-attack/)** — The report that coined "LLMjacking": stolen cloud creds proxied into hosted LLMs (Bedrock/Azure), victim foots up to ~$46k/day. The origin story of the category.
- **[ShadowRay (Oligo)](https://www.oligo.security/blog/shadowray-attack-ai-workloads-actively-exploited-in-the-wild)** — In-the-wild campaign against exposed Ray dashboards via disputed CVE-2023-48022. An open Ray port on an AI cluster is shared infrastructure, not a dev convenience.
- ⭐ **[Probllama — Ollama RCE (Wiz)](https://www.wiz.io/blog/probllama-ollama-vulnerability-cve-2024-37032)** — CVE-2024-37032, unauthenticated remote code execution in Ollama. An exposed Ollama port is a shell.
- **[LiteLLM MCP command injection (CSA)](https://labs.cloudsecurityalliance.org/research/csa-research-note-litellm-cve-2026-42271-ai-gateway-exploita/)** — CVE-2026-42271: command injection on LiteLLM's MCP test endpoints, chained with Starlette's BadHost auth bypass (CVE-2026-48710) to unauthenticated RCE. Added to CISA KEV in June 2026.
- **[Mind Your Key — LLM API Key Leakage in iOS Apps](https://arxiv.org/abs/2606.12212)** — 282 of 444 LLM-enabled iOS apps leaked exploitable credentials (plaintext keys, unauthenticated proxies, JWTs). The feeder channel for LLMjacking.

<p align="right"><a href="#top">↑ back to top</a></p>

## 🪱 AI Malware & Self-Propagating

Injection as a delivery mechanism. Where offense stops being one-shot and starts to spread.

- ⭐ **[Morris II — Zero-Click GenAI Worm](https://arxiv.org/abs/2403.02817)** — The seminal AI worm (Cornell Tech): adversarial self-replicating prompts that spread through GenAI email assistants, exfiltrating data with no human click.
- **[The Promptware Kill Chain](https://arxiv.org/abs/2601.09625)** — How prompt injections evolve into multi-step malware delivery. The tradecraft blueprint for weaponizing injection.

<p align="right"><a href="#top">↑ back to top</a></p>

## 🎭 Deepfake & Voice Offense

For authorized social-engineering ops — the media layer of the kill chain.

- **[DeepFaceLab](https://github.com/iperov/DeepFaceLab)** — The reference open-source face-swap toolkit. Archived November 2024; still what you reach for on authorized media ops.
- ⭐ **[RVC — Voice Conversion](https://github.com/RVC-Project/Retrieval-based-Voice-Conversion-WebUI)** — Retrieval-based voice cloning/conversion. Clone a voice from seconds of audio for authorized vishing simulations.
- **[Bishop Fox — Deepfakes in Red Teaming](https://bishopfox.com/resources/attacking-defending-deepfakes-virtual-session)** — Real-world lessons on operationalizing deepfakes in red-team engagements.
- **[Sirens' Whisper (SWhisper)](https://arxiv.org/abs/2603.13847)** — Inaudible near-ultrasonic prompts that demodulate through commodity mics to jailbreak speech-driven LLMs — black-box, and humans can't hear it. Physical-channel voice-agent attack.

<p align="right"><a href="#top">↑ back to top</a></p>

## 🖼️ Multimodal / Vision / Audio Attacks

Images, audio, and video are the softest injection channel. Everyone tests text; test the rest.

- ⭐ **[FigStep](https://github.com/CryptoAILab/FigStep)** — Typographic images that carry the instruction a text filter would block. AAAI 2025 oral, black-box, cheap. The reason a vision test is not optional.
- **[AdvWave](https://arxiv.org/abs/2412.08608)** — ICLR 2025. Adversarial audio that jailbreaks large audio-language models while sounding like ordinary noise. Use it when the target accepts a waveform, not only text.
- **[JailBreakV-28K](https://github.com/SaFo-Lab/JailBreakV_28K)** — 28k text-image jailbreak pairs; tests transferability of LLM jailbreaks to MLLMs. Go-to benchmark.
- **[MM-SafetyBench](https://github.com/isXinLiu/MM-SafetyBench)** — ECCV'24 image-based jailbreak benchmark: 13 categories, 1,680 samples.
- **[Awesome-MLLM-Safety](https://github.com/isXinLiu/Awesome-MLLM-Safety)** — Curated survey of multimodal LLM safety attacks & defenses.
- **[OmniSafeBench-MM](https://arxiv.org/abs/2512.06589)** — Unified multimodal attack-defense toolbox: 13 attacks, 15 defenses, 9 risk domains.
- **[Adversarial Attacks on MLLMs — Survey](https://arxiv.org/abs/2603.27918)** — Comprehensive 2026 survey of the multimodal attack surface.
- **[OpenRT](https://github.com/AI45Lab/OpenRT)** — Open-source red-teaming framework for multimodal LLMs — 42+ attack methods (ArtPrompt, Past Tense, LAA, imperceptible jailbreak).
- **[Image Hijacks](https://github.com/euanong/image-hijacks)** — Adversarial images that control a VLM's behavior at runtime — steer outputs with a crafted picture. Research code, quiet since 2023.
- **[UltraBreak](https://arxiv.org/abs/2602.01025)** — Universal, transferable jailbreak for vision-language models — regularizes the adversarial image so it survives black-box targets instead of overfitting one surrogate.
- **[MemJack — "Every Picture Tells a Dangerous Story"](https://arxiv.org/abs/2604.12616)** — Memory-augmented multi-agent jailbreak mapping entities in unmodified natural images to malicious intent — 71% ASR on Qwen3-VL (→90% extended). Ships MemJack-Bench (113k trajectories).
- ⭐ **[VPI-Bench](https://arxiv.org/abs/2506.02456)** — Visual prompt injection against computer-use agents: instructions embedded in rendered UIs across 5 platforms — CUAs deceived up to 51%, browser-use agents up to 100%. DOM-text sanitization isn't enough.
- **[GRM — Audio LLM Jailbreak](https://arxiv.org/abs/2604.09222)** — Utility-aware audio jailbreak: perturbs only the Mel bands that drive jailbreak success while preserving transcription/QA utility — 88% average ASR across 4 audio LLMs.

<p align="right"><a href="#top">↑ back to top</a></p>

## 📚 RAG & Vector DB Security

RAG is the enterprise default — and its knowledge base is an injection sink.

- ⭐ **[PoisonedRAG](https://github.com/sleeepeer/PoisonedRAG)** — USENIX Sec'25 — first knowledge-corruption attack on RAG. 90% success with 5 poisoned docs.
- ⭐ **[AgentPoison](https://github.com/AI-secure/AgentPoison)** — NeurIPS 2024. Backdoor a RAG store or long-term memory so a trigger query retrieves the attacker's demo, at under a 0.1% poison rate. Official code, still updated.
- **[Phantom](https://arxiv.org/abs/2405.20485)** — One poisoned document, retrieved only when the query contains a chosen trigger, then an adversarial suffix steers the answer. Demonstrated on NVIDIA Chat with RTX.
- **[ConfusedPilot](https://arxiv.org/abs/2408.04870)** — Confused-deputy / access-control bypass in RAG (demoed on M365 Copilot).
- **[RAG Poisoning POC (Prompt Security)](https://github.com/prompt-security/RAG_Poisoning_POC)** — Stealthy injection/poisoning via vector-DB embeddings.
- **[RAG Data Poisoning — Promptfoo](https://www.promptfoo.dev/blog/rag-poisoning/)** — Clear practitioner explainer of RAG poisoning mechanics and testing.
- **[SilentRetrieval](https://arxiv.org/abs/2605.28074)** — Semantically-preserving RAG corpus poisoning that survives fluency/perplexity screening — retrieval hijack with one poisoned doc per query; transfers to unseen retrievers (ColBERT + commercial embeddings).
- **[PIDP-Attack](https://arxiv.org/abs/2603.25164)** — Compound RAG attack: inference-time prompt injection + poisoned passages together, without knowing the exact query. Beats PoisonedRAG by 4–16 points across 8 LLMs.
- **[RefineRAG](https://arxiv.org/abs/2604.07403)** — Word-level RAG poisoning: generate harmful seeds, then optimize wording with the retriever in the loop — 90% success on Natural Questions while killing grammar/repetition artifacts.
- **[M3Att — Medical Multimodal RAG Poisoning](https://arxiv.org/abs/2605.10253)** — Covert, clinically-plausible misinformation + paired visual triggers that promote retrieval in medical multimodal RAG. Needs provenance + image integrity, not just answer-level safety.

<p align="right"><a href="#top">↑ back to top</a></p>

## 🧪 Adversarial ML (classic model attacks)

Evasion and poisoning — the pre-LLM foundations that still bite. Extraction, inversion, and membership inference are the next section.

- ⭐ **[Adversarial Robustness Toolbox (ART)](https://github.com/Trusted-AI/adversarial-robustness-toolbox)** — Most complete adversarial ML library: evasion, poisoning, extraction, inference.
- **[Counterfit (Microsoft)](https://github.com/Azure/counterfit)** — CLI to orchestrate attacks against ML models; wraps ART/TextAttack. Archived July 2025.
- **[TextAttack](https://github.com/QData/TextAttack)** — NLP adversarial attacks, augmentation, adversarial training.
- **[Foolbox](https://github.com/bethgelab/foolbox)** — Fast evasion attacks (FGSM/PGD/C&W) across PyTorch/TF/JAX.
- **[CleverHans](https://github.com/cleverhans-lab/cleverhans)** — OG adversarial-examples library for benchmarking attacks and defenses. Historical library, quiet since 2024.
- ⭐ **[GCG — Universal & Transferable Attacks](https://github.com/llm-attacks/llm-attacks)** — Reference implementation of the transferable adversarial suffix attack + AdvBench. Repo quiet since 2024.
- **[GCG paper — Universal & Transferable Attacks](https://llm-attacks.org/)** — The paper behind that suffix attack. Foundational transferable-jailbreak result.

<p align="right"><a href="#top">↑ back to top</a></p>

## 🔓 Model Extraction, Inversion & Membership Inference

API access is enough. Steal a training row, a prompt, or a slice of the weights — then put a number on it.

- **[Extracting Training Data from LLMs (Carlini et al.)](https://arxiv.org/abs/2012.07805)** — The seminal training-data extraction attack — memorization = leakage. Foundation of model privacy attacks.
- ⭐ **[Scalable Extraction from Production LMs (Nasr, Carlini et al.)](https://arxiv.org/abs/2311.17035)** — Training data, including PII, pulled out of production ChatGPT. The extraction result you cite when a client says "the API doesn't leak."
- **[Stealing Part of a Production Language Model](https://arxiv.org/abs/2403.06634)** — Recover a production model's embedding projection layer through API queries. Model theft without the weight file.
- **[vec2text — Language Model Inversion](https://github.com/vec2text/vec2text)** — Reconstruct input text from embeddings. Invert the model; leak what it saw.
- **[Membership Inference (Shokri et al.)](https://arxiv.org/abs/1610.05820)** — The attack that defined the class: decide whether a point was in the training set from the model's outputs.
- **[LiRA — Membership Inference From First Principles](https://arxiv.org/abs/2112.03570)** — Carlini et al.'s likelihood-ratio test. The method later papers are measured against; calibrated, and it works on harder targets.
- **[Privacy Meter](https://github.com/privacytrustlab/ml_privacy_meter)** — Open-source library for running membership-inference audits. Use it when the question is whether a row trained the model. Repo quiet since early 2025.

<p align="right"><a href="#top">↑ back to top</a></p>

## ☠️ Data Poisoning & Backdoors

Attack the model before it's a model. Training-time is the highest-leverage, lowest-noise vector.

- ⭐ **[Sleeper Agents (Anthropic)](https://arxiv.org/abs/2401.05566)** — Models trained to look aligned, then drop the act on a trigger — and the behavior survives safety training. Not the same thing as runtime memory poisoning.
- **[BackdoorBench](https://github.com/SCLBD/BackdoorBench)** — Backdoor-learning benchmark: attacks and defenses in one harness. Repo quiet since 2025.
- **[TrojanZoo](https://github.com/ain-soph/trojanzoo)** — Unified platform for evaluating neural backdoor attacks/defenses end-to-end.
- **[TrojAI (NIST)](https://github.com/usnistgov/trojai-literature)** — NIST's Trojan-in-AI program + curated literature.
- **[Backdoor Learning Resources](https://github.com/THUYimingLi/backdoor-learning-resources)** — Massive curated bibliography of backdoor attack/defense papers & code.
- **[Stealthy Pickle Model Poisoning](https://arxiv.org/abs/2508.19774)** — 2025 research making pickle-based supply-chain poisoning evade scanners again.
- **[PoisonGPT (Mithril Security)](https://blog.mithrilsecurity.io/poisongpt-how-we-hid-a-lobotomized-llm-on-hugging-face-to-spread-fake-news/)** — Surgically edited an LLM to spread targeted fake news, then reuploaded it to Hugging Face. The model supply-chain wake-up call.
- **[Fine-Tuning Breaks Safety](https://github.com/LLM-Tuning-Safety/LLMs-Finetuning-Safety)** — A few adversarial (or even benign) fine-tune steps strip alignment. Repo plus the HEx-PHI dataset. Research code, quiet since early 2024.
- **[Cordyceps](https://arxiv.org/abs/2605.26595)** — Covert-control backdoor: teach a model a semantic information-hiding scheme so arbitrary malicious instructions encode/decode post-poisoning. Defeats trigger-scanning + clean-data regularization.
- **[MirageBackdoor](https://arxiv.org/abs/2604.06840)** — "Think well, answer wrong": preserves a plausible clean chain-of-thought while steering only the final answer under a trigger. Beats CoT / process-monitoring defenses.

<p align="right"><a href="#top">↑ back to top</a></p>

## 🔗 MLSecOps & Model Supply Chain

Malicious weights, poisoned pickles, and the guardrails you'll be measured against.

- **[ModelScan (Protect AI)](https://github.com/protectai/modelscan)** — Scans H5, Pickle (and pickle-derived), and SavedModel files for serialization attacks and code injection before load.
- **[picklescan](https://github.com/mmaitre314/picklescan)** — Detects malicious pickles; used across the HF/PyPI ecosystem.
- ⭐ **[Fickling (Trail of Bits)](https://github.com/trailofbits/fickling)** — Decompile/analyze/inject Python pickles; craft and detect malicious model files.
- ⭐ **[Sleepy Pickle (Trail of Bits)](https://blog.trailofbits.com/2024/06/11/exploiting-ml-models-with-pickle-file-attacks-part-1/)** — Built on Fickling. A malicious pickle patches weights or hooks model methods at load, so the model itself is the payload, not only the machine that unpickled it.
- **[nullifAI (ReversingLabs)](https://www.reversinglabs.com/blog/rl-identifies-malware-ml-model-hosted-on-hugging-face)** — Malformed pickles on the Hugging Face Hub that the scanner marked clean. A green Hub scan is not a result when the pickle is deliberately broken.
- **[PickleScan zero-days (JFrog)](https://jfrog.com/blog/unveiling-3-zero-day-vulnerabilities-in-picklescan/)** — Three PickleScan bypasses from December 2025, fixed in 0.0.31, including a file-extension trick (CVE-2025-10155). A green scan on an old picklescan is not a result.
- **[Safetensors conversion hijack (HiddenLayer)](https://www.hiddenlayer.com/research/silent-sabotage)** — A model uploaded for Safetensors conversion hijacked Hugging Face's conversion bot, which could then open pull requests on other repos. The format stayed data-only. The bot was the bug.
- **[Hugging Face pickle scanning](https://huggingface.co/docs/hub/en/security-pickle)** — What the Hub's pickle scanner claims to detect. Read it beside the bypasses above before you treat a "safe" badge as a finding.
- **[NeMo Guardrails (NVIDIA)](https://github.com/NVIDIA-NeMo/Guardrails)** — *Bypass target.* Programmable guardrails. Know it to beat it.
- **[LLM Guard (Protect AI)](https://github.com/protectai/llm-guard)** — *Bypass target.* Input/output scanners (injection, PII, toxicity). Archived July 2026.
- **[Rebuff](https://github.com/protectai/rebuff)** — *Bypass target.* Multi-layer prompt-injection detector. Archived August 2024.
- **[Vigil](https://github.com/deadbits/vigil-llm)** — *Bypass target.* Injection/jailbreak detection scanners. Quiet since 2024.
- **[Guardrails AI](https://github.com/guardrails-ai/guardrails)** — *Bypass target.* Composable validators (schema, regex, PII, toxicity) with re-ask loops.
- **[Anthropic Constitutional Classifiers](https://www.anthropic.com/research/constitutional-classifiers)** — *Bypass target.* Rule-based alignment classifiers (Anthropic's jailbreak defense). Study the approach to route around it.
- **[Meta Prompt Guard 86M](https://huggingface.co/meta-llama/Prompt-Guard-86M)** — *Bypass target.* Small classifier for detecting injection/jailbreak inputs. Fingerprint it, then evade.
- **[Circuit Breakers (Gray Swan)](https://github.com/GraySwanAI/circuit-breakers)** — *Bypass target.* Representation-engineering defense that short-circuits harmful generations. Repo quiet since 2024.

<p align="right"><a href="#top">↑ back to top</a></p>

## 🕹️ Labs, CTFs & Challenges

Hands-on reps. Where you actually build the skill.

- ⭐ **[Gandalf (Lakera)](https://play.lakera.ai/agent-breaker)** — Lakera's hosted AI-hacking game (the Gandalf line, now Agent Breaker). The on-ramp.
- **[Crucible (Dreadnode)](https://app.dreadnode.io/)** — Dreadnode's hosted AI-challenge platform. The old Crucible host now lands on the app, and sign-in is required.
- **[HackAPrompt](https://www.hackaprompt.com/)** — Largest prompt-injection competition; huge public attack dataset.
- ⭐ **[PortSwigger — Web LLM Attacks](https://portswigger.net/web-security/llm-attacks)** — Free labs: API abuse, excessive agency, indirect injection, insecure output handling.
- **[Prompt Airlines (Wiz)](https://promptairlines.com/)** — 5-stage CTF: manipulate an airline chatbot for a free ticket.
- **[Doublespeak (Forces Unseen)](https://doublespeak.chat/)** — Text game on LLM sandboxing: extract the bot's hidden name.
- **[Arcanum AI Security Lab Hub](https://arcanum-sec.github.io/ai-sec-resources/)** — Jason Haddix's directory: 71 labs, plus competitions, bounties, tools, and taxonomies.
- **[AIGoat — vulnerable LLM playground](https://github.com/AISecurityConsortium/AIGoat)** — Vulnerable AI e-commerce app covering the full OWASP LLM Top 10. Runs locally.
- **[ai-goat (dhammon)](https://github.com/dhammon/ai-goat)** — Local vulnerable-LLM CTF. No signups, no cloud fees. Repo quiet since 2024.
- **[OWASP Vulnerable Web Apps Directory](https://vwad.owasp.org/)** — Registry of legal vulnerable targets — now indexes AI/LLM apps.
- **[Microsoft AI Red Teaming Playground Labs](https://github.com/microsoft/AI-Red-Teaming-Playground-Labs)** — Official MS labs from the Black Hat "AI Red Teaming in Practice" course; several automated with PyRIT notebooks. Infra included.
- **[MyLLM Bank (WithSecure)](https://myllmbank.com/)** — Multi-LLM banking CTF — learn real-world prompt-injection chains.
- **[MyLLM Doctor (WithSecure)](https://myllmdoc.com/)** — Medical chatbot challenge — multi-stage injection and policy evasion.
- **[HackMerlin](https://hackmerlin.io)** — Wizard-themed prompt-injection game — coax escalating passwords out of Merlin across levels. Slick, addictive on-ramp.
- **[Tensor Trust](https://tensortrust.ai)** — Attack-and-defend prompt-injection game (UC Berkeley) — build a defense, break everyone else's. Ships a large public human attack dataset.
- **[LLMail-Inject (Microsoft)](https://microsoft.github.io/llmail-inject)** — Adaptive prompt-injection challenge: sneak instructions past defenses in a simulated LLM email client. Real evasion, real dataset.
- **[The Great Escape (Pangea)](https://escape.pangea.cloud)** — Multi-room LLM prompt-injection escape challenge with prize pools — jailbreak your way out room by room.
- **[Invariant Agent CTF (Challenge 24)](https://invariantlabs.ai/play-ctf-challenge-24)** — Hosted agent-security CTF from the MCP-security crew — practice injection + tool abuse on a real tool-using agent.

<p align="right"><a href="#top">↑ back to top</a></p>

## 📊 Benchmarks & Datasets

Standardized attacks and behaviors — for measuring, comparing, and building your own harness.

- ⭐ **[HarmBench](https://github.com/centerforaisafety/HarmBench)** — Standardized automated red-teaming eval (attacks + defenses), textual and multimodal. Benchmark repo quiet since 2024; the eval is still the reference.
- **[JailbreakBench](https://github.com/JailbreakBench/jailbreakbench)** — Open robustness benchmark; JBB-Behaviors (200 behaviors), leaderboard. Repo quiet since early 2025; the behavior set is still the reference.
- **[AgentHarm](https://arxiv.org/abs/2410.09024)** — 110 malicious agent tasks (440 augmented) across 11 harm categories.
- **[Purple Llama / CyberSecEval (Meta)](https://github.com/meta-llama/PurpleLlama)** — Security & safety evals + Llama Guard.
- **[In-The-Wild Jailbreak Prompts (verazuo)](https://github.com/verazuo/jailbreak_llms)** — CCS'24 dataset: 15,140 real prompts (1,405 jailbreaks). Gold corpus. Same set on Hugging Face as `TrustAIRLab/in-the-wild-jailbreak-prompts`.
- **[BIPIA (Microsoft)](https://github.com/microsoft/BIPIA)** — Benchmark for indirect prompt-injection attacks and defenses. Archived April 2024; still the classic indirect-injection set.
- ⭐ **[StrongREJECT](https://arxiv.org/abs/2402.10260)** — Rubric that refuses to count an empty or off-topic answer as a jailbreak. Use it or your attack-success rate is fiction.
- **[InjecAgent](https://github.com/uiuc-kang-lab/InjecAgent)** — 1,054 indirect-injection cases against tool-using agents (17 user tools, 62 attacker tools). The standard agent IPI benchmark. Research code, quiet since 2024.
- **[DeepRed — Partial-Credit CTF Eval](https://arxiv.org/abs/2604.19354)** — LLM agents in isolated Kali+target VMs with checkpoint scoring; best model only 35% avg checkpoint completion. Realistic offensive-agent benchmark.
- **[CTFusion](https://arxiv.org/abs/2605.11504)** — Evaluates agents on LIVE CTFs to kill benchmark contamination; live solve ~5–7% vs inflated static scores. Leakage-resistant agent eval.
- **[WASP](https://arxiv.org/abs/2504.18575)** — Benchmarks web-agent security against prompt injection (Operator, Claude Computer Use): agents execute the injected instruction 16–86% of the time. Measures steerability under attack.
- **[OS-Harm](https://arxiv.org/abs/2506.14866)** — Safety benchmark for computer-use agents across email, browser, and code editors — covers deliberate misuse, prompt injection, and model misbehavior.
- **[Offensive Cyber Capability Benchmark](https://arxiv.org/abs/2604.17159)** — Systematic benchmark of 10 frontier LLMs on offensive tasks; a Kali environment beat Ubuntu by 9.5 points — tooling/environment matters more than "uncensored" branding.
- **[SafeClawBench](https://arxiv.org/abs/2606.18356)** — 600 adversarial cases across direct/indirect injection, tool-return injection, memory poison/extract, and unsafe inference — scores sandbox-observed harm, not just "the model said a bad thing."
- **[AgentDyn](https://arxiv.org/abs/2602.03117)** — Dynamic agent-security benchmark: 60 open-ended tasks / 560 injection cases across Shopping, GitHub, Daily-Life — 10 SOTA defenses were either insufficiently secure or over-blocked.

<p align="right"><a href="#top">↑ back to top</a></p>

## 💰 Bug Bounty & Disclosure

Turn skill into reputation and income.

- ⭐ **[huntr (Protect AI)](https://huntr.com/)** — The AI/ML bug bounty platform. CVE-issuing. Best entry point.
- **[Mozilla 0din](https://0din.ai/)** — Mozilla's GenAI bug bounty for injection, guardrail bypass, and model vulns.
- **[Gray Swan Arena](https://www.grayswan.ai/)** — Paid jailbreak/agent competitions — and a talent funnel to top labs.
- **[AI Vulnerability Database (AVID)](https://avidml.org/)** — Open knowledge base of AI/ML failure modes & vulns.
- **[AI Incident Database](https://incidentdatabase.ai/)** — Real-world AI harm/incident reports; recon for impact narratives.
- ⭐ **[OpenAI Safety Bug Bounty](https://openai.com/index/safety-bug-bounty/)** — 2026 program for agent hijack and data exfil (including MCP), proprietary-info exposure, and account integrity. A jailbreak with no safety impact is out of scope.
- **[Anthropic Model Safety Bug Bounty](https://support.claude.com/en/articles/12119250-model-safety-bug-bounty-program)** — HackerOne program for universal jailbreaks that beat Constitutional Classifiers on deployed ASL-3 systems. One-off prompts are not the target.
- **[Microsoft Copilot Bounty](https://www.microsoft.com/en-us/msrc/bounty-ai)** — MSRC program for Copilot and AI/ML issues, $100–$30,000. Submit as "Copilot, AI+ML, and LLMs" and include the conversation id from `/id`.
- **[xAI / Grok on HackerOne](https://hackerone.com/x)** — Product vulnerabilities in Grok and xAI. Prompt injection and jailbreaks are not this bounty; those go to safety@x.ai.
- **[Google AI Vulnerability Reward Program](https://bughunters.google.com/about/rules/google-friends/ai-vulnerability-reward-program-rules)** — Gemini, Search, and Workspace. Pays for rogue actions and sensitive-data exfiltration. A jailbreak that only affects the researcher's own session is out of scope.

<p align="right"><a href="#top">↑ back to top</a></p>

## 📖 Awesome Lists & Curations

Go deep. Where the next technique comes from.

<details>
<summary>Other lists — open for the deep cut</summary>

- **[Awesome-LLM-Red-Teaming](https://github.com/user1342/Awesome-LLM-Red-Teaming)** — Curated red-teaming training, tools, and resources.
- **[Awesome-LLMSecOps](https://github.com/wearetyomsmnv/Awesome-LLMSecOps)** — LLM / Agentic / Security / Operations in one well-illustrated repo.
- ⭐ **[Awesome-AI-Security (Tal Eliyahu)](https://github.com/TalEliyahu/Awesome-AI-Security)** — Broad, actively-maintained AI security index.
- **[Arcanum ai-sec-resources](https://github.com/Arcanum-Sec/ai-sec-resources)** — Jason Haddix's hub: labs, competitions, bounties, tools, taxonomies.
- **[OpenRedTeaming (Libr-AI)](https://github.com/Libr-AI/OpenRedTeaming)** — 30+ automated red-teaming methods + papers.
- **[Offensive AI Compilation (jiep)](https://github.com/jiep/offensive-ai-compilation)** — Broad "offensive AI" resource list — attacks on and with AI.
- **[awesome-ai-security (ottosulin)](https://github.com/ottosulin/awesome-ai-security)** — General AI security reading list.
- **[LLM Security Guide (requie)](https://github.com/requie/LLMSecurityGuide)** — OWASP GenAI-mapped reference.
- **[awesome-cybersecurity-agentic-ai](https://github.com/raphabot/awesome-cybersecurity-agentic-ai)** — Curated agentic-AI security resources.
- **[Awesome-LLM-Fingerprinting](https://github.com/shaoshuo-ss/Awesome-LLM-Fingerprinting)** — Paper list for LLM fingerprinting/copyright auditing — the recon-side reading.
- **[awesome-llm-security (corca-ai)](https://github.com/corca-ai/awesome-llm-security)** — One of the most-referenced LLM security lists — tools, papers, articles across attack & defense.
- **[Awesome-LM-SSP](https://github.com/CryptoAILab/Awesome-LM-SSP)** — LM safety, security, and privacy reading list. Repo moved to CryptoAILab.
- **[Awesome-LLM-Safety](https://github.com/ydyjya/Awesome-LLM-Safety)** — Date-sorted safety/security/privacy/jailbreak papers + talks; constantly backfilled.
- **[Awesome LLM Harmful Fine-Tuning](https://github.com/git-disl/awesome_LLM-harmful-fine-tuning-papers)** — Niche but sharp: papers on breaking alignment via fine-tuning — the fine-tuning attack surface.
- ⭐ **[awesome-mcp-security](https://github.com/puliczek/awesome-mcp-security)** — The MCP-specific index of advisories, writeups, and tools. Open it when the Agentic & MCP section is not deep enough.
- **[awesome-prompt-injection](https://github.com/Joe-B-Security/awesome-prompt-injection)** — Joe-B-Security's injection index, still updated. The next stop after Willison, L1B3RT4S, and the papers in Prompt Injection.

</details>

<p align="right"><a href="#top">↑ back to top</a></p>

## 🎓 Courses & Certifications

Structured skill + credentials that price your rate.

- ⭐ **[OffSec OSAI (AI-300)](https://www.offsec.com/courses/ai-300/)** — Advanced AI Red Teaming. 24-hour practical exam → OSAI cert. LLM/RAG/multi-agent + AI-in-cloud exploitation. Assumes OSCP-level skills.
- **[EC-Council COASP](https://www.eccouncil.org/ai-courses/certified-offensive-ai-security-professional-coasp-north-america/)** — Pure offensive AI red-teaming cert.
- **[Practical DevSecOps CAISP](https://www.practical-devsecops.com/certified-ai-security-professional/)** — Hands-on cert on LLM vulns, threat modeling, and the AI supply chain.
- **[SANS SEC545 — GenAI & LLM App Security](https://www.sans.org/cyber-security-courses/genai-llm-application-security)** — 5-day: threat-modeling GenAI, RAG/vector defense, injection, MLOps hardening.
- **[Learn Prompting](https://learnprompting.org/)** — Free docs + the org behind HackAPrompt.
- ⭐ **[Attacking AI — Arcanum (Jason Haddix)](https://arcanum-sec.com/training/attacking-ai/)** — Offensive-first AI hacking course from a bug-bounty legend. The practitioner pick.
- **[Karpathy — Deep Dive into LLMs](https://www.youtube.com/watch?v=7xTGNNLPyMI)** — Free 3.5h masterclass on how LLMs actually work. Nail internals → smuggle better.
- **[HTB AI Red Teamer Path (+ COAE cert)](https://academy.hackthebox.com/path/preview/ai-red-teamer)** — Hack The Box × Google job-role path: injection, model privacy, adversarial AI, supply chain. Capstone = HTB Certified Offensive AI Expert (COAE). Hands-on, SAIF-aligned.
- **[Red Teaming LLM Applications (DeepLearning.AI × Giskard)](https://www.deeplearning.ai/courses/red-teaming-llm-applications)** — Free short course (Andrew Ng + Giskard): manual + automated LLM red teaming, injection, at-scale. Best quick on-ramp.
- **[GenAI Security Training (schwartz1375)](https://github.com/schwartz1375/genai-security-training)** — 8 modules / 40 notebooks: injection, evasion, poisoning, ART — hands-on offensive AI curriculum.

<p align="right"><a href="#top">↑ back to top</a></p>

## 📕 Books

- ⭐ **[The Developer's Playbook for LLM Security — Steve Wilson](https://www.oreilly.com/library/view/the-developers-playbook/9781098162191/)** — From the OWASP LLM Top 10 lead. The practical LLM security bible.
- **[Generative AI Security: Theories & Practices — Ken Huang et al.](https://www.amazon.com/Generative-AI-Security-Theories-Practices/dp/3031542517)** — Comprehensive GenAI security across the stack.
- **[AI-Native LLM Security — Malik, Huang, Dawson](https://www.amazon.com/Native-LLM-Security-comprehensive-applications/dp/1836203756)** — Threats, defenses, best practices; strong on adversarial AI.
- **[Securing AI Agents — Ken Huang, Chris Hughes](https://www.amazon.com/Securing-Agents-Foundations-Frameworks-Real-World/dp/3032021294)** — Foundations + frameworks for agentic deployments.

> Also recommended: *Adversarial AI Attacks, Mitigations, and Defense Strategies* — John Sotiropoulos (Packt) — the most red-team-relevant MLSecOps book.

<p align="right"><a href="#top">↑ back to top</a></p>

## 🧑‍💻 People & Blogs to Follow

Follow the operators, not the vendors.

- ⭐ **[Johann Rehberger — Embrace The Red](https://embracethered.com/)** — (@wunderwuzzi23) The most important practical AI exploit researcher working today.
- ⭐ **[Simon Willison](https://simonwillison.net/)** — Coined "lethal trifecta"; the clearest thinking on injection & LLM app risk.
- **[Jason Haddix — Arcanum](https://arcanum-sec.com/)** — Executive Offense; AI hacking labs, taxonomies, offensive training from a bug-bounty legend.
- ⭐ **[Pliny the Liberator](https://github.com/elder-plinius)** — Jailbreak virtuoso; maintains L1B3RT4S / CL4R1T4S / P4RS3LT0NGV3.
- **[Adversa AI](https://adversa.ai/blog/)** — Adversarial ML & jailbreak research; "Towards Trusted AI."
- **[Lakera Blog](https://www.lakera.ai/blog)** — Gandalf makers; injection research & datasets.
- **[Trail of Bits](https://blog.trailofbits.com/)** — ML supply-chain & pickle exploitation; deep security engineering.
- **[NVIDIA Developer — AI Red Team](https://developer.nvidia.com/blog)** — The garak team; practical AI red-team writeups.
- **[Microsoft AI Red Team](https://learn.microsoft.com/en-us/security/ai-red-team/)** — The PyRIT team; lessons from red-teaming 100+ GenAI products.
- **[WithSecure Labs / Reversec](https://www.withsecure.com/en/resources-hub/w-labs/)** — WithSecure's research hub (the old labs host). LLM-agent injection writeups; Reversec is the spikee / DVLA crew.
- **[Haize Labs](https://haizelabs.com/)** — AI red-teaming research lab — automated "haizing"/jailbreak research (ACG accelerated GCG, red-team evals).
- **[Lilian Weng — Adversarial Attacks on LLMs](https://lilianweng.github.io/posts/2023-10-25-adv-attack-llm/)** — The canonical deep-dive explainer on adversarial attacks against LLMs. Read it twice.
- **[Daniel Miessler — AI Attack Surface Map](https://danielmiessler.com/blog/the-ai-attack-surface-map-v1-0)** — The canonical one-page map of the AI attack surface. Great for scoping and client decks.
- **[llmsecurity.net (@llm_sec)](https://llmsecurity.net/)** — Dedicated LLM-security blog + curation. Follow @llm_sec.
- **[Kai Greshake](https://kai-greshake.de/)** — Indirect-prompt-injection pioneer's blog — where a lot of this started.
- **[Varonis Threat Labs](https://www.varonis.com/blog/searchleak)** — SearchLeak / Reprompt: one-click Microsoft 365 Copilot data-exfil chaining parameter→prompt injection, a rendering race, and Bing SSRF. AI-native + classic-web chains.
- **[Brave — AI Browser Security](https://brave.com/blog/comet-prompt-injection/)** — Indirect prompt injection against agentic browsers (Comet): the agent acts across your authenticated sessions, breaking old web-security assumptions.
- **[AppOmni — Aaron Costello (SaaS security)](https://appomni.com/ao-labs/)** — "Second-order prompt injection": agents delegating to higher-privilege agents (ServiceNow Now Assist) turn workflow automation into a privilege-boundary problem.
- **[Guardio Labs](https://guard.io/labs)** — Scamlexity: agentic AI browsers vs fake shops, phishing, and hidden prompts — they clicked, they paid, they failed. Consumer-realistic agent attack surface.

<p align="right"><a href="#top">↑ back to top</a></p>

## 🗣️ Communities & Conferences

Stay current. The field moves weekly.

- ⭐ **[OWASP GenAI Security Project](https://genai.owasp.org/)** — The center of gravity. Join the Slack and working groups.
- ⭐ **[DEF CON AI Village](https://aivillage.org/)** — The community + Generative Red Team (GRT) events at DEF CON.
- **[MLSecOps Community](https://community.mlsecops.com/)** — Slack + resources for ML/AI security practitioners.
- **[CAMLIS](https://www.camlis.org/)** — Conference on Applied ML in Information Security. Practitioner-focused, red-team heavy.
- **[IEEE SaTML](https://satml.org/)** — Secure and Trustworthy ML — top academic venue for attacks/defenses.
- **[r/ChatGPTJailbreak](https://www.reddit.com/r/ChatGPTJailbreak/)** — The public jailbreak lab — fresh working jailbreaks and techniques daily.

<p align="right"><a href="#top">↑ back to top</a></p>

## 🎤 Talks

Watch the operators. A good demo beats another survey.

- ⭐ **[Indirect Prompt Injections in the Wild (Johann Rehberger)](https://www.youtube.com/watch?v=ADHAokjniE4)** — The briefing that made indirect injection concrete: real apps, real exfil, and what actually mitigates. Start here if you have one hour.
- **[SpAIware & More (Black Hat)](https://blackhat.com/html/webcast/06102025.html)** — Rehberger, June 2025. Tool abuse, memory persistence, and ASCII smuggling against Copilot, Gemini, Claude, and GitHub Copilot Chat.
- ⭐ **[Agentic ProbLLMs (39C3)](https://media.ccc.de/v/39c3-agentic-probllms-exploiting-ai-computer-use-and-coding-agents)** — Rehberger, Chaos Communication Congress 2025. Prompt injection to RCE, token theft, and C2 on computer-use and coding agents, distilled from the Month of AI Bugs disclosures. The one-hour version.

<p align="right"><a href="#top">↑ back to top</a></p>

## 📰 Newsletters & Podcasts

- ⭐ **[AI Security Newsletter (Tal Eliyahu)](https://github.com/TalEliyahu/AI-Security-Newsletter)** — Monthly digest: research, reports, tools, events (AISecHub).
- **[The Agentic Security Newsletter](https://agenticsecurity.substack.com/)** — Weekly on agent/multi-agent offense & defense.
- **[Executive Offense (Arcanum)](https://executiveoffense.beehiiv.com/)** — Jason Haddix's newsletter — practical offensive AI & red-team ops.
- **[AI Safety Takes (Daniel Paleka)](https://newsletter.danielpaleka.com/)** — Sharp monthly digest of AI safety/security research.
- **[Hackstery](https://hackstery.com/)** — Offensive-AI blog + newsletter; hands-on LLM hacking writeups.

<p align="right"><a href="#top">↑ back to top</a></p>

## 🏢 Vendor & Market Landscape

Competitive intel for building your own company — know the map before you plant a flag.

<details>
<summary>Company map — open for competitive intel</summary>

- **[Protect AI (Palo Alto Networks)](https://www.paloaltonetworks.com/ai-security/prisma-airs)** — Palo Alto Networks' AI security platform (Prisma AIRS). Protect AI — huntr, ModelScan, LLM Guard — was folded in.
- **[HiddenLayer](https://www.hiddenlayer.com/)** — Model scanning, runtime detection, adversarial red teaming.
- ⭐ **[Lakera](https://www.lakera.ai/)** — Runtime guardrails + Gandalf. AI-native security, strong research brand.
- **[Mindgard](https://mindgard.ai/)** — Continuous automated AI red teaming (academic roots).
- **[SplxAI](https://splx.ai/)** — AI red teaming + governance; makers of Agentic Radar.
- **[Prompt Security (SentinelOne)](https://prompt.security/)** — GenAI runtime security & posture; acquired by SentinelOne.
- **[Lasso Security](https://www.lasso.security/)** — Enterprise GenAI visibility, data protection, runtime controls.
- **[Aim Security (Cato Networks)](https://www.aim.security/)** — AI agent runtime security & posture; acquired by Cato.
- **[Knostic](https://www.knostic.ai/)** — Need-to-know access controls at the AI layer; stops copilot oversharing.
- **[Straiker](https://www.straiker.ai/)** — AI-native runtime security for embedded & shadow AI.
- **[Zenity](https://zenity.io/)** — Agentic AI security for copilots/low-code agents; makers of the GenAI Attacks Matrix.
- **[Cisco AI Defense](https://www.cisco.com/site/us/en/products/security/ai-defense/index.html)** — Enterprise AI security (incl. Robust Intelligence tech).
- **[Adversa AI](https://adversa.ai/)** — AI red teaming + secure-AI advisory; prolific research.
- **[AI Security Startups Watchlist (Top 30)](https://medium.com/ai-security-hub/ai-security-startups-watchlist-top-30-2025-5a95471bbacc)** — Tal Eliyahu's market map. Intel for positioning your own company.

</details>

<p align="right"><a href="#top">↑ back to top</a></p>

---

## Contributing

Pull requests welcome — this is a living list. **Rotate, re-angle, never stop.**

- One resource per line, in the right category, matching the format: `**[Name](url)** — one-line, operator-voice reason *why it matters*.`
- **Best-in-class only.** If it's a paper, it must be foundational or introduce a technique people actually use. No SEO blogspam, no dead/archived repos.
- Prefer the **canonical source URL** (official repo over a mirror; project page over a news article).
- Keep defenses in the relevant section tagged **_bypass target_** — this is an offense-first list.
- **⭐** marks the one or two entries to open first in a category.

See [CONTRIBUTING.md](CONTRIBUTING.md) for the full checklist.

## License

[MIT](LICENSE) © [Rafael Gacek](https://bersec.me) — do whatever, attribution appreciated.

<p align="center"><sub>Curated by <a href="https://bersec.me">Rafael Gacek</a> · hub at <a href="https://ai.bersec.me">ai.bersec.me</a> · also lives as a start.me board.</sub></p>
