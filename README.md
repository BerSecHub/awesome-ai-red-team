# 🔴 Awesome AI Red Team [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> The definitive, no-fluff resource list for **offensive AI security** — LLM red teaming, prompt injection, payload obfuscation, agentic/MCP attacks, multimodal, RAG poisoning, adversarial ML, model supply chain, and hacking *with* AI.

<p align="center">
  <a href="https://github.com/YOURHANDLE/awesome-ai-red-team/stargazers"><img src="https://img.shields.io/github/stars/YOURHANDLE/awesome-ai-red-team?style=flat-square&logo=github" alt="Stars"></a>
  <a href="https://github.com/YOURHANDLE/awesome-ai-red-team/network/members"><img src="https://img.shields.io/github/forks/YOURHANDLE/awesome-ai-red-team?style=flat-square&logo=github" alt="Forks"></a>
  <a href="https://github.com/YOURHANDLE/awesome-ai-red-team/graphs/contributors"><img src="https://img.shields.io/github/contributors/YOURHANDLE/awesome-ai-red-team?style=flat-square" alt="Contributors"></a>
  <a href="LICENSE"><img src="https://img.shields.io/github/license/YOURHANDLE/awesome-ai-red-team?style=flat-square" alt="License"></a>
  <a href="https://github.com/YOURHANDLE/awesome-ai-red-team/commits/main"><img src="https://img.shields.io/github/last-commit/YOURHANDLE/awesome-ai-red-team?style=flat-square" alt="Last commit"></a>
</p>

**260+ hand-picked resources across 27 categories.** Curated by **[Rafael Gacek](https://ai.bersec.me)** — offensive-AI / red-team operator. Every link earns its place: best-in-class, current, no SEO filler. Defense shows up only as **bypass targets**.

> ⚠️ **Authorized use only.** Everything here is for red-team engagements, security research, and CTFs you have permission to run.

### Why this list?

Most "AI security" lists are academic paper dumps or vendor brochures. This one is built by an operator, for operators — weighted toward **things you actually run**: scanners, jailbreak frameworks, payload crafters, agentic/MCP exploits, offensive LLMs, and labs. If you attack, break, or defend AI systems, this is the map.

> 🔧 **Setup:** after forking, replace `YOURHANDLE` in the badge URLs above with your GitHub username.

---

## Contents

1. [🎯 Frameworks, Standards & Taxonomies](#-frameworks-standards--taxonomies)
2. [🛠️ LLM Red-Team Tools & Scanners](#️-llm-red-team-tools--scanners)
3. [🦾 AI-Augmented Offense (hack WITH AI)](#-ai-augmented-offense-hack-with-ai)
4. [🧬 Offensive & Uncensored Models](#-offensive--uncensored-models)
5. [💉 Prompt Injection & Jailbreaks](#-prompt-injection--jailbreaks)
6. [🧨 Jailbreak Frameworks & Methods](#-jailbreak-frameworks--methods)
7. [🐍 Payload Obfuscation & Token Smuggling](#-payload-obfuscation--token-smuggling)
8. [🤖 Agentic & MCP Security](#-agentic--mcp-security)
9. [🖥️ Coding-Assistant & Agent Attacks](#️-coding-assistant--agent-attacks)
10. [☁️ Cloud AI Attack & LLMjacking](#️-cloud-ai-attack--llmjacking)
11. [🪱 AI Malware & Self-Propagating](#-ai-malware--self-propagating)
12. [🎭 Deepfake & Voice Offense](#-deepfake--voice-offense)
13. [🖼️ Multimodal / Vision / Audio Attacks](#️-multimodal--vision--audio-attacks)
14. [📚 RAG & Vector DB Security](#-rag--vector-db-security)
15. [🧪 Adversarial ML](#-adversarial-ml-classic-model-attacks)
16. [☠️ Data Poisoning & Backdoors](#️-data-poisoning--backdoors)
17. [🔗 MLSecOps & Model Supply Chain](#-mlsecops--model-supply-chain)
18. [🕹️ Labs, CTFs & Challenges](#️-labs-ctfs--challenges)
19. [📊 Benchmarks & Datasets](#-benchmarks--datasets)
20. [💰 Bug Bounty & Disclosure](#-bug-bounty--disclosure)
21. [📖 Awesome Lists & Curations](#-awesome-lists--curations)
22. [🎓 Courses & Certifications](#-courses--certifications)
23. [📕 Books](#-books)
24. [🧑‍💻 People & Blogs to Follow](#-people--blogs-to-follow)
25. [🗣️ Communities & Conferences](#️-communities--conferences)
26. [📰 Newsletters & Podcasts](#-newsletters--podcasts)
27. [🏢 Vendor & Market Landscape](#-vendor--market-landscape)

---

## 🎯 Frameworks, Standards & Taxonomies

The maps you scope, threat-model, and write reports against.

- **[OWASP Top 10 for LLM Applications (2025)](https://genai.owasp.org/llm-top-10/)** — Definitive risk taxonomy for LLM apps. Baseline for scoping any engagement.
- **[OWASP LLM AI Security & Governance Checklist](https://genai.owasp.org/resource/llm-applications-cybersecurity-and-governance-checklist-english/)** — 13-item action checklist. Great for client-facing framing.
- **[MITRE ATLAS](https://atlas.mitre.org/)** — Adversary TTP matrix for ML/AI (16 tactics, 84+ techniques). The ATT&CK of AI.
- **[Zenity GenAI Attacks Matrix (ttps.ai)](https://ttps.ai/)** — Living matrix of real-world GenAI/agent attack techniques; feeds MITRE ATLAS.
- **[NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)** — Governance framework + GenAI profile (AI 600-1). Compliance language clients speak.
- **[Google SAIF](https://saif.google/)** — Secure AI Framework: design/build/deploy principles + risk self-assessment.
- **[OWASP ML Security Top 10](https://mltop10.info/)** — Classic (non-LLM) ML risks: poisoning, inversion/extraction, adversarial examples.
- **[OWASP AI Exchange](https://owaspai.org/)** — 300+ page living reference mapping AI threats to controls and standards (ISO/IEC, EU AI Act).
- **[CSA MAESTRO](https://cloudsecurityalliance.org/blog/2025/02/06/agentic-ai-threat-modeling-framework-maestro)** — 7-layer threat-modeling method for agentic systems.
- **[MIT AI Risk Repository](https://airisk.mit.edu/)** — 1000+ catalogued AI risks with causal + domain taxonomies.
- **[OWASP AIVSS — AI Vulnerability Scoring System](https://vineethsai.github.io/aivss/)** — Emerging CVSS-equivalent for scoring AI/agentic vulns. Rate findings consistently in reports.
- **[EU AI Act](https://artificialintelligenceact.eu/)** — The regulation reshaping AI risk/compliance in the EU. Know it for client engagements.

## 🛠️ LLM Red-Team Tools & Scanners

The frameworks you actually run against a target.

- **[garak (NVIDIA)](https://github.com/NVIDIA/garak)** — *The* LLM vuln scanner. 120+ probes; broadest automated base-model coverage; now includes agentic probing.
- **[PyRIT (Microsoft)](https://github.com/microsoft/PyRIT)** — Multi-turn orchestrators — Crescendo, TAP, Skeleton Key. *(Repo moved from Azure/PyRIT, archived Mar 2026.)*
- **[Promptfoo](https://github.com/promptfoo/promptfoo)** — Dev-loop red teaming + evals. Auto-generates attack cases; CI/CD regression testing. Ships a Pliny plugin.
- **[DeepTeam](https://github.com/confident-ai/deepteam)** — 50+ vulnerabilities, 20+ research-backed attacks (single & multi-turn). Pairs with DeepEval.
- **[Giskard](https://github.com/Giskard-AI/giskard)** — Open-source LLM & ML testing: injection, harmful output, hallucination, bias.
- **[Spikee (Reversec)](https://github.com/ReversecLabs/spikee)** — Simple Prompt Injection Kit for Evaluation & Exploitation. Modular.
- **[Broken Hill (Bishop Fox)](https://github.com/BishopFox/BrokenHill)** — Productionized GCG attack tool; transferable jailbreak suffixes on a single RTX 4090.
- **[promptmap (utkusen)](https://github.com/utkusen/promptmap)** — Automated injection scanner. White-box & black-box (HTTP endpoint) modes.
- **[Agentic Security (msoedov)](https://github.com/msoedov/agentic_security)** — Open-source agentic LLM vuln scanner: multi-step jailbreaks, multimodal, fuzzing, RL-based probes.
- **[Prompt Fuzzer (ps-fuzz)](https://github.com/prompt-security/ps-fuzz)** — Harden your system prompt: 15 dynamic attacks × 16 providers + playground.
- **[Agentic Radar (SplxAI)](https://github.com/splx-ai/agentic-radar)** — Static scanner for agentic workflows; maps tools/MCP to OWASP risks + adversarial test mode.
- **[FuzzyAI (CyberArk)](https://github.com/cyberark/FuzzyAI)** — Fuzzing framework with 20+ techniques (ASCII smuggling, ManyShot, Crescendo, genetic) across providers.
- **[AI-Infra-Guard (Tencent)](https://github.com/Tencent/AI-Infra-Guard)** — Full-stack AI red-team platform: agent scan, MCP/skills scan, AI-infra vuln scan, web fingerprinting, jailbreak eval. Open source.
- **[Repello ARTEMIS](https://repello.ai/)** — Automated red teaming with 1200+ attack vectors across text/image/audio + agent red teaming (commercial).
- **[Augustus (Praetorian)](https://github.com/praetorian-inc/augustus)** — Go single-binary LLM vuln scanner — 210+ probes / 47 attack categories across 28 providers. Garak-class coverage, way faster.
- **[Redamon](https://github.com/samugit83/redamon)** — Agentic meta-framework: runs garak + PyRIT + Giskard + promptfoo, scores ASR, writes OWASP-LLM/ATLAS-mapped findings.
- **[RAMPART (Microsoft)](https://www.microsoft.com/en-us/security/blog/2026/05/20/introducing-rampart-and-clarity-open-source-tools-to-bring-safety-into-agent-development-workflow/)** — Pytest-native agentic red teaming on PyRIT — cross-prompt-injection tests gated in CI/CD. MIT.
- **[LLMmap — model fingerprinting](https://github.com/pasquini-dario/LLMmap)** — Recon: identify the exact LLM behind an app/endpoint — 42 versions at 95%+ in ~8 queries. Know your target before you swing.
- **[Rigging (Dreadnode)](https://github.com/dreadnode/rigging)** — Lightweight agent + tool-calling harness for orchestrating offensive LLM experiments. Great for custom attack chains.
- **[LLM-itM (LLM-in-the-Middle)](https://github.com/user1342/LLM-itM)** — MitM proxy for OpenAI-compatible APIs — inspect and modify prompts/responses on the wire. Burp for LLM traffic.
- **[Plexiglass](https://github.com/kortex-labs/plexiglass)** — Security toolbox for testing & safeguarding LLMs — adversarial prompts, toxicity, jailbreak checks.
- **[WhistleBlower](https://github.com/Repello-AI/whistleblower)** — Infers a target agent's hidden system prompt from its outputs. System-prompt extraction on tap.

## 🦾 AI-Augmented Offense (hack WITH AI)

The force multiplier. Where offense is heading — and the moat you're building.

- **[XBOW](https://xbow.com/)** — Autonomous pentester that hit **#1 on HackerOne US** (1,000+ valid reports). $237M raised, $1B+ valuation. Proof AI offense is real.
- **[PentestGPT](https://github.com/GreyDGL/PentestGPT)** — LLM-guided pentest framework; multi-model. Web, pwn, crypto, priv-esc, CTF.
- **[CAI — Cybersecurity AI (Alias Robotics)](https://github.com/aliasrobotics/cai)** — Bug-bounty-ready agent framework: agents, tools, handoffs, tracing, HITL. 300+ model backends.
- **[HackingBuddyGPT](https://github.com/ipa-lab/hackingBuddyGPT)** — LLMs that execute shell in a sandbox and decide next move. 83% Linux priv-esc with guidance.
- **[Nebula (BerylliumSec)](https://github.com/berylliumsec/nebula)** — AI pentest assistant in the CLI: recon, notes, vuln analysis with local Llama/Mistral.
- **[Vulnhuntr (Protect AI)](https://github.com/protectai/vulnhuntr)** — Zero-shot vuln discovery: LLM traces full call chains input→sink in Python. Found real 0-days.
- **[Awesome AI Hacking Agents](https://github.com/EvanThomasLuke/Awesome-AI-Hacking-Agents)** — Curated list of autonomous AI hacking agents & frameworks.
- **[Cyber-AutoAgent](https://github.com/westonbrown/Cyber-AutoAgent)** — Autonomous cyber agent (recon→exploit) on open frameworks. Good code to study for building your own.
- **[HexStrike AI](https://github.com/0x4m4/hexstrike-ai)** — MCP server wiring LLMs (Claude/GPT/Copilot) to 150+ security tools for autonomous pentest, vuln discovery, bounty automation. Shipped in Kali.
- **[PentAGI](https://github.com/vxcontrol/pentagi)** — Fully autonomous multi-agent pentest system in Docker sandboxes (14k+ stars).
- **[Strix](https://github.com/usestrix/strix)** — Autonomous agent that simulates a human attacker and proves findings with working PoC exploits.
- **[FuseAI](https://getfuseai.com/)** — Multi-agent AI platform for automated pentest & vuln management. Chains agents across recon→exploit→report.
- **[pentest-ai (0xSteph)](https://github.com/0xsteph/pentest-ai)** — Offensive MCP server: 205 wrapped tools, 17 specialist agents, 60 SPA-aware OWASP-Top-10 probes. CLI + MCP, bring-your-own-LLM.
- **[The AI Offensive Security Boom (70 tools)](https://hadrian.io/blog/the-ai-offensive-security-boom-seventy-tools-in-eighteen-months)** — Landscape survey: 70 offensive-AI tools in 18 months.

## 🧬 Offensive & Uncensored Models

Local, low-refusal firepower. For authorized engagements — run it on your box.

- **[WhiteRabbitNeo](https://huggingface.co/WhiteRabbitNeo)** — Offensive-tuned, low-refusal security LLM (8B/70B, Llama-3.1). Built for red/blue infosec workflows. Your local pair-hacker.
- **[Foundation-Sec-8B (Cisco)](https://huggingface.co/fdtn-ai/Foundation-Sec-8B)** — Cisco's cybersecurity LLM (Llama-3.1, 5.1B sec-tokens). SOTA-for-size on threat-intel. Uncensored variant: `huihui-ai/Foundation-Sec-8B-abliterated`.
- **[huihui_ai — abliterated models (Ollama)](https://ollama.com/huihui_ai)** — Pull-and-run collection of refusal-removed models locally.
- **[Dolphin / uncensored (cognitivecomputations)](https://huggingface.co/cognitivecomputations)** — Long-running uncensored fine-tune line; solid no-refusal base for tooling.

## 💉 Prompt Injection & Jailbreaks

The core offensive discipline. Read the theory, steal the payloads.

- **[Simon Willison — Prompt Injection series](https://simonwillison.net/tags/prompt-injection/)** — Canonical writing on injection & the "lethal trifecta." Start here.
- **[L1B3RT4S (Pliny)](https://github.com/elder-plinius/L1B3RT4S)** — Living collection of working jailbreak prompts per vendor. The reference corpus.
- **[CL4R1T4S (Pliny)](https://github.com/elder-plinius/CL4R1T4S)** — Extracted/leaked system prompts for major AI products. Recon gold.
- **[Prompt Hacking Resources (PromptLabs)](https://github.com/PromptLabs/Prompt-Hacking-Resources)** — Curated hub of red-teaming, jailbreaking, and injection resources.
- **[LLM Hacker's Handbook (Forces Unseen)](https://github.com/forcesunseen/llm-hackers-handbook)** — Practical, non-academic guide: fundamentals, injection, offense, defense.
- **[greshake/llm-security](https://github.com/greshake/llm-security)** — "Not what you've signed up for" — the seminal indirect prompt-injection PoCs.
- **[Learn Prompting — Prompt Hacking](https://learnprompting.org/docs/prompt_hacking/introduction)** — Structured intro to injection/jailbreak/leaking.
- **[Arcanum Prompt Injection Taxonomy](https://github.com/Arcanum-Sec/arc_pi_taxonomy)** — Jason Haddix's structured classification of injection attack types (the `arc_pi_taxonomy` repo).
- **[PIPE — Prompt Injection Primer for Engineers](https://github.com/jthack/PIPE)** — Compact, practical primer on prompt injection for builders and red teamers.
- **[CPH-SEC AI/LLM Red Team Field Manual](https://cph-sec.gitbook.io/ai-llm-red-team-handbook-and-field-manual/part-v-attacks-and-techniques/chapter_14_prompt_injection)** — 46-chapter AI red-team handbook + field manual (GitBook). Ch. 14 is the full direct/indirect prompt-injection playbook.
- **[PayloadsAllTheThings — Prompt Injection](https://github.com/swisskyrepo/PayloadsAllTheThings/tree/master/Prompt%20Injection)** — The classic payload bible now has a prompt-injection section. Starting points + bypasses.
- **[SecLists](https://github.com/danielmiessler/SecLists)** — The tester's wordlist companion — fuzzing payloads to feed your injection/fuzzing harness.
- **[The Big Prompt Library](https://github.com/0xeb/TheBigPromptLibrary)** — Huge collection of system prompts, jailbreaks, and protection prompts across ChatGPT/Copilot/Claude/Gemini. Recon + payload mine.
- **[Ignore Previous Prompt (Perez & Ribeiro)](https://arxiv.org/abs/2211.09527)** — The paper that put "prompt injection" on the map. Foundational reading.
- **[PALLMs — Payloads for Attacking LLMs](https://github.com/mik0w/pallms)** — Ready-to-fire payload collection for LLM attacks. Grab-and-go.
- **[Prompt Injection Cheat Sheet (Seclify)](https://blog.seclify.com/prompt-injection-cheat-sheet/)** — Compact field cheat sheet of injection techniques and manipulations.

## 🧨 Jailbreak Frameworks & Methods

Attack-technique implementations — when a scanner isn't enough and you need the actual method.

- **[EasyJailbreak](https://github.com/EasyJailbreak/EasyJailbreak)** — Unified framework: 11 classic attacks (AutoDAN, PAIR, GPTFuzz, DeepInception…) via Selector/Mutator/Constraint/Evaluator.
- **[GPTFuzz](https://github.com/sherdencooper/GPTFuzz)** — AFL-inspired black-box jailbreak fuzzer; auto-generates jailbreak templates from seeds.
- **[Open-Prompt-Injection](https://github.com/liu00222/Open-Prompt-Injection)** — USENIX Sec'24 benchmark: 5 injection attacks × 10 defenses × 10 LLMs × 7 tasks.
- **[HouYi](https://github.com/LLMSecurity/HouYi)** — Automated black-box prompt-injection framework for LLM-integrated apps.
- **[JailbreakZoo](https://github.com/Allen-piexl/JailbreakZoo)** — Living zoo of jailbreak methods & papers for LLMs and multimodal models.
- **[ArtPrompt (ASCII-art jailbreak)](https://github.com/uw-nsl/ArtPrompt)** — ACL'24 — encode blocked words as ASCII art to slip past alignment. Cheap, black-box.
- **[AutoDAN-Turbo](https://github.com/SaFoLab-WISC/AutoDAN-Turbo)** — ICLR'25 — lifelong agent that self-discovers jailbreak strategies from scratch.
- **[PAIR — Jailbreaking in 20 Queries](https://github.com/patrickrchao/JailbreakingLLMs)** — Attacker-LLM iteratively refines a jailbreak against a black-box target; breaks GPT-4 in <20 queries. The efficient classic.
- **[Best-of-N Jailbreaks](https://arxiv.org/abs/2412.03556)** — Black-box: sample many augmented prompts, keep the ones that slip through. Dead simple, brutally effective across modalities.
- **[Jailbroken: How Does LLM Safety Training Fail?](https://arxiv.org/abs/2307.02483)** — Why aligned models break — competing objectives & mismatched generalization. The mental model behind most jailbreaks.
- **[CipherChat](https://github.com/RobustNLP/CipherChat)** — Jailbreak via ciphers — GPT-4 is "too smart to be safe": encode the chat, bypass the filter.
- **[DeepInception](https://github.com/tmlr-group/DeepInception)** — Nested-scene "hypnosis" jailbreak — wrap the ask in a story-within-a-story to erode refusals.
- **[ReNeLLM — nested jailbreak](https://github.com/NJUNLP/ReNeLLM)** — "Wolf in sheep's clothing": generalized prompt rewriting + scenario nesting. Cheap and effective.

## 🐍 Payload Obfuscation & Token Smuggling

Where nobody's looking. Beat filters that only read plaintext — encode, hide, and smuggle.

- **[P4RS3LT0NGV3 / Parseltongue (Pliny)](https://elder-plinius.github.io/P4RS3LT0NGV3/)** — The payload crafter. Encode/mutate text into leetspeak, base64, runes, invisible Unicode, variation selectors — plus "tokenade" grenades that explode into thousands of tokens.
- **[P4RS3LT0NGV3 — source](https://github.com/elder-plinius/P4RS3LT0NGV3)** — Repo: universal text transformation, encoding/decoding, promptcrafting.
- **[Parseltongue (BASI Labs) — browser extension](https://github.com/BASI-LABS/parseltongue)** — Real-time tokenization viz + text conversion (binary/base64/leetspeak/unicode). Live crafting inside the target UI.
- **[Emoji Smuggler (Paul Butler)](https://emoji.paulbutler.org/)** — Hide arbitrary text inside a single emoji via Unicode variation selectors. Invisible-instruction channel.
- **[OpenAI Tokenizer](https://platform.openai.com/tokenizer)** — See exactly how a payload tokenizes. Essential for building smuggling / token-expansion attacks.
- **[Cryptex OSS](https://github.com/m4xx101/cryptex-oss)** — 159 transforms (ciphers, Unicode tricks, emoji stego, tokenade, bijection, anti-classifier) + 15 red-team labs + one-shot Campaign mode with ASR report. MIT.
- **[Data Exfiltration Attacks (Simon Willison)](https://simonwillison.net/tags/exfiltration-attacks/)** — Curated running log of zero-click exfil via markdown-image rendering + ASCII/Unicode smuggling. The other half of obfuscation: getting data OUT.
- **[Invisible Unicode Tags Playground (jthack)](https://josephthacker.com/invisible_prompt_injection)** — Convert text to invisible Unicode tag characters to smuggle hidden instructions past filters and humans.
- **[ASCII→Unicode Reducer (jthack)](https://josephthacker.com/unicode_reducer)** — Re-encode ASCII as compact Unicode lookalikes to defeat brittle string filters.

## 🤖 Agentic & MCP Security

Where the 2026 attack surface actually lives: tools, memory, MCP, autonomy.

- **[AgentDojo (ETH SPY Lab)](https://github.com/ethz-spylab/agentdojo)** — Dynamic benchmark/environment for injection attacks & defenses on tool-using agents.
- **[Damn Vulnerable MCP Server](https://github.com/harishsg993010/damn-vulnerable-MCP-server)** — Tool poisoning, rug pulls, tool shadowing, indirect injection, excessive permissions.
- **[Damn Vulnerable LLM Agent (Reversec)](https://github.com/ReversecLabs/damn-vulnerable-llm-agent)** — ReAct/LangChain agent for practicing injection on tool-use chains.
- **[Damn Vulnerable AI Agent](https://github.com/opena2a-org/damn-vulnerable-ai-agent)** — Vulnerable agent platform for hands-on testing.
- **[Invariant Labs](https://invariantlabs.ai/)** — Tool-poisoning disclosures, agent guardrails, and MCP security tooling research.
- **[awesome-agent-skills-security](https://github.com/LLMSecurity/awesome-agent-skills-security)** — Curated attacks/defenses/benchmarks for agent tool-use & skill ecosystems.
- **[Damn Vulnerable Email Agent (kyuz0)](https://github.com/kyuz0/damn-vulnerable-email-agent)** — Vulnerable email-handling agent — practice indirect injection via inbound mail.
- **[SuperClaw](https://github.com/SuperagenticAI/superclaw)** — Scenario-driven, behavior-first red teaming for autonomous agents. Generates adversarial scenarios, scores vs security contracts. pip install.
- **[MCP-Scan (Invariant / Snyk)](https://github.com/invariantlabs-ai/mcp-scan)** — Static + dynamic scanner for MCP connections: tool poisoning, cross-origin escalation, rug pulls, toxic flows. The MCP audit standard.
- **[MCP Injection Experiments](https://github.com/invariantlabs-ai/mcp-injection-experiments)** — Working PoCs that exfiltrate SSH keys/config from Claude Desktop & Cursor via tool poisoning. Copy-paste attack lab.
- **[The Lethal Trifecta (Simon Willison)](https://simonwillison.net/series/prompt-injection/)** — Private data + untrusted content + exfiltration = the core agentic exploit class.

## 🖥️ Coding-Assistant & Agent Attacks

Copilots and coding agents run with your privileges — poison the context, own the shell.

- **[Rules File Backdoor (Pillar Security)](https://www.pillar.security/blog/new-vulnerability-in-github-copilot-and-cursor-how-hackers-can-weaponize-code-agents)** — Invisible-Unicode instructions in `.cursorrules` / `copilot-instructions.md` → the AI writes backdoors and hides its own logs.
- **[TrustFall — 1-click RCE (Adversa)](https://adversa.ai/blog/trustfall-coding-agent-security-flaw-rce-claude-cursor-gemini-cli-copilot/)** — Folder-trust abuse: a malicious repo spawns unsandboxed code on Claude Code, Cursor, Gemini CLI, Copilot with one keypress.
- **["Your AI, My Shell"](https://arxiv.org/abs/2509.22040)** — Systematic study of prompt-injection → shell on agentic AI editors. 85%+ success with adaptive attacks.
- **[Prompt Injection on Agentic Coding Assistants](https://arxiv.org/abs/2601.17548)** — Vulnerability analysis across skills, tools, and MCP ecosystems.
- **[CSA — AI Coding Assistants as Attack Surface](https://labs.cloudsecurityalliance.org/research/csa-research-note-ai-coding-assistant-attack-surface-2026040/)** — Practitioner note: code, skills, and secrets as entry points.
- **[Hacking Auto-GPT → Docker escape (RCE)](https://positive.security/blog/auto-gpt-rce)** — Indirect prompt injection into an autonomous agent → arbitrary code exec → container escape. Classic agent-RCE chain.

## ☁️ Cloud AI Attack & LLMjacking

Where AI meets your cloud-security edge. SSRF a model endpoint, steal the token, ride the quota.

- **[HackTricks — Cloud SSRF → metadata creds](https://book.hacktricks.xyz/pentesting-web/ssrf-server-side-request-forgery/cloud-ssrf)** — SSRF an AI web app → hit the metadata service → steal the service-account token. AWS/Azure/GCP.
- **[Unit 42 — Autonomous AI attacks the cloud](https://unit42.paloaltonetworks.com/autonomous-ai-cloud-attacks/)** — Building an autonomous multi-agent cloud-offense system: recon → SSRF → token theft → lateral.
- **[Unit 42 — Attacking Bedrock multi-agent apps](https://unit42.paloaltonetworks.com/amazon-bedrock-multiagent-applications/)** — Abusing Amazon Bedrock multi-agent deployments. Concrete agentic-cloud tradecraft.
- **[Why Attackers Target AWS Bedrock (Vectra)](https://www.vectra.ai/resources/threat-briefing-why-attackers-target-aws-bedrock)** — LLMjacking + Bedrock abuse: stolen creds → invoke hosted models on the victim's bill.

## 🪱 AI Malware & Self-Propagating

Injection as a delivery mechanism. Where offense stops being one-shot and starts to spread.

- **[Morris II — Zero-Click GenAI Worm](https://arxiv.org/abs/2403.02817)** — The seminal AI worm (Cornell Tech): adversarial self-replicating prompts that spread through GenAI email assistants, exfiltrating data with no human click.
- **[The Promptware Kill Chain](https://arxiv.org/abs/2601.09625)** — How prompt injections evolve into multi-step malware delivery. The tradecraft blueprint for weaponizing injection.

## 🎭 Deepfake & Voice Offense

For authorized social-engineering ops — the media layer of the kill chain.

- **[DeepFaceLab](https://github.com/iperov/DeepFaceLab)** — The de-facto open-source face-swap/deepfake toolkit. For authorized social-engineering / red-team media ops.
- **[RVC — Voice Conversion](https://github.com/RVC-Project/Retrieval-based-Voice-Conversion-WebUI)** — Retrieval-based voice cloning/conversion. Clone a voice from seconds of audio for authorized vishing simulations.
- **[Bishop Fox — Deepfakes in Red Teaming](https://bishopfox.com/resources/attacking-defending-deepfakes-virtual-session)** — Real-world lessons on operationalizing deepfakes in red-team engagements.

## 🖼️ Multimodal / Vision / Audio Attacks

Images, audio, and video are the softest injection channel. Everyone tests text; test the rest.

- **[JailBreakV-28K](https://github.com/EddyLuo1232/JailBreakV_28K)** — 28k text-image jailbreak pairs; tests transferability of LLM jailbreaks to MLLMs. Go-to benchmark.
- **[MM-SafetyBench](https://github.com/isXinLiu/MM-SafetyBench)** — ECCV'24 image-based jailbreak benchmark: 13 categories, 1,680 samples.
- **[Awesome-MLLM-Safety](https://github.com/isXinLiu/Awesome-MLLM-Safety)** — Curated survey of multimodal LLM safety attacks & defenses.
- **[OmniSafeBench-MM](https://arxiv.org/abs/2512.06589)** — Unified multimodal attack-defense toolbox: 13 attacks, 15 defenses, 9 risk domains.
- **[Adversarial Attacks on MLLMs — Survey](https://arxiv.org/abs/2603.27918)** — Comprehensive 2026 survey of the multimodal attack surface.
- **[OpenRT](https://github.com/AI45Lab/OpenRT)** — Open-source red-teaming framework for multimodal LLMs — 42+ attack methods (ArtPrompt, Past Tense, LAA, imperceptible jailbreak).
- **[Image Hijacks](https://github.com/euanong/image-hijacks)** — Adversarial images that control a VLM's behavior at runtime — steer outputs with a crafted picture.

## 📚 RAG & Vector DB Security

RAG is the enterprise default — and its knowledge base is an injection sink.

- **[PoisonedRAG](https://github.com/sleeepeer/PoisonedRAG)** — USENIX Sec'25 — first knowledge-corruption attack on RAG. 90% success with 5 poisoned docs.
- **[ConfusedPilot](https://arxiv.org/abs/2408.04870)** — Confused-deputy / access-control bypass in RAG (demoed on M365 Copilot).
- **[RAG Poisoning POC (Prompt Security)](https://github.com/prompt-security/RAG_Poisoning_POC)** — Stealthy injection/poisoning via vector-DB embeddings.
- **[Awesome-Rag-Attacks](https://github.com/jawadhussein462/Awesome-Rag-Attacks)** — Framework + curated list for implementing/evaluating RAG poisoning.
- **[RAG Data Poisoning — Promptfoo](https://www.promptfoo.dev/blog/rag-poisoning/)** — Clear practitioner explainer of RAG poisoning mechanics and testing.

## 🧪 Adversarial ML (classic model attacks)

Evasion, poisoning, extraction, inversion — the pre-LLM foundations that still bite.

- **[Adversarial Robustness Toolbox (ART)](https://github.com/Trusted-AI/adversarial-robustness-toolbox)** — Most complete adversarial ML library: evasion, poisoning, extraction, inference.
- **[Counterfit (Microsoft)](https://github.com/Azure/counterfit)** — CLI to orchestrate attacks against ML models; wraps ART/TextAttack.
- **[TextAttack](https://github.com/QData/TextAttack)** — NLP adversarial attacks, augmentation, adversarial training.
- **[Foolbox](https://github.com/bethgelab/foolbox)** — Fast evasion attacks (FGSM/PGD/C&W) across PyTorch/TF/JAX.
- **[CleverHans](https://github.com/cleverhans-lab/cleverhans)** — OG adversarial-examples library; benchmarking attacks and defenses.
- **[GCG — Universal & Transferable Attacks](https://github.com/llm-attacks/llm-attacks)** — Reference implementation of the transferable adversarial suffix attack + AdvBench.
- **[Extracting Training Data from LLMs (Carlini et al.)](https://arxiv.org/abs/2012.07805)** — The seminal training-data extraction attack — memorization = leakage. Foundation of model privacy attacks.
- **[vec2text — Language Model Inversion](https://github.com/jxmorris12/vec2text)** — Reconstruct input text from embeddings. Invert the model; leak what it saw.

## ☠️ Data Poisoning & Backdoors

Attack the model before it's a model. Training-time is the highest-leverage, lowest-noise vector.

- **[BackdoorBench](https://github.com/SCLBD/BackdoorBench)** — Comprehensive backdoor-learning benchmark: attacks + defenses, 8,000+ trials.
- **[TrojanZoo](https://github.com/ain-soph/trojanzoo)** — Unified platform for evaluating neural backdoor attacks/defenses end-to-end.
- **[TrojAI (NIST)](https://github.com/usnistgov/trojai-literature)** — NIST's Trojan-in-AI program + curated literature.
- **[Backdoor Learning Resources](https://github.com/THUYimingLi/backdoor-learning-resources)** — Massive curated bibliography of backdoor attack/defense papers & code.
- **[Stealthy Pickle Model Poisoning](https://arxiv.org/abs/2508.19774)** — 2025 research making pickle-based supply-chain poisoning evade scanners again.
- **[PoisonGPT (Mithril Security)](https://blog.mithrilsecurity.io/poisongpt-how-we-hid-a-lobotomized-llm-on-hugging-face-to-spread-fake-news/)** — Surgically edited an LLM to spread targeted fake news, then reuploaded it to Hugging Face. The model supply-chain wake-up call.
- **[Virtual Prompt Injection](https://github.com/wegodev2/virtual-prompt-injection)** — Backdoor instruction-tuned models so a trigger topic silently steers outputs. Poison at fine-tune time.
- **[Fine-Tuning Breaks Safety](https://github.com/LLM-Tuning-Safety/LLMs-Finetuning-Safety)** — A few adversarial (or even benign) fine-tune steps strip alignment. Repo + HEx-PHI dataset.

## 🔗 MLSecOps & Model Supply Chain

Malicious weights, poisoned pickles, and the guardrails you'll be measured against.

- **[ModelScan (Protect AI)](https://github.com/protectai/modelscan)** — Scans models across 35+ formats for serialization attacks & code injection before load.
- **[picklescan](https://github.com/mmaitre314/picklescan)** — Detects malicious pickles; used across the HF/PyPI ecosystem.
- **[Fickling (Trail of Bits)](https://github.com/trailofbits/fickling)** — Decompile/analyze/inject Python pickles; craft and detect malicious model files.
- **[NeMo Guardrails (NVIDIA)](https://github.com/NVIDIA/NeMo-Guardrails)** — *Bypass target.* Programmable guardrails. Know it to beat it.
- **[LLM Guard (Protect AI)](https://github.com/protectai/llm-guard)** — *Bypass target.* Input/output scanners (injection, PII, toxicity).
- **[Rebuff](https://github.com/protectai/rebuff)** — *Bypass target.* Multi-layer prompt-injection detector.
- **[Vigil](https://github.com/deadbits/vigil-llm)** — *Bypass target.* Injection/jailbreak detection scanners.
- **[Guardrails AI](https://github.com/guardrails-ai/guardrails)** — *Bypass target.* Composable validators (schema, regex, PII, toxicity) with re-ask loops.
- **[Anthropic Constitutional Classifiers](https://www.anthropic.com/news/constitutional-classifiers)** — *Bypass target.* Rule-based alignment classifiers (Anthropic's jailbreak defense). Study the approach to route around it.
- **[Meta Prompt Guard 86M](https://huggingface.co/meta-llama/Prompt-Guard-86M)** — *Bypass target.* Small classifier for detecting injection/jailbreak inputs. Fingerprint it, then evade.
- **[Circuit Breakers (Gray Swan)](https://github.com/GraySwanAI/circuit-breakers)** — *Bypass target.* Representation-engineering defense that "short-circuits" harmful generations. Study it to beat the newest guardrail class.

## 🕹️ Labs, CTFs & Challenges

Hands-on reps. Where you actually build the skill.

- **[Gandalf (Lakera)](https://gandalf.lakera.ai/)** — The gateway drug. New Agent Breaker mode = 10 mock agentic apps.
- **[Crucible (Dreadnode)](https://crucible.dreadnode.io/)** — 70+ hosted LLM/ML challenges; weekly drops. Backed by AIRTBench.
- **[HackAPrompt](https://www.hackaprompt.com/)** — Largest prompt-injection competition; huge public attack dataset.
- **[PortSwigger — Web LLM Attacks](https://portswigger.net/web-security/llm-attacks)** — Free labs: API abuse, excessive agency, indirect injection, insecure output handling.
- **[Prompt Airlines (Wiz)](https://promptairlines.com/)** — 5-stage CTF: manipulate an airline chatbot for a free ticket.
- **[Doublespeak (Forces Unseen)](https://doublespeak.chat/)** — Text game on LLM sandboxing: extract the bot's hidden name.
- **[Arcanum AI Security Lab Hub](https://arcanum-sec.github.io/ai-sec-resources/)** — Jason Haddix's directory: 23 labs, competitions, bounties, tools.
- **[AIGoat — vulnerable LLM playground](https://github.com/AISecurityConsortium/AIGoat)** — Vulnerable AI e-commerce app covering the full OWASP LLM Top 10. Runs locally.
- **[ai-goat (dhammon)](https://github.com/dhammon/ai-goat)** — Local vulnerable-LLM CTF. No signups, no cloud fees.
- **[OWASP Vulnerable Web Apps Directory](https://vwad.owasp.org/)** — Registry of legal vulnerable targets — now indexes AI/LLM apps.
- **[RedTeam Arena](https://redarena.ai/)** — Live, competitive jailbreak arena — speed-run prompts against models on a public leaderboard.
- **[LLM Vulnerable Recruitment App (Reversec)](https://github.com/ReversecLabs/llm-vulnerable-recruitment-app)** — Vulnerable hiring assistant — practice injection/data-exfil in a realistic business app.
- **[Microsoft AI Red Teaming Playground Labs](https://github.com/microsoft/AI-Red-Teaming-Playground-Labs)** — Official MS labs from the Black Hat "AI Red Teaming in Practice" course; several automated with PyRIT notebooks. Infra included.
- **[Folly](https://github.com/user1342/Folly)** — Open-source prompt-injection & jailbreak playground for hands-on experimentation.
- **[Damn Vulnerable Math LLM](https://github.com/user1342/DamnVulnerableMathLLM)** — Intentionally vulnerable maths LLM app — practice injection and logic exploits.
- **[Damn Vulnerable Shopping LLM](https://github.com/user1342/DamnVulnerableShoppingLLM)** — Vulnerable shopping assistant — test data leakage and unsafe tool use.
- **[MyLLM Bank (WithSecure)](https://myllmbank.com/)** — Multi-LLM banking CTF — learn real-world prompt-injection chains.
- **[MyLLM Doctor (WithSecure)](https://myllmdoc.com/)** — Medical chatbot challenge — multi-stage injection and policy evasion.

## 📊 Benchmarks & Datasets

Standardized attacks and behaviors — for measuring, comparing, and building your own harness.

- **[HarmBench](https://github.com/centerforaisafety/HarmBench)** — Standardized automated red-teaming eval (attacks + defenses), textual & multimodal.
- **[JailbreakBench](https://github.com/JailbreakBench/jailbreakbench)** — Open robustness benchmark; JBB-Behaviors (200 behaviors), leaderboard.
- **[AgentHarm](https://arxiv.org/abs/2410.09024)** — 110 malicious agent tasks (440 augmented) across 11 harm categories.
- **[Purple Llama / CyberSecEval (Meta)](https://github.com/meta-llama/PurpleLlama)** — Security & safety evals + Llama Guard.
- **[In-The-Wild Jailbreak Prompts (verazuo)](https://github.com/verazuo/jailbreak_llms)** — CCS'24 dataset: 15,140 real prompts (1,405 jailbreaks). Gold corpus.
- **[TrustAIRLab Jailbreak Prompts (HF)](https://huggingface.co/datasets/TrustAIRLab/in-the-wild-jailbreak-prompts)** — Same dataset, HF-ready, with ForbiddenQuestionSet.
- **[BIPIA (Microsoft)](https://github.com/microsoft/BIPIA)** — Benchmark for indirect prompt-injection attacks & defenses. Measure your indirect-injection coverage.
- **[jailbreak-evaluation](https://github.com/controllability/jailbreak-evaluation)** — Python package to score jailbreak success rigorously. Stop eyeballing ASR.

## 💰 Bug Bounty & Disclosure

Turn skill into reputation and income.

- **[huntr (Protect AI)](https://huntr.com/)** — The AI/ML bug bounty platform. CVE-issuing. Best entry point.
- **[Mozilla 0din](https://0din.ai/)** — GenAI-native bounty (injection, guardrail bypass, model vulns). $500–$15k+.
- **[Gray Swan Arena](https://www.grayswan.ai/)** — Paid jailbreak/agent competitions — and a talent funnel to top labs.
- **[AI Vulnerability Database (AVID)](https://avidml.org/)** — Open knowledge base of AI/ML failure modes & vulns.
- **[AI Incident Database](https://incidentdatabase.ai/)** — Real-world AI harm/incident reports; recon for impact narratives.

> Also worth programs at OpenAI, Anthropic, Google, Microsoft, and xAI/Grok — most now scope AI-specific findings.

## 📖 Awesome Lists & Curations

Go deep. Where the next technique comes from.

- **[Awesome-LLM-Red-Teaming](https://github.com/user1342/Awesome-LLM-Red-Teaming)** — Curated red-teaming training, tools, and resources.
- **[Awesome-LLMSecOps](https://github.com/wearetyomsmnv/Awesome-LLMSecOps)** — LLM / Agentic / Security / Operations in one well-illustrated repo.
- **[Awesome-AI-Security (Tal Eliyahu)](https://github.com/TalEliyahu/Awesome-AI-Security)** — Broad, actively-maintained AI security index.
- **[Arcanum ai-sec-resources](https://github.com/Arcanum-Sec/ai-sec-resources)** — Jason Haddix's hub: labs, competitions, bounties, tools, taxonomies.
- **[OpenRedTeaming (Libr-AI)](https://github.com/Libr-AI/OpenRedTeaming)** — 30+ automated red-teaming methods + papers.
- **[Offensive AI Compilation (jiep)](https://github.com/jiep/offensive-ai-compilation)** — Broad "offensive AI" resource list — attacks on and with AI.
- **[awesome-ai-security (ottosulin)](https://github.com/ottosulin/awesome-ai-security)** — General AI security reading list.
- **[LLM Security Guide (requie)](https://github.com/requie/LLMSecurityGuide)** — OWASP GenAI-mapped reference.
- **[awesome-cybersecurity-agentic-ai](https://github.com/raphabot/awesome-cybersecurity-agentic-ai)** — Curated agentic-AI security resources.
- **[Awesome GPT Super Prompting](https://github.com/CyberAlbSecOP/Awesome_GPT_Super_Prompting)** — Jailbreaks, prompt leaks, injection, super prompts, adversarial ML — a dense prompt-hacking corpus.
- **[Awesome-LLM-Fingerprinting](https://github.com/shaoshuo-ss/Awesome-LLM-Fingerprinting)** — Paper list for LLM fingerprinting/copyright auditing — the recon-side reading.
- **[awesome-llm-security (corca-ai)](https://github.com/corca-ai/awesome-llm-security)** — One of the most-referenced LLM security lists — tools, papers, articles across attack & defense.
- **[Awesome-LM-SSP](https://github.com/ThuCCSLab/Awesome-LM-SSP)** — Comprehensive LM Safety/Security/Privacy reading list from Tsinghua CCSLab.
- **[Awesome-LLM-Safety](https://github.com/ydyjya/Awesome-LLM-Safety)** — Date-sorted safety/security/privacy/jailbreak papers + talks; constantly backfilled.
- **[Awesome LLM Harmful Fine-Tuning](https://github.com/git-disl/awesome_LLM-harmful-fine-tuning-papers)** — Niche but sharp: papers on breaking alignment via fine-tuning — the fine-tuning attack surface.
- **[GCG paper — Universal & Transferable Attacks](https://llm-attacks.org/)** — Foundational jailbreak research.

## 🎓 Courses & Certifications

Structured skill + credentials that price your rate.

- **[OffSec OSAI (AI-300)](https://www.offsec.com/courses/ai-300/)** — Advanced AI Red Teaming. 24-hour practical exam → OSAI cert. LLM/RAG/multi-agent + AI-in-cloud exploitation. Assumes OSCP-level skills.
- **[EC-Council COASP](https://www.eccouncil.org/ai-courses/certified-offensive-ai-security-professional-coasp/)** — Pure offensive AI red-teaming cert.
- **[Practical DevSecOps CAISP](https://www.practical-devsecops.com/certified-ai-security-professional/)** — 30+ labs on LLM vulns, threat modeling, supply chain. $999.
- **[SANS SEC545 — GenAI & LLM App Security](https://www.sans.org/cyber-security-courses/genai-llm-application-security-5day)** — 5-day: threat-modeling GenAI, RAG/vector defense, injection, MLOps hardening.
- **[Lakera AI Security Guides](https://www.lakera.ai/ai-security-guides)** — Free, high-quality guides + Gandalf.
- **[Learn Prompting](https://learnprompting.org/)** — Free docs + the org behind HackAPrompt.
- **[Attacking AI — Arcanum (Jason Haddix)](https://www.arcanum-sec.com/training/attacking-ai)** — Offensive-first AI hacking course from a bug-bounty legend. The practitioner pick.
- **[Karpathy — Deep Dive into LLMs](https://youtube.com/watch?v=7xTGNNLPyMI)** — Free 3.5h masterclass on how LLMs actually work. Nail internals → smuggle better.
- **[HTB AI Red Teamer Path (+ COAE cert)](https://academy.hackthebox.com/path/preview/ai-red-teamer)** — Hack The Box × Google job-role path: injection, model privacy, adversarial AI, supply chain. Capstone = HTB Certified Offensive AI Expert (COAE). Hands-on, SAIF-aligned.
- **[Red Teaming LLM Applications (DeepLearning.AI × Giskard)](https://www.deeplearning.ai/courses/red-teaming-llm-applications)** — Free short course (Andrew Ng + Giskard): manual + automated LLM red teaming, injection, at-scale. Best quick on-ramp.
- **[GenAI Security Training (schwartz1375)](https://github.com/schwartz1375/genai-security-training)** — 8 modules / 40 notebooks: injection, evasion, poisoning, ART — hands-on offensive AI curriculum.

## 📕 Books

- **[The Developer's Playbook for LLM Security — Steve Wilson](https://www.oreilly.com/library/view/the-developers-playbook/9781098162191/)** — From the OWASP LLM Top 10 lead. The practical LLM security bible.
- **[Generative AI Security: Theories & Practices — Ken Huang et al.](https://www.amazon.com/Generative-AI-Security-Theories-Practices/dp/3031542517)** — Comprehensive GenAI security across the stack.
- **[AI-Native LLM Security — Malik, Huang, Dawson](https://www.amazon.com/Native-LLM-Security-comprehensive-applications/dp/1836203756)** — Threats, defenses, best practices; strong on adversarial AI.
- **[Securing AI Agents — Ken Huang, Chris Hughes](https://www.amazon.com/Securing-Agents-Foundations-Frameworks-Real-World/dp/3032021294)** — Foundations + frameworks for agentic deployments.

> Also recommended: *Adversarial AI Attacks, Mitigations, and Defense Strategies* — John Sotiropoulos (Packt) — the most red-team-relevant MLSecOps book.

## 🧑‍💻 People & Blogs to Follow

Follow the operators, not the vendors.

- **[Johann Rehberger — Embrace The Red](https://embracethered.com/)** — (@wunderwuzzi23) The most important practical AI exploit researcher working today.
- **[Simon Willison](https://simonwillison.net/)** — Coined "lethal trifecta"; the clearest thinking on injection & LLM app risk.
- **[Jason Haddix — Arcanum](https://www.arcanum-sec.com/)** — Executive Offense; AI hacking labs, taxonomies, offensive training from a bug-bounty legend.
- **[Pliny the Liberator](https://github.com/elder-plinius)** — Jailbreak virtuoso; maintains L1B3RT4S / CL4R1T4S / P4RS3LT0NGV3.
- **[Adversa AI](https://adversa.ai/blog/)** — Adversarial ML & jailbreak research; "Towards Trusted AI."
- **[Lakera Blog](https://www.lakera.ai/blog)** — Gandalf makers; injection research & datasets.
- **[Trail of Bits](https://blog.trailofbits.com/)** — ML supply-chain & pickle exploitation; deep security engineering.
- **[NVIDIA Developer — AI Red Team](https://developer.nvidia.com/blog)** — The garak team; practical AI red-team writeups.
- **[Microsoft AI Red Team](https://learn.microsoft.com/en-us/security/ai-red-team/)** — The PyRIT team; lessons from red-teaming 100+ GenAI products.
- **[WithSecure Labs / Reversec](https://labs.withsecure.com/)** — Deep LLM-agent injection research (browser agents, Gemini, ReAct forging). Reversec = the spikee/DVLA crew.
- **[Haize Labs](https://haizelabs.com/)** — AI red-teaming research lab — automated "haizing"/jailbreak research (ACG accelerated GCG, red-team evals).
- **[Lilian Weng — Adversarial Attacks on LLMs](https://lilianweng.github.io/posts/2023-10-25-adv-attack-llm/)** — The canonical deep-dive explainer on adversarial attacks against LLMs. Read it twice.
- **[Daniel Miessler — AI Attack Surface Map](https://danielmiessler.com/p/the-ai-attack-surface-map-v1-0/)** — The canonical one-page map of the AI attack surface. Great for scoping and client decks.
- **[llmsecurity.net (@llm_sec)](https://llmsecurity.net/)** — Dedicated LLM-security blog + curation. Follow @llm_sec.
- **[Kai Greshake](https://kai-greshake.de/)** — Indirect-prompt-injection pioneer's blog — where a lot of this started.

## 🗣️ Communities & Conferences

Stay current. The field moves weekly.

- **[OWASP GenAI Security Project](https://genai.owasp.org/)** — The center of gravity. Join the Slack and working groups.
- **[DEF CON AI Village](https://aivillage.org/)** — The community + Generative Red Team (GRT) events at DEF CON.
- **[MLSecOps Community](https://community.mlsecops.com/)** — Slack + resources for ML/AI security practitioners.
- **[Coalition for Secure AI (CoSAI)](https://www.coalitionforsecureai.org/)** — Industry coalition + open workstreams.
- **[CAMLIS](https://www.camlis.org/)** — Conference on Applied ML in Information Security. Practitioner-focused, red-team heavy.
- **[IEEE SaTML](https://satml.org/)** — Secure and Trustworthy ML — top academic venue for attacks/defenses.
- **[r/ChatGPTJailbreak](https://www.reddit.com/r/ChatGPTJailbreak/)** — The public jailbreak lab — fresh working jailbreaks and techniques daily.

## 📰 Newsletters & Podcasts

- **[The MLSecOps Podcast](https://mlsecops.com/podcast)** — Interviews across AI red teaming, model security, supply chain.
- **[AI Security Newsletter (Tal Eliyahu)](https://github.com/TalEliyahu/AI-Security-Newsletter)** — Monthly digest: research, reports, tools, events (AISecHub).
- **[The Agentic Security Newsletter](https://agenticsecurity.substack.com/)** — Weekly on agent/multi-agent offense & defense.
- **[Executive Offense (Arcanum)](https://executiveoffense.beehiiv.com/)** — Jason Haddix's newsletter — practical offensive AI & red-team ops.
- **[AI Safety Takes (Daniel Paleka)](https://newsletter.danielpaleka.com/)** — Sharp monthly digest of AI safety/security research.
- **[Hackstery](https://hackstery.com/)** — Offensive-AI blog + newsletter; hands-on LLM hacking writeups.

## 🏢 Vendor & Market Landscape

Competitive intel for building your own company — know the map before you plant a flag.

- **[Protect AI (Palo Alto Networks)](https://protectai.com/)** — huntr, ModelScan, Guardian. Model supply chain + AI bounty.
- **[HiddenLayer](https://hiddenlayer.com/)** — Model scanning, runtime detection, adversarial red teaming.
- **[Lakera](https://www.lakera.ai/)** — Runtime guardrails + Gandalf. AI-native security, strong research brand.
- **[Mindgard](https://mindgard.ai/)** — Continuous automated AI red teaming (academic roots).
- **[SplxAI](https://splx.ai/)** — AI red teaming + governance; makers of Agentic Radar.
- **[Prompt Security (SentinelOne)](https://www.prompt.security/)** — GenAI runtime security & posture; acquired by SentinelOne.
- **[Lasso Security](https://www.lasso.security/)** — Enterprise GenAI visibility, data protection, runtime controls.
- **[Aim Security (Cato Networks)](https://www.aim.security/)** — AI agent runtime security & posture; acquired by Cato.
- **[Knostic](https://www.knostic.ai/)** — Need-to-know access controls at the AI layer; stops copilot oversharing.
- **[Straiker](https://www.straiker.ai/)** — AI-native runtime security for embedded & shadow AI.
- **[Zenity](https://zenity.io/)** — Agentic AI security for copilots/low-code agents; makers of the GenAI Attacks Matrix.
- **[Cisco AI Defense](https://www.cisco.com/site/us/en/products/security/ai-defense/index.html)** — Enterprise AI security (incl. Robust Intelligence tech).
- **[Adversa AI](https://adversa.ai/)** — AI red teaming + secure-AI advisory; prolific research.
- **[AI Security Startups Watchlist (Top 30)](https://medium.com/ai-security-hub/ai-security-startups-watchlist-top-30-2025-5a95471bbacc)** — Tal Eliyahu's market map. Intel for positioning your own company.

---

## Contributing

Pull requests welcome — this is a living list. **Rotate, re-angle, never stop.**

- One resource per line, in the right category, matching the format: `**[Name](url)** — one-line, operator-voice reason *why it matters*.`
- **Best-in-class only.** If it's a paper, it must be foundational or introduce a technique people actually use. No SEO blogspam, no dead/archived repos.
- Prefer the **canonical source URL** (official repo over a mirror; project page over a news article).
- Keep defenses in the relevant section tagged **_bypass target_** — this is an offense-first list.

See [CONTRIBUTING.md](CONTRIBUTING.md) for the full checklist.

## License

[MIT](LICENSE) © [Rafael Gacek](https://ai.bersec.me) — do whatever, attribution appreciated.

<sub>Curated at <a href="https://ai.bersec.me">ai.bersec.me</a> · also lives as a start.me board.</sub>
