# passive_index.md

_A living, project-aware, holistically annotated map of the repository’s documentation and resource tree._

**Purpose:** Efficiently bridge high-level project goals and needs (minimal, moldable, self-reflexive Nix/AI environment) with the right resources, without getting lost in the forest of files.

**Legend:**  
- 🟢 CORE: Crucial for our workflow or understanding.  
- 🟡 PERIPHERAL: Useful reference, but not essential.  
- 🟠 CAUTION: Easy to get lost, outdated, or less relevant; read with care.  
- ⚠️ TRAP/WARNING: Often mistaken, distracts, or context risk—check meta annotation!  
- (Meta notes in italics.)

_This index is maintained for both human and AI navigation. When in doubt, check with AI or revisit this file for orientation._

---

## Root

- **AI-prompt: Principles (HOW, Efficacity)** 🟢  
    _Living record of project principles—**crucial for maintaining alignment, transparency, and AI/human self-reflexivity.**  
    Use to calibrate AI and yourself to core values and workflow philosophy before diving into technical docs._
- **My Computer Specifications** 🟡  
    _Reference hardware/environment info—can clarify why some configs/docs don’t “fit.” Only relevant for troubleshooting, sharing context with AI, or debugging environment-specific issues._
- **README** 🟢
    _General orientation. **If well-populated, read first for project overview.** If empty or minimal, skip and rely on this index._
- **temporal_narrative.md** 🟡  
    _Auxiliary project meta-narrative and orientation tool. Use for reflecting on project evolution, especially when time/context is ambiguous._
- **transcending_traps_of_the_project.md** 🟢  
    _Meta-compass for surfacing, reflecting on, and transcending both technical and meta/cognitive traps. Consult for process guidance, not as rigid law._
- **understanding_the_documentation_for_this_project.md** 🟢  
    _Project-centric synthesis distilling the paradigms, teachings, and practical affordances of major documentation sources. **Not a substitute for the docs—use as a compass for holistic orientation and meta-awareness.**_ 

---

## NIX OS/
_Meta: Centralized Nix/NixOS learning and reference.  
**Begin here for high-level system understanding—but beware: many sections are deep or reference-heavy, so use this index to sort what’s relevant to your current stage/needs.**_

### NixPills/ 🟢 **CORE**
_Deep tutorial—best resource for moving from “basic user” to “competent Nix architect.”  
Recommended for building the *mental models* needed for minimal, adaptive, declarative systems. Beware of technical depth—pace yourself, and don’t get bogged down if not every chapter is relevant yet!_
- **00-preface.md** – *(Sets intent and learning strategy. Good orientation, read if unsure where to start.)*
- **01-why-you-should-give-it-a-try.md** – *(Motivation, “what Nix is good for”—helpful if you’re still skeptical or need to align purpose.)*
- **02-install-on-your-running-system.md** – 🟠  
    _*Practical, but may be dated or not fit your minimal/context-unique setup—always double-check before running commands.*_
- **03-enter-environment.md** – 🟢  
    _*Crucial for sandboxing/isolating workflows—the core of safe, portable, reproducible hacking.*_
- **04-basics-of-language.md** – 🟢  
    _*Learn Nix language syntax and semantics—read if writing or editing any Nix expression, or debugging mysterious config failures.*_
- **05-functions-and-imports.md** – 🟢  
    _*Understand modularity/reusability in Nix. Required for meta-programmable configs.*_
- **06-20-*.md** –  
    _*Each covers an important build, package, or system management topic.  
    Pick what matches your current challenge—don’t try to “read it all” at once.*_
- **SUMMARY.md** –  
    _Navigation aid. Use to jump to topics or as a sanity check for coverage._

### NixOS Manual/ 🟢 **CORE**
_Official (and semi-official) NixOS manual—**your primary resource for nearly all system-level tasks, troubleshooting, and best practices.**  
If lost or stuck with NixOS, start here or search this first._
- **manual.md** – 🟢  
    _*Central reference—always check here for system questions before deep-diving web or forums.*_
- **Cheatsheet - NixOS Wiki.md** – 🟡  
    _*Quick, sometimes out-of-date but good for fast reference—don’t rely exclusively if details matter.*_
- **Unofficial nixos cheatsheet.md** – 🟡  
    _*Alternative cheatsheet—use for a different “voice” or where official docs are unclear.*_
- **contributing-to-this-manual.chapter.md** – 🟠  
    _*Mainly for those wanting to contribute to docs, not for core learning.*_
- **nixos-options.md** – 🟢  
    _*Reference for system configuration options—scan when tuning/tweaking system setup.*_
- **preface.md** –  
    _Meta-orientation, may clarify manual’s purpose or audience._
- **README.md, default.nix, shell.nix, common.nix** – 🟠  
    _Mostly internal or technical scaffolding; rarely needed unless hacking the manual itself or contributing upstream._

### Nix.dev/ 🟡 **PERIPHERAL**
_Official “meta site” for Nix learning.  
**Useful for initial orientation and links out to deeper resources.**  
Often, you’ll be bounced to external docs—use for broad orientation, not deep dives._
- **index.md** –  
    _Table of contents or top-level entry point._
- **install-nix.md** – 🟢  
    _*Current official instructions for installing Nix—use this over random blog posts or outdated forum advice.*_
- **recommended-reading.md** – 🟡  
    _*Good overview for “where to start” if totally new or overwhelmed by doc sprawl.*_
- **conf.py, robots.txt** – 🟠  
    _Technical/config files—ignore unless working on doc site infrastructure._

### NixOS and Flakes (book)/ 🟡  
_An evolving, book-length guide to using NixOS and Flakes.  
More in-depth than most docs, but potentially overwhelming or opinionated—use for advanced learning, not as first steps._
- **index.md, preface.md** –  
    _Start here for a sense of what’s in scope._
- **(all chapters)** –  
    _Pick by topic of current challenge. Flakes are an “advanced” Nix feature; skip unless aiming for bleeding-edge workflow or reproducibility._

### NixPkgs/ 🟡 **PERIPHERAL**
_Reference for the Nix package collection.  
Essential if you plan to write or heavily modify packages, less critical for just configuring your system.  
**Some sections are deep internals—beware rabbit holes!**_
- **functions.md, stdenv.md** – 🟠 ⚠️  
    _Read only if writing/maintaining packages. Deep, not required for normal system config—easy to lose context here._
- **manual.md.in, build-helpers.md, development.md, contributing.md, ...** – 🟡  
    _Scan as needed, but keep project needs in mind; these are more for package contributors._
- **README.md, shell.nix, lib.md** –  
    _Mostly for those hacking or extending Nixpkgs itself._

### nixacademy cheatsheet (unofficial).pdf – 🟡  
_Fast, practical reference—good for command lookup, but beware of drift/outdated advice. Double-check with official docs for critical tasks._

---

## Aider.chat (PairProgrammingWithLLM)/ 🟢

_Meta: Central toolkit for dialogical/AI-augmented programming and configuration.  
Aider is both an AI pair-programmer and a living demonstration of agentic, co-evolving workflows—directly aligned with our aim for moldable, reflexive, and minimal computing.  
**Read to: adapt AI workflows, prototype config/code, and avoid “black-box” habits with LLMs.**_

### config/ 🟢
_Core settings and behaviors for Aider itself—change these to “bend” Aider to fit your workflows, privacy, and minimalism principles.  
Misconfigurations here can completely change how AI behaves—consult the meta annotations before editing!_
- **adv-model-settings.md** –  
    _Advanced LLM parameters (temperature, system prompts, response length, etc).  
    🟠 CAUTION: *Tweaking without context can make LLM less predictable or less aligned with your intentions—edit only with clear goal.*_
- **aider_conf.md** –  
    _Primary config file—foundation for Aider’s operation.  
    🟢 CORE: *If you need to make global changes or debug strange behaviors, start here.*_
- **api-keys.md** –  
    _Managing and securing API keys for LLM providers.  
    🟠 CAUTION: *Never share or check in this file. Essential for LLM access, but security risk if mishandled.*_
- **dotenv.md** –  
    _How to set and manage environment variables for Aider.  
    🟡 Useful for stateless/minimal environments—often easier than editing config files directly._
- **editor.md** –  
    _Settings for integrating Aider with code editors (VSCode, vim, etc).  
    🟡 Edit if Aider’s not connecting to your preferred environment._
- **model-aliases.md** –  
    _Custom model names for fast switching between LLMs.  
    🟡 Peripheral—only edit if juggling multiple models or providers._
- **options.md** –  
    _All tweakable Aider settings, described.  
    🟡 Good for custom workflows, but can be overwhelming—read with a clear intention!_
- **reasoning.md** –  
    _Notes on Aider’s “reasoning” mechanics (prompt design, context management).  
    🟢 *If Aider’s responses seem “dumb” or context-blind, check here.*_

### install/ 🟡
_Install guides for various environments (Codespaces, Docker, Replit).  
🟢 Use if you want fast, isolated, or reproducible setups for Aider.  
🟡 Ignore if Aider is already working or you’re not changing environments._
- **codespaces.md** –  
    _Install in GitHub Codespaces (cloud-based dev)._
- **docker.md** –  
    _Containerized install—most “portable/reproducible” method.  
    🟠 CAUTION: *May introduce subtle issues with file access or networking—test before adopting for all workflows.*_
- **optional.md** –  
    _Non-essential install options.  
    🟡 Skip unless you have a special use-case._
- **replit.md** –  
    _Web-based install—quickest for demos/experiments, but limited for “real” dev._

### leaderboards/ 🟡
_Performance data and comparisons for LLMs across versions and providers.  
🟡 Useful for model selection, but may become outdated quickly.  
🟠 CAUTION: *Don’t over-interpret as “the final word”—real performance may differ in your use-case.*_
- **by-release-date.md** –  
    _Track performance by release date—good for historical context._
- **contrib.md** –  
    _Community leaderboard contributions—may contain useful edge cases._
- **edit.md** –  
    _Guide to editing/maintaining leaderboards._
- **index.md, notes.md, refactor.md** –  
    _Index, meta-commentary, and notes on refactor impacts on performance._

### legal/ 🟡
_Legal/privacy files.  
🟡 Review if you intend to share/contribute or deploy in a sensitive setting._
- **contributor-agreement.md** –  
    _Upstream contributor agreement—read before submitting PRs._
- **privacy.md** –  
    _How Aider handles user/code data.  
    ⚠️ TRAP/WARNING: *If using private/sensitive data, read before running or sharing sessions with Aider!*_

### llms/ 🟢
_Documentation for integrating specific LLM APIs/providers (Anthropic, OpenAI, Azure, etc).  
🟢 Read when switching models or troubleshooting LLM-specific issues.  
🟡 Ignore if you’re only using the default provider._
- **anthropic.md, azure.md, bedrock.md, ... xai.md** –  
    _Each is provider-specific setup/tuning doc.  
    🟠 CAUTION: *Some API features may differ in critical ways—read provider doc carefully when integrating a new LLM.*_

### more/ 🟡
_Miscellaneous advanced/edge-case docs.  
🟡 Useful for “weird” or advanced needs—safe to skip if focusing on basics._
- **analytics.md** –  
    _Tracking/analyzing usage patterns.  
    🟠 CAUTION: *May introduce privacy/surveillance concerns—disable unless really needed.*_
- **edit-formats.md, infinite-output.md, ...** –  
    _Format extensions, handling large generations, etc._

### recordings/ 🟡
_Session logs and playbacks.  
🟡 Use as case studies for learning best practices or understanding common pitfalls.  
🟠 CAUTION: *Content may be outdated or specific to older Aider versions—use for illustration, not gospel.*_
- **auto-accept-architect.md, ... tree-sitter-language-pack.md** –  
    _Each is a specific session/feature recording._

### troubleshooting/ 🟢
_Collection of error diagnostics, fixes, and support notes.  
🟢 Start here if Aider “breaks” or behaves unpredictably—often faster than web/forum search!_
- **aider-not-found.md, edit-errors.md, imports.md, ...** –  
    _Each covers a specific class of error or troubleshooting method.  
    ⚠️ TRAP/WARNING: *Sometimes solutions are version-specific or require deep config understanding—cross-check your current setup before applying fixes blindly!*_

### usage/ 🟢
_Practical usage docs, tips, and tutorials.  
🟢 Begin here for day-to-day reference, onboarding, or expanding workflow.  
🟡 Not always exhaustive—cross-reference config/troubleshooting for deep questions._
- **browser.md, caching.md, commands.md, ...** –  
    _Each is a specific feature/mode guide.  
    🟡 Some may be outdated if project is moving quickly—check file date._

#### Other files in Aider.chat/  
- **benchmarks-*.md** – 🟡  
    _Real-world LLM benchmarks.  
    🟠 CAUTION: *Interpret as guidance, not hard law—your environment may yield different results.*_
- **config.md** – 🟢  
    _Main entry-point config reference—start here when unclear which file to edit._
- **faq.md** – 🟢  
    _Frequently asked questions—quick answers to common blocks._
- **git.md** – 🟢  
    _Git integration for safe, auditable AI code edits.  
    🟠 CAUTION: *If using advanced git features or non-standard workflows, some caveats may apply—double-check docs for edge cases.*_
- **index.md, install.md, languages.md, llms.md, more-info.md, repomap.md, scripting.md, troubleshooting.md, unified-diffs.md, usage.md** –  
    _Misc docs—use index and file names to judge relevance, or search this passive-index for clarification._

