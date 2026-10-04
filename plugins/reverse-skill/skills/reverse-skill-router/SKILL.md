---
name: reverse-skill-router
description: "Use when Codex needs the reverse-skill suite for authorized reverse engineering, security assessment, defensive analysis, or CTF routing; covers native/bytecode/WASM/custom DSL-VM reversing, APK/Android and iOS, .NET/C#, Go/Rust, macOS/Mach-O, IDA/Ghidra/Binary Ninja/radare2, binary/symbol/patch diffs, firmware/IoT/UART/JTAG/SPI, browser JavaScript/extensions and desktop automation, protocol/PCAP replay, pwn/exploit chains, API/GraphQL/WebSocket, web/SRC-bounty playbooks, identity/OAuth/OIDC/SAML/JWT and Windows/AD/AD CS/Kerberos, cloud/Kubernetes/container runtime, malware/EDR, DFIR timelines, threat intelligence/OSINT/hunting, code/database/email, LLM/agent/RAG/MCP, supply-chain/CI/CD, OT/ICS, Wi-Fi/RF/SDR, diagrams and security reports and CTF/AWD/ranges and sandbox orchestration for web/SSR/source maps/browser persistence/WebSocket/SSE, proxy/Host/HTTP smuggling/SSRF/metadata, queues/races/file parsers/ZipCrypto, crypto/stego/mobile hooks, reverse/pwn/firmware/PCAP/DFIR, prompt injection/cloud/container escape, identity/certificates/tickets/credentials/mailbox pivots. Resolves the repository from the current workspace or an explicit local path, loads the master skill and tool index, and retains case/scope authorization, native primary routes, and no unrequested tool installation or registration."
---

# Reverse Skill Codex adapter

This plugin is an optional Codex entry point. The repository remains the canonical, client-neutral implementation.

When the current workspace is the `reverse-skill` repository:

1. Read `RULES.md` at the repository root.
2. Run the platform-native `skills/scripts/master-route` entry with the user's task to select the PRIMARY skill from `skills/config/routing.json`.
3. Before any target action, create and validate `work/<case>/scope.md` with the platform-native `case-init` and `case-guard` scripts.
4. Open the selected `skills/<PRIMARY>/SKILL.md` and follow its task-specific instructions.
5. Resolve tools only through the generated `skills/tool-index.md`; do not register MCP servers or install tools unless the user requested that action.

If the repository is not the current workspace and no local repository path was supplied, explain that this adapter does not bundle a second copy of the router. Ask the user to open or clone `https://github.com/zhaoxuya520/reverse-skill` and then continue from its `RULES.md`.

Do not treat the presence of this plugin, a target name, or a sample path as authorization. Authorization comes from the repository's scope contract.
