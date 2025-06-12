passive_index.md

A living, project-aware, holistically annotated map of the repository’s documentation and resource tree.

Purpose: Efficiently bridge high-level project goals and needs (minimal, moldable, self-reflexive Nix/AI environment) with the right resources, without getting lost in the forest of files.

Legend:
	•	🟢 CORE: Crucial for our workflow or understanding.
	•	🟡 PERIPHERAL: Useful reference, but not essential.
	•	🟠 CAUTION: Easy to get lost, outdated, or less relevant; read with care.
	•	⚠️ TRAP/WARNING: Often mistaken, distracts, or context risk—check meta annotation!
	•	(Meta notes in italics.)

This index is maintained for both human and AI navigation. When in doubt, check with AI or revisit this file for orientation.

⸻

Root
	•	AI-prompt: Principles (HOW, Efficacity) 🟢
Living record of project principles—crucial for maintaining alignment, transparency, and AI/human self-reflexivity.
Use to calibrate AI and yourself to core values and workflow philosophy before diving into technical docs.
	•	My Computer Specifications 🟡
Reference hardware/environment info—can clarify why some configs/docs don’t “fit.” Only relevant for troubleshooting, sharing context with AI, or debugging environment-specific issues.
	•	README 🟡
General orientation. If well-populated, read first for project overview. If empty or minimal, skip and rely on this index.
	•	temporal_narrative.md 🟡
Auxiliary project meta-narrative and orientation tool. Use for reflecting on project evolution, especially when time/context is ambiguous.
	•	transcending_traps_of_the_project.md 🟢
Meta-compass for surfacing, reflecting on, and transcending both technical and meta/cognitive traps. Consult for process guidance, not as rigid law.
	•	understanding_the_documentation_for_this_project.md 🟢
Project-centric synthesis distilling the paradigms, teachings, and practical affordances of major documentation sources. Not a substitute for the docs—use as a compass for holistic orientation and meta-awareness.

⸻

NIX OS/

Meta: Centralized Nix/NixOS learning and reference.
Begin here for high-level system understanding—but beware: many sections are deep or reference-heavy, so use this index to sort what’s relevant to your current stage/needs.

NixPills/ 🟢 CORE

Deep tutorial—best resource for moving from “basic user” to “competent Nix architect.”
Recommended for building the mental models needed for minimal, adaptive, declarative systems. Beware of technical depth—pace yourself, and don’t get bogged down if not every chapter is relevant yet!
	•	00-preface.md – (Sets intent and learning strategy. Good orientation, read if unsure where to start.)
	•	01-why-you-should-give-it-a-try.md – (Motivation, “what Nix is good for”—helpful if you’re still skeptical or need to align purpose.)
	•	02-install-on-your-running-system.md – 🟠
Practical, but may be dated or not fit your minimal/context-unique setup—always double-check before running commands.
	•	03-enter-environment.md – 🟢
Crucial for sandboxing/isolating workflows—the core of safe, portable, reproducible hacking.
	•	04-basics-of-language.md – 🟢
Learn Nix language syntax and semantics—read if writing or editing any Nix expression, or debugging mysterious config failures.
	•	05-functions-and-imports.md – 🟢
Understand modularity/reusability in Nix. Required for meta-programmable configs.
	•	06-20-*.md –
Each covers an important build, package, or system management topic.
Pick what matches your current challenge—don’t try to “read it all” at once.
	•	SUMMARY.md –
Navigation aid. Use to jump to topics or as a sanity check for coverage.

NixOS Manual/ 🟢 CORE

Official (and semi-official) NixOS manual—your primary resource for nearly all system-level tasks, troubleshooting, and best practices.
If lost or stuck with NixOS, start here or search this first.
	•	manual.md – 🟢
Central reference—always check here for system questions before deep-diving web or forums.
	•	Cheatsheet - NixOS Wiki.md – 🟡
Quick, sometimes out-of-date but good for fast reference—don’t rely exclusively if details matter.
	•	Unofficial nixos cheatsheet.md – 🟡
Alternative cheatsheet—use for a different “voice” or where official docs are unclear.
	•	contributing-to-this-manual.chapter.md – 🟠
Mainly for those wanting to contribute to docs, not for core learning.
	•	nixos-options.md – 🟢
Reference for system configuration options—scan when tuning/tweaking system setup.
	•	preface.md –
Meta-orientation, may clarify manual’s purpose or audience.
	•	README.md, default.nix, shell.nix, common.nix – 🟠
Mostly internal or technical scaffolding; rarely needed unless hacking the manual itself or contributing upstream.

Nix.dev/ 🟡 PERIPHERAL

Official “meta site” for Nix learning.
Useful for initial orientation and links out to deeper resources.
Often, you’ll be bounced to external docs—use for broad orientation, not deep dives.
	•	index.md –
Table of contents or top-level entry point.
	•	install-nix.md – 🟢
Current official instructions for installing Nix—use this over random blog posts or outdated forum advice.
	•	recommended-reading.md – 🟡
Good overview for “where to start” if totally new or overwhelmed by doc sprawl.
	•	conf.py, robots.txt – 🟠
Technical/config files—ignore unless working on doc site infrastructure.

NixOS and Flakes (book)/ 🟡

An evolving, book-length guide to using NixOS and Flakes.
More in-depth than most docs, but potentially overwhelming or opinionated—use for advanced learning, not as first steps.
	•	index.md, preface.md –
Start here for a sense of what’s in scope.
	•	(all chapters) –
Pick by topic of current challenge. Flakes are an “advanced” Nix feature; skip unless aiming for bleeding-edge workflow or reproducibility.

NixPkgs/ 🟡 PERIPHERAL

Reference for the Nix package collection.
Essential if you plan to write or heavily modify packages, less critical for just configuring your system.
Some sections are deep internals—beware rabbit holes!
	•	functions.md, stdenv.md – 🟠 ⚠️
Read only if writing/maintaining packages. Deep, not required for normal system config—easy to lose context here.
	•	manual.md.in, build-helpers.md, development.md, contributing.md, … – 🟡
Scan as needed, but keep project needs in mind; these are more for package contributors.
	•	README.md, shell.nix, lib.md –
Mostly for those hacking or extending Nixpkgs itself.

nixacademy cheatsheet (unofficial).pdf – 🟡

Fast, practical reference—good for command lookup, but beware of drift/outdated advice. Double-check with official docs for critical tasks.

⸻

Aider.chat (PairProgrammingWithLLM)/ 🟢

Meta: Central toolkit for dialogical/AI-augmented programming and configuration.
Aider is both an AI pair-programmer and a living demonstration of agentic, co-evolving workflows—directly aligned with our aim for moldable, reflexive, and minimal computing.
Read to: adapt AI workflows, prototype config/code, and avoid “black-box” habits with LLMs.

config/ 🟢

Core settings and behaviors for Aider itself—change these to “bend” Aider to fit your workflows, privacy, and minimalism principles.
Misconfigurations here can completely change how AI behaves—consult the meta annotations before editing!
	•	adv-model-settings.md –
Advanced LLM parameters (temperature, system prompts, response length, etc).
🟠 CAUTION: Tweaking without context can make LLM less predictable or less aligned with your intentions—edit only with clear goal.
	•	aider_conf.md –
Primary config file—foundation for Aider’s operation.
🟢 CORE: If you need to make global changes or debug strange behaviors, start here.
	•	api-keys.md –
Managing and securing API keys for LLM providers.
🟠 CAUTION: Never share or check in this file. Essential for LLM access, but security risk if mishandled.
	•	dotenv.md –
How to set and manage environment variables for Aider.
🟡 Useful for stateless/minimal environments—often easier than editing config files directly.
	•	editor.md –
Settings for integrating Aider with code editors (VSCode, vim, etc).
🟡 Edit if Aider’s not connecting to your preferred environment.
	•	model-aliases.md –
Custom model names for fast switching between LLMs.
🟡 Peripheral—only edit if juggling multiple models or providers.
	•	options.md –
All tweakable Aider settings, described.
🟡 Good for custom workflows, but can be overwhelming—read with a clear intention!
	•	reasoning.md –
Notes on Aider’s “reasoning” mechanics (prompt design, context management).
🟢 If Aider’s responses seem “dumb” or context-blind, check here.

install/ 🟡

Install guides for various environments (Codespaces, Docker, Replit).
🟢 Use if you want fast, isolated, or reproducible setups for Aider.
🟡 Ignore if Aider is already working or you’re not changing environments.
	•	codespaces.md –
Install in GitHub Codespaces (cloud-based dev).
	•	docker.md –
Containerized install—most “portable/reproducible” method.
🟠 CAUTION: May introduce subtle issues with file access or networking—test before adopting for all workflows.
	•	optional.md –
Non-essential install options.
🟡 Skip unless you have a special use-case.
	•	replit.md –
Web-based install—quickest for demos/experiments, but limited for “real” dev.

leaderboards/ 🟡

Performance data and comparisons for LLMs across versions and providers.
🟡 Useful for model selection, but may become outdated quickly.
🟠 CAUTION: Don’t over-interpret as “the final word”—real performance may differ in your use-case.
	•	by-release-date.md –
Track performance by release date—good for historical context.
	•	contrib.md –
Community leaderboard contributions—may contain useful edge cases.
	•	edit.md –
Guide to editing/maintaining leaderboards.
	•	index.md, notes.md, refactor.md –
Index, meta-commentary, and notes on refactor impacts on performance.

legal/ 🟡

Legal/privacy files.
🟡 Review if you intend to share/contribute or deploy in a sensitive setting.
	•	contributor-agreement.md –
Upstream contributor agreement—read before submitting PRs.
	•	privacy.md –
How Aider handles user/code data.
⚠️ TRAP/WARNING: If using private/sensitive data, read before running or sharing sessions with Aider!

llms/ 🟢

Documentation for integrating specific LLM APIs/providers (Anthropic, OpenAI, Azure, etc).
🟢 Read when switching models or troubleshooting LLM-specific issues.
🟡 Ignore if you’re only using the default provider.
	•	anthropic.md, azure.md, bedrock.md, … xai.md –
Each is provider-specific setup/tuning doc.
🟠 CAUTION: Some API features may differ in critical ways—read provider doc carefully when integrating a new LLM.

more/ 🟡

Miscellaneous advanced/edge-case docs.
🟡 Useful for “weird” or advanced needs—safe to skip if focusing on basics.
	•	analytics.md –
Tracking/analyzing usage patterns.
🟠 CAUTION: May introduce privacy/surveillance concerns—disable unless really needed.
	•	edit-formats.md, infinite-output.md, … –
Format extensions, handling large generations, etc.

recordings/ 🟡

Session logs and playbacks.
🟡 Use as case studies for learning best practices or understanding common pitfalls.
🟠 CAUTION: Content may be outdated or specific to older Aider versions—use for illustration, not gospel.
	•	auto-accept-architect.md, … tree-sitter-language-pack.md –
Each is a specific session/feature recording.

troubleshooting/ 🟢

Collection of error diagnostics, fixes, and support notes.
🟢 Start here if Aider “breaks” or behaves unpredictably—often faster than web/forum search!
	•	aider-not-found.md, edit-errors.md, imports.md, … –
Each covers a specific class of error or troubleshooting method.
⚠️ TRAP/WARNING: Sometimes solutions are version-specific or require deep config understanding—cross-check your current setup before applying fixes blindly!

usage/ 🟢

Practical usage docs, tips, and tutorials.
🟢 Begin here for day-to-day reference, onboarding, or expanding workflow.
🟡 Not always exhaustive—cross-reference config/troubleshooting for deep questions.
	•	browser.md, caching.md, commands.md, … –
Each is a specific feature/mode guide.
🟡 Some may be outdated if project is moving quickly—check file date.

Other files in Aider.chat/
	•	benchmarks-*.md – 🟡
Real-world LLM benchmarks.
🟠 CAUTION: Interpret as guidance, not hard law—your environment may yield different results.
	•	config.md – 🟢
Main entry-point config reference—start here when unclear which file to edit.
	•	faq.md – 🟢
Frequently asked questions—quick answers to common blocks.
	•	git.md – 🟢
Git integration for safe, auditable AI code edits.
🟠 CAUTION: If using advanced git features or non-standard workflows, some caveats may apply—double-check docs for edge cases.
	•	index.md, install.md, languages.md, llms.md, more-info.md, repomap.md, scripting.md, troubleshooting.md, unified-diffs.md, usage.md –
Misc docs—use index and file names to judge relevance, or search this passive-index for clarification.
