## Tristan Rega

Twenty years in infrastructure and technical support. Most recently five years of cloud
support for a core banking platform serving ~60 banks. Career details live on
[LinkedIn](https://www.linkedin.com/in/tristech); this is what I build when nobody's asking
me to.

---

### What I'm working on

**[maplecast-flycast](https://github.com/t3chnicallyinclined/maplecast-flycast)**: Dreamcast
streaming that ships raw GPU command buffers instead of encoded video. The browser replays
them locally, so frames are byte-identical rather than compressed. Two diff layers take it
from the 25–50 Mbps video would cost down to **~4 Mbps**, on a 2 vCPU box **with no GPU at
all**. Powers an always-on cabinet at [play.nobd.net](https://play.nobd.net).

**[GP2040-CE-NOBD](https://github.com/t3chnicallyinclined/GP2040-CE-NOBD)**: controller
firmware that fixes something most players assumed was their own execution. Fingers have a
2–8 ms gap between contacts; the Dreamcast polled every 16.67 ms so it was invisible, PC
polls every 1 ms so it isn't, and a simultaneous press lands on two separate frames. The
fix is a sync window aimed at your finger instead of the poll. I'm not a firmware developer;
I just wanted my dashes back.

**[autoseo](https://github.com/t3chnicallyinclined/autoseo)**: a podcast-to-clips and SEO
pipeline built around never paying for inference you can avoid. Three ONNX models run locally
before anything hosted is touched, and active-speaker detection is just face presence multiplied
by voice activity: two signals I already had, so no model gets paid to work out who is talking.
A batched ranker turns a two-hour episode into about twenty model calls instead of 240. The part
I'd point at is the loop: how published clips actually performed, views on YouTube and likes and
reposts on Bluesky, gets pulled back into the ranker prompt, so what it picks improves from
measured outcomes.

**Forgily Creations** ([creations.forgily.com](https://creations.forgily.com)): an AI character
platform in Rust. The promise is that no two characters are ever alike, which is a hard thing to
guarantee about a stochastic system, so it's defended in seven independent layers: a combinatorial
visual seed, a structured schema the model can't cheat, exact-match dedup, and a vector novelty
check stratified by type so the measure stays sharp as the collection grows. Private repo; the
product is live.

**[mvc2-oracle](https://github.com/t3chnicallyinclined/mvc2-oracle)**: a reverse-engineering
toolkit, and a knowledge graph where every claim carries a truth status and a link to its
evidence, **including the things we proved don't work.** Most knowledge bases only record
wins, which is why teams re-walk the same dead end every six months.

**[design-notes](https://github.com/t3chnicallyinclined/design-notes)**: design proposals
for systems I think should exist. Problem, data model, trade-offs, failure modes, rollout.

---

### The through-line

Different domains, different languages, same reflexes:

- **Compare two states to find what matters**: diffing memory to locate game state, diffing
  frames to cut bandwidth by an order of magnitude, diffing implementations to prove a
  firmware change was safe before shipping it
- **Isolate what must not stall from what's unpredictable**: a relay in front of the
  emulator, live updates on their own service, heavy work in a throwaway context
- **Never let a component grade its own work**: differential proofs, deterministic checks
  rather than a model judging a model
- **Work out who owns the truth and don't shadow it**: no database where the provider
  already owns the state; one authoritative log with every other store derived and rebuildable
- **Let the fast path degrade to the boring one**: a neural VAD that falls back to ffmpeg when
  its model file is missing, pitch detection skipped rather than fatal when a binary isn't
  installed, a read-mirror that degrades to the JSON that owns the truth, live updates that poll
  underneath a WebSocket when a socket misses a transition

I also build a fair amount on LLM APIs: multi-model routing, retrieval over graph and
vector stores, agent orchestration, content safety guardrails, and the unglamorous parts
like usage metering and knowing which stage doesn't need a model at all.

---

### Currently

Open to work: applied AI and solutions architecture, enterprise support engineering, or
anything where the job is being the person a customer reaches for when it breaks. New York
or remote.

📫 **tristech@gmail.com** · [LinkedIn](https://www.linkedin.com/in/tristech)
