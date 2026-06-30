# Awesome Agent Skill Registry [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of resources for building, publishing, and consuming AI agent skill packages — covering registries, tooling, frameworks, and best practices across the agent ecosystem.

---

## Contents

- [Registries & Package Hosts](#registries--package-hosts)
- [CLI Tools & Package Managers](#cli-tools--package-managers)
- [Skill Frameworks & SDKs](#skill-frameworks--sdks)
- [Agent Harnesses & Runtimes](#agent-harnesses--runtimes)
- [Versioning & Dependency Resolution](#versioning--dependency-resolution)
- [Skill Discovery & Search](#skill-discovery--search)
- [Schema & Specification](#schema--specification)
- [Testing & Validation](#testing--validation)
- [Security & Trust](#security--trust)
- [Observability & Debugging](#observability--debugging)
- [Example Skill Packages](#example-skill-packages)
- [Learning Resources](#learning-resources)
- [Community & Ecosystem](#community--ecosystem)

---

## Registries & Package Hosts

Places to publish, browse, and install agent skill packages.

- [npm](https://www.npmjs.com) — The JavaScript package registry; widely used to host skill packages with `@agent-skills/` scoped namespaces.
- [PyPI](https://pypi.org) — Python's package index; natural home for Python-based skill modules and tool wrappers.
- [GitHub Packages](https://github.com/features/packages) — Host skill packages alongside source code with tight CI/CD integration.
- [JSR](https://jsr.io) — Modern TypeScript-first registry with native ESM support, well-suited for typed skill definitions.
- [Verdaccio](https://verdaccio.org) — Lightweight self-hosted npm proxy registry; ideal for private enterprise skill registries.
- [Gitea](https://gitea.io) — Self-hosted Git service with built-in package registry support for npm, PyPI, and more.
- [Artifactory](https://jfrog.com/artifactory) — Enterprise-grade universal artifact repository with fine-grained access control for skill packages.
- [Cloudsmith](https://cloudsmith.io) — Fully managed multi-format package registry with geo-replication and audit logs.
- [Forgejo](https://forgejo.org) — Community fork of Gitea with package registry; good for air-gapped deployments.

---

## CLI Tools & Package Managers

Command-line interfaces for installing, publishing, and managing skill packages.

- [npm CLI](https://docs.npmjs.com/cli) — The reference CLI for the npm ecosystem; `npm install`, `publish`, and `pack` all apply directly to skill packages.
- [pnpm](https://pnpm.io) — Fast, disk-efficient package manager with strict dependency isolation; great for monorepo skill collections.
- [uv](https://github.com/astral-sh/uv) — Extremely fast Python package manager written in Rust; ideal for Python skill package workflows.
- [pipx](https://pipx.pypa.io) — Install Python CLI-based skill tools in isolated environments without polluting global state.
- [Bun](https://bun.sh) — All-in-one JavaScript runtime and package manager with near-instant installs.
- [Yarn Berry](https://yarnpkg.com) — Modern Yarn with Plug'n'Play and zero-install support; useful for reproducible skill environments.
- [Homebrew](https://brew.sh) — macOS/Linux package manager; useful for distributing standalone skill CLI binaries.
- [Scoop](https://scoop.sh) — Windows command-line installer; complements Homebrew for cross-platform skill tool distribution.
- [cargo-binstall](https://github.com/cargo-bins/cargo-binstall) — Install pre-built Rust binaries; relevant for high-performance skill runtime tools.
- [mise](https://mise.jdx.dev) — Polyglot tool version manager; pin exact runtime versions for reproducible skill execution environments.

---

## Skill Frameworks & SDKs

Libraries and frameworks for authoring agent skills.

- [LangChain Tools](https://python.langchain.com/docs/modules/tools) — Structured tool interface used by LangChain agents; a de facto standard for skill shape.
- [OpenAI Function Calling](https://platform.openai.com/docs/guides/function-calling) — JSON Schema-based function definitions that most modern agents understand natively.
- [Anthropic Tool Use](https://docs.anthropic.com/en/docs/tool-use) — Claude's native tool/skill protocol with structured input and output schemas.
- [LlamaIndex Tools](https://docs.llamaindex.ai/en/stable/module_guides/deploying/agents/tools) — Tool abstractions for LlamaIndex agents with built-in query engine and API wrappers.
- [Semantic Kernel Plugins](https://learn.microsoft.com/en-us/semantic-kernel/agents/plugins) — Microsoft's plugin model for skills across C#, Python, and Java.
- [AutoGen Tools](https://microsoft.github.io/autogen/docs/tutorial/tool-use) — Tool registration for multi-agent AutoGen workflows.
- [CrewAI Tools](https://docs.crewai.com/concepts/tools) — Composable tool system for CrewAI agent crews with built-in caching.
- [Haystack Tools](https://docs.haystack.deepset.ai/docs/agent) — Tool interface for Haystack pipelines and agents.
- [Pydantic AI Tools](https://ai.pydantic.dev/tools) — Type-safe tool definitions backed by Pydantic validation; excellent developer experience.
- [ToolSpec (OpenAPI)](https://swagger.io/specification) — Use OpenAPI specs as the canonical source of truth for HTTP-based skill definitions.
- [MCP (Model Context Protocol)](https://modelcontextprotocol.io) — Anthropic's open protocol for connecting agents to external tools and data sources.

---

## Agent Harnesses & Runtimes

Environments that load and execute skill packages at runtime.

- [Claude Code](https://claude.ai/code) — Anthropic's agentic coding environment; reads skill files from disk and executes them in context.
- [Cursor](https://cursor.sh) — AI-first code editor with agent mode that can invoke registered tools and skills.
- [GitHub Copilot Workspace](https://githubnext.com/projects/copilot-workspace) — GitHub's task-oriented agent environment with extensible tool support.
- [Aider](https://aider.chat) — Terminal-based AI coding assistant; supports custom tool scripts alongside LLM sessions.
- [Continue](https://continue.dev) — Open-source IDE extension with a context provider system that maps well to skill packages.
- [Cline](https://github.com/cline/cline) — Autonomous coding agent for VS Code with MCP server support for skill loading.
- [Goose](https://block.github.io/goose) — Block's open-source agent with a toolkit system for installing and running skills.
- [Sweep](https://sweep.dev) — AI junior developer that resolves GitHub issues; extensible with custom skill handlers.
- [SWE-agent](https://swe-agent.com) — Research agent for software engineering tasks with a configurable tool interface.
- [OpenHands](https://github.com/All-Hands-AI/OpenHands) — Open-source coding agent platform (formerly OpenDevin) with sandboxed skill execution.
- [Agentless](https://github.com/OpenAutoCoder/Agentless) — Lightweight agent framework focused on minimal, auditable tool use.

---

## Versioning & Dependency Resolution

Tools and standards for managing skill package versions and their dependencies.

- [Semantic Versioning (SemVer)](https://semver.org) — The foundational spec for `MAJOR.MINOR.PATCH` versioning that all skill packages should follow.
- [node-semver](https://github.com/npm/node-semver) — The canonical semver parsing and range-matching library used by npm's resolver.
- [packaging (Python)](https://packaging.pypa.io) — Python library for parsing PEP 440 version strings and dependency specifiers.
- [Renovate](https://docs.renovatebot.com) — Automated dependency update bot; keeps skill package dependencies current across repos.
- [Dependabot](https://docs.github.com/en/code-security/dependabot) — GitHub-native dependency update automation with security advisory integration.
- [pip-tools](https://pip-tools.readthedocs.io) — Compile pinned `requirements.txt` from high-level specs; useful for reproducible skill environments.
- [Poetry](https://python-poetry.org) — Python dependency manager with a lock file and built-in publishing workflow.
- [Cargo (Rust)](https://doc.rust-lang.org/cargo) — Reference implementation of a modern resolver with workspace support; good design inspiration.
- [pubgrub](https://github.com/pubgrub-rs/pubgrub) — Rust implementation of the PubGrub version solving algorithm used by Dart/Flutter.
- [Nix](https://nixos.org) — Purely functional package manager enabling fully reproducible skill runtime environments.

---

## Skill Discovery & Search

Tools and patterns for finding the right skill package for a task.

- [npm search](https://www.npmjs.com/search) — Full-text search across npm with keyword, author, and quality filters.
- [libraries.io](https://libraries.io) — Aggregates package metadata across 30+ registries; useful for cross-ecosystem skill discovery.
- [Sourcegraph](https://sourcegraph.com) — Universal code search; find real-world skill implementations across public repositories.
- [grep.app](https://grep.app) — Fast regex search across GitHub; great for finding skill usage patterns in the wild.
- [OpenTools](https://opentools.ai) — Directory of AI tools and integrations with categorized browsing.
- [Toolhouse](https://toolhouse.ai) — Managed tool store for AI agents with one-line install and hosted execution.
- [Composio](https://composio.dev) — 150+ pre-built integrations packaged as agent tools with managed auth.
- [LangChain Hub](https://smith.langchain.com/hub) — Community repository of prompts and chains; includes reusable tool configurations.
- [Smithery](https://smithery.ai) — Registry and marketplace for MCP servers, searchable by capability.

---

## Schema & Specification

Standards and formats for defining skill interfaces and manifests.

- [JSON Schema](https://json-schema.org) — The lingua franca for describing skill input/output shapes; supported by virtually every agent.
- [OpenAPI 3.1](https://spec.openapis.org/oas/v3.1.0) — REST API specification format; doubles as a skill manifest for HTTP-based tools.
- [AsyncAPI](https://www.asyncapi.com) — Event-driven API specification; useful for skills that emit or consume streams.
- [JSON-LD](https://json-ld.org) — Linked data format for adding semantic meaning to skill metadata and capability descriptions.
- [SPDX](https://spdx.dev) — Software Package Data Exchange format for expressing license information in skill manifests.
- [CycloneDX](https://cyclonedx.org) — Software Bill of Materials (SBOM) standard; apply to skill packages for supply chain transparency.
- [package.json spec](https://docs.npmjs.com/cli/v10/configuring-npm/package-json) — The most widely understood package manifest format; a reasonable baseline for skill manifests.
- [pyproject.toml (PEP 517/518)](https://peps.python.org/pep-0517) — Modern Python project metadata standard; clean model for Python skill package manifests.
- [Zod](https://zod.dev) — TypeScript-first schema validation; define and validate skill I/O schemas at runtime.
- [Pydantic](https://docs.pydantic.dev) — Python data validation using type hints; the standard for typed skill interfaces in Python.

---

## Testing & Validation

Frameworks and approaches for testing skill packages before publishing.

- [Vitest](https://vitest.dev) — Fast Vite-native test runner; ideal for unit-testing TypeScript skill implementations.
- [Jest](https://jestjs.io) — Widely used JavaScript test framework with snapshot testing for skill output validation.
- [pytest](https://pytest.org) — The standard Python test framework; pairs well with `pytest-asyncio` for async skill tests.
- [Hypothesis](https://hypothesis.readthedocs.io) — Property-based testing for Python; fuzz skill inputs to find edge cases automatically.
- [fast-check](https://fast-check.dev) — Property-based testing for JavaScript/TypeScript skill implementations.
- [Pact](https://pact.io) — Consumer-driven contract testing; validate that skill interfaces match what agents actually expect.
- [Schemathesis](https://schemathesis.readthedocs.io) — Automatically generate and run tests from OpenAPI specs; great for HTTP-based skills.
- [Testcontainers](https://testcontainers.com) — Spin up real dependencies (databases, APIs) in Docker for integration-testing skills.
- [VCR.py](https://vcrpy.readthedocs.io) — Record and replay HTTP interactions; deterministic testing for skills that call external APIs.
- [Polly.js](https://netflix.github.io/pollyjs) — JavaScript HTTP record/replay library; same pattern as VCR.py for Node-based skills.
- [AgentEval](https://github.com/microsoft/autogen/tree/main/samples/agenteval) — Framework for evaluating agent task completion; apply to end-to-end skill validation.

---

## Security & Trust

Practices and tools for securing the skill package supply chain.

- [Sigstore](https://www.sigstore.dev) — Keyless signing and verification for software artifacts; sign skill packages at publish time.
- [cosign](https://github.com/sigstore/cosign) — Container and artifact signing tool from the Sigstore project.
- [npm audit](https://docs.npmjs.com/cli/v10/commands/npm-audit) — Scan skill package dependencies for known vulnerabilities.
- [pip-audit](https://github.com/pypa/pip-audit) — Audit Python skill environments against the OSV vulnerability database.
- [Socket](https://socket.dev) — Detects supply chain attacks and malicious packages before they reach your registry.
- [Snyk](https://snyk.io) — Developer-first security platform with deep package vulnerability scanning.
- [SLSA Framework](https://slsa.dev) — Supply chain Levels for Software Artifacts; a maturity model for skill package provenance.
- [in-toto](https://in-toto.io) — Framework for securing the steps of a software supply chain end-to-end.
- [OSV (Open Source Vulnerabilities)](https://osv.dev) — Google's open vulnerability database covering npm, PyPI, and many other ecosystems.
- [Semgrep](https://semgrep.dev) — Static analysis for finding security issues in skill source code before publishing.
- [Trivy](https://trivy.dev) — Comprehensive vulnerability scanner for packages, containers, and IaC configs.

---

## Observability & Debugging

Tools for understanding what skills are doing at runtime.

- [OpenTelemetry](https://opentelemetry.io) — Vendor-neutral observability framework; instrument skill invocations with traces, metrics, and logs.
- [Langfuse](https://langfuse.com) — Open-source LLM observability platform with tool call tracing and cost tracking.
- [LangSmith](https://smith.langchain.com) — LangChain's tracing and evaluation platform; visualize skill call chains in agent runs.
- [Arize Phoenix](https://phoenix.arize.com) — Open-source AI observability with trace visualization for agent tool use.
- [Helicone](https://helicone.ai) — LLM proxy with request logging, caching, and skill call analytics.
- [Braintrust](https://braintrustdata.com) — Evaluation and logging platform for AI applications with dataset management.
- [Pino](https://getpino.io) — Extremely fast JSON logger for Node.js; structured logging baseline for skill servers.
- [structlog](https://www.structlog.org) — Structured logging for Python skill implementations with context binding.
- [Sentry](https://sentry.io) — Error tracking and performance monitoring; catch skill runtime exceptions in production.
- [Jaeger](https://www.jaegertracing.io) — Open-source distributed tracing; visualize latency across multi-skill agent pipelines.

---

## Example Skill Packages

Real-world and reference implementations worth studying.

- [langchain-community tools](https://github.com/langchain-ai/langchain/tree/master/libs/community/langchain_community/tools) — Large collection of production tool implementations covering search, code execution, APIs, and more.
- [composio-core](https://github.com/ComposioHQ/composio) — Source for Composio's 150+ agent integrations; good reference for auth-aware skill design.
- [browser-use](https://github.com/browser-use/browser-use) — Browser automation skill for AI agents; well-structured tool interface over Playwright.
- [e2b Code Interpreter](https://github.com/e2b-dev/code-interpreter) — Sandboxed code execution skill with streaming output; reference for stateful skills.
- [Hermes Tweet](https://github.com/Xquik-dev/hermes-tweet) — Hermes Agent plugin and portable skill package for X/Twitter research, monitoring, and approval-gated social actions.
- [Tavily Search](https://github.com/tavily-ai/tavily-python) — Web search skill optimized for LLM agents; clean, minimal interface design.
- [crawl4ai](https://github.com/unclecode/crawl4ai) — Web crawling and scraping skill built for AI agent consumption.
- [mcp-server-filesystem](https://github.com/modelcontextprotocol/servers/tree/main/src/filesystem) — Reference MCP server for filesystem operations; canonical example of the MCP skill pattern.
- [mcp-server-github](https://github.com/modelcontextprotocol/servers/tree/main/src/github) — GitHub API skill via MCP; demonstrates OAuth and paginated resource handling.
- [mcp-server-postgres](https://github.com/modelcontextprotocol/servers/tree/main/src/postgres) — PostgreSQL read access skill; shows safe, read-only database tool design.
- [openai-python tools examples](https://github.com/openai/openai-python/tree/main/examples) — Official examples of function-calling tool definitions from OpenAI.

---

## Learning Resources

Articles, courses, and references for going deeper.

- [Building Effective Agents — Anthropic](https://www.anthropic.com/research/building-effective-agents) — Anthropic's guide to agent design patterns including tool use best practices.
- [Function Calling Guide — OpenAI Cookbook](https://cookbook.openai.com/examples/how_to_call_functions_with_chat_models) — Practical walkthrough of designing and calling tools with the OpenAI API.
- [MCP Documentation](https://modelcontextprotocol.io/docs) — Official spec and tutorials for the Model Context Protocol.
- [LangChain Expression Language (LCEL)](https://python.langchain.com/docs/expression_language) — Composable chain primitives that inform good skill composition patterns.
- [Semantic Kernel Concepts](https://learn.microsoft.com/en-us/semantic-kernel/concepts) — Microsoft's documentation on plugins, planners, and memory — transferable concepts for any skill system.
- [Designing Data-Intensive Applications](https://dataintensive.net) — Kleppmann's book; chapters on encoding and schema evolution apply directly to skill versioning.
- [The Twelve-Factor App](https://12factor.net) — Methodology for building portable, maintainable services; applies cleanly to skill server design.
- [npm's package.json documentation](https://docs.npmjs.com/cli/v10/configuring-npm/package-json) — Exhaustive reference for the most widely understood package manifest format.
- [SemVer FAQ](https://semver.org/#faq) — Answers to common versioning edge cases you will encounter when publishing skills.
- [OWASP Top 10 for LLM Applications](https://owasp.org/www-project-top-10-for-large-language-model-applications) — Security risks specific to LLM tool use, including prompt injection via skill outputs.
- [Thoughtworks Technology Radar](https://www.thoughtworks.com/radar) — Periodic assessment of emerging tools and techniques; tracks agent tooling trends.

---

## Community & Ecosystem

Places to connect, discuss, and stay current.

- [Anthropic Discord](https://discord.gg/anthropic) — Official community for Claude and MCP discussion; active #tool-use and #mcp channels.
- [LangChain Discord](https://discord.gg/langchain) — Large community for LangChain, LangGraph, and LangSmith users and contributors.
- [Hugging Face Discord](https://discord.gg/huggingface) — Community hub for open-source AI; active agent and tool-use discussions.
- [r/LocalLLaMA](https://www.reddit.com/r/LocalLLaMA) — Reddit community covering open-source models and local agent setups.
- [AI Engineer Foundation](https://www.ai.engineer) — Community and conference series focused on applied AI engineering, including agent tooling.
- [AgentOps Community](https://discord.gg/agentops) — Discord focused on agent observability, evaluation, and production operations.
- [MCP GitHub Discussions](https://github.com/modelcontextprotocol/servers/discussions) — Official discussion board for MCP server development and skill packaging questions.
- [Hacker News — "Ask HN: What agent tools are you building?"](https://news.ycombinator.com) — Search HN for periodic threads on agent tooling; high signal-to-noise ratio.
- [The Batch — DeepLearning.AI](https://www.deeplearning.ai/the-batch) — Weekly newsletter covering AI research and engineering, including agent ecosystem news.
- [TLDR AI](https://tldr.tech/ai) — Daily digest of AI news with good coverage of developer tooling and agent frameworks.

---

## Contributing

Contributions are welcome and encouraged. This list grows better with community input.

**To add an item:**

1. Fork this repository.
2. Add your item to the relevant section in alphabetical order within that section.
3. Use the format: `- [Name](URL) — One-line description that explains what it does, not what it is.`
4. Make sure the link is to the primary source (official docs, GitHub repo, or homepage).
5. Open a pull request with a brief explanation of why the item belongs here.

**Guidelines:**

- Items should be directly relevant to building, publishing, discovering, or running agent skill packages.
- Prefer actively maintained projects. If a project has been archived or unmaintained for over a year, it will be removed.
- One item per pull request makes review faster.
- Descriptions should be factual and neutral — no marketing language.
- If you are the author of a project, disclose that in your PR description.

**To report a broken link or outdated entry**, open an issue with the section name and item name.

---

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0)

To the extent possible under law, the contributors to this list have waived all copyright and related or neighboring rights to this work. See the [LICENSE](LICENSE) file for details.

The list itself is released under [CC0 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0). Individual linked projects retain their own licenses.
```

## Visual Overview

```mermaid
flowchart TD
    User["User / Developer"] --> Interface["CLI / UI / API"]
    Interface --> CommandSet["Commands\nskill init — scaffold a new skill package with manifest\nskill publish — pack and upload a skill to the registry"]
    CommandSet --> Core["Agent Skill Registry"]
    Core --> Feature1["Publish skill packages with semantic versioning and metadata"]
    Core --> Feature2["Full-text search and tag-based discovery of community skills"]
    Core --> Feature3["CLI to install, update, and resolve skill dependencies"]
    Core --> Feature4["Harness-agnostic output adapters (Claude .md, Cursor rules, generic)"]
    Core --> Runtime["Runtime\nfastapi, uvicorn, typer"]
    Runtime --> Deploy["Docker Support"]
    Core --> Output["Repository Artifacts"]
