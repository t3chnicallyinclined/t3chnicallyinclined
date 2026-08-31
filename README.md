## Tristan Rega

Infrastructure and support engineering — about fifteen years of it. Most recently five years
keeping a cloud-native core banking platform running for ~60 banks: production on-call with
break-glass into regulated environments, and the major incident framework the engineering
org now runs on.

Everything below is what I build when nobody's asking me to.

---

### What I'm working on

**[maplecast-flycast](https://github.com/t3chnicallyinclined/maplecast-flycast)** — Dreamcast
streaming that ships raw GPU command buffers instead of encoded video. The browser replays
them locally, so frames are byte-identical rather than compressed. Two diff layers take it
from the 25–50 Mbps video would cost down to **~4 Mbps** — on a 2 vCPU box **with no GPU at
all**. Powers an always-on cabinet at [play.nobd.net](https://play.nobd.net).

**[GP2040-CE-NOBD](https://github.com/t3chnicallyinclined/GP2040-CE-NOBD)** — controller
firmware that fixes something most players assumed was their own execution. Fingers have a
2–8 ms gap between contacts; the Dreamcast polled every 16.67 ms so it was invisible, PC
polls every 1 ms so it isn't — and a simultaneous press lands on two separate frames. The
fix is a sync window aimed at your finger instead of the poll. I'm not a firmware developer;
I just wanted my dashes back.

**[mvc2-oracle](https://github.com/t3chnicallyinclined/mvc2-oracle)** — a reverse-engineering
toolkit, and a knowledge graph where every claim carries a truth status and a link to its
evidence — **including the things we proved don't work.** Most knowledge bases only record
wins, which is why teams re-walk the same dead end every six months.

**[design-notes](https://github.com/t3chnicallyinclined/design-notes)** — design proposals
for systems I think should exist. Problem, data model, trade-offs, failure modes, rollout.

---

### The through-line

Different domains, different languages, same reflexes:

- **Compare two states to find what matters** — diffing memory to locate game state, diffing
  frames to cut bandwidth by an order of magnitude, diffing implementations to prove a
  firmware change was safe before shipping it
- **Isolate what must not stall from what's unpredictable** — a relay in front of the
  emulator, live updates on their own service, heavy work in a throwaway context
- **Never let a component grade its own work** — differential proofs, deterministic checks
  rather than a model judging a model
- **Work out who owns the truth and don't shadow it** — no database where the provider
  already owns the state; one authoritative log with every other store derived and rebuildable

I also build a fair amount on LLM APIs — multi-model routing, retrieval over graph and
vector stores, agent orchestration, content safety guardrails, and the unglamorous parts
like usage metering and knowing which stage doesn't need a model at all.

---

### Currently

Open to work — applied AI and solutions architecture, enterprise support engineering, or
anything where the job is being the person a customer reaches for when it breaks. New York
or remote.

📫 **tristech@gmail.com** · [LinkedIn](https://www.linkedin.com/in/tristech)
