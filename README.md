# Mateus Stec

Reverse engineering on Android native code — stripped ARM64, no symbols, no
source. I find the mechanism, confirm it at runtime, and write it down so the
next person does not have to rediscover it.

Most of what I use, I had to build. A few of those are public:

| Repo | What it solves |
|---|---|
| [elf-xref](https://github.com/0xstallen/elf-xref) | Cross-references for stripped ARM64 ELF. Decodes `ADRP`/`ADD`/`LDR` directly — 0.6s for a full `.text` sweep of a 4.2 MB library, against 2.2s for a plain capstone sweep and 14.2s for instruction-by-instruction decoding. |
| [frida-harness](https://github.com/0xstallen/frida-harness) | Call-site histogram for a hooked function. Keyed on `returnAddress - moduleBase`, because the heap address changes every launch and the call site does not. |
| [apk-audit-checklist](https://github.com/0xstallen/apk-audit-checklist) | First-pass Android security review. Manifest, network, storage, anti-tamper, native layer — and the bar a finding has to clear to be reportable. |

## Current focus

- Static analysis of stripped native libraries — anchoring on string and
  constant cross-references when there are no symbols to follow
- Runtime instrumentation that survives repeated attach, on real devices
- Repackaging pipelines: decompile, patch, recompile, sign v2/v3, verify

## Tooling

`Ghidra` · `Frida` · `capstone` · `pyelftools` · `LIEF` · `apktool` · `Python` · `C/C++`

## Contact

Open to contract and part-time work — reverse engineering, native debugging,
tooling. Remote, UTC-3, overlap with US and EU hours.

Telegram: [@mateusstec](https://t.me/mateusstec)
