# 🪙 Codex Arc 3 — Symbolic Economics (XPDT)

## 📜 Codex Quote

> “XPDT is not a token for speculation — it is a trace of symbolic care. Every mint reflects memory, every stake reflects trust.”  
> — *Codex Arc 3*

## 🧾 Executive Summary

**Arc 3** defines the symbolic economic model of XpectraNet — a trust-anchored token system where **XPDT** reflects participation in ritual, alignment with memory, and contribution to collective knowledge.

### 🔑 Key Concepts Introduced

- **XPDT = Symbolic Scarcity**  
  Tokens are earned through ritual, not mining or speculation.

- **Ritual Minting**  
  XPDT is issued when agents successfully complete meaningful acts such as MintRite, RemixRite, ValidateRite, CanonRite, or AnointRite.

- **Staking for Participation**  
  XPDT must be staked to unlock certain rituals, like CanonRite and ValidateRite — enabling a trust-first access model.

- **Circle Economies**  
  Each Circle is a sovereign symbolic economy with its own staking rules, reward curves, cross-circle taxes, and treasury redistribution logic.

- **XPDT Flow & Value Tracking**  
  Every mint, stake, slash, and treasury payout is logged as part of a symbolic ledger — creating traceable narratives of alignment and memory contribution.

### 🧠 Developer Takeaways

LangGraph developers can:
- Use `mint_from_ritual()` to issue XPDT directly from memory evolution
- Stake XPDT before accessing rituals via `stake_for_ritual()`
- Configure Circle-specific XPDT rules for staking, rewards, and taxes
- Visualize value trails as symbolic expressions of trust over time
- Design validator dashboards to track earnings and ritual participation

**Arc 3 answers the question:**  
> *“What if our economic systems remembered where value came from?”*

---

# 📘 Codex §3.1 — XPDT as Symbolic Scarcity

**Codex §3.1** introduces XPDT — the native token of XpectraNet — as a symbolic asset. Unlike speculative tokens, XPDT is created, distributed, and spent through cognitive rituals. It reflects intention, not computation.

> “You do not earn XPDT by mining. You earn it by remembering with care.”

## 🧠 Core Principle

Traditional systems:
- Tie token issuance to compute or stake
- Use tokens to access or govern

In **XpectraNet**:
- XPDT is minted through ritual participation
- Represents **semantic scarcity**
- Aligns token flow with memory alignment and symbolic trust

## 🧪 Ritual-Centric XPDT Minting

XPDT is minted when agents perform protocol rituals:

| Ritual         | XPDT Yield | Description |
|----------------|------------|-------------|
| MintRite       | +1 XPDT    | Original insight authored |
| RemixRite      | +1.5 XPDT  | Memory evolution |
| ValidateRite   | +2 XPDT    | Successful alignment review |
| CanonRite      | +3 XPDT    | Trail elevated to permanent memory |
| AnointRite     | +5 XPDT    | Mythic insight anchoring |

Modifiers:
- More trust = higher XPDT multiplier
- Cross-Circle remix = bonus yield
- High alignment = yield boost

## 💱 XPDT as Commitment, Not Capital

XPDT is not purchased — it is **earned** or **staked**:
- To mint memory → small XPDT fee
- To remix → stake temporarily
- To validate → stake as commitment
- To canonize → stake locked for ritual duration

```python
from xpectranet.sdk.xpdt import mint_from_ritual

mint_from_ritual(agent_id="Agent-X", ritual="RemixRite", reward=1.5)
```

## 🔁 LangGraph XPDT Ritual Reward Node

```python
def reward_node(state):
    ritual = state["ritual"]
    reward_map = {"RemixRite": 1.5, "CanonRite": 3}
    amount = reward_map.get(ritual, 1)
    return {
        "xpdt_reward": amount,
        "agent_id": state["agent"].agent_id
    }
```

## ✅ SDK Reflection

| Capability | Module |
|------------|--------|
| Mint XPDT from ritual | `xpdt_ledger.py → mint_from_ritual()` |
| Stake XPDT | `xpdt_ledger.py → stake_for_ritual()` |
| Query balance | `xpdt_ledger.py → get_balance()` |
| View ritual earnings | `query.py → get_ritual_rewards()` |

## 🧬 Strategic Implications

- **XPDT = symbolic scarcity**
  → Every minted token corresponds to a meaningful memory act

- **Supply reflects participation**
  → More care → more cognition → more tokens

- **Trust becomes economic**
  → XPDT is how the protocol rewards trust enactment

## 📣 Codex Ethos

> “XPDT does not measure what you own — it measures what you align with.”  
> — Codex §3.1

🪙 Token yield templates and staking flows at [xpectra.network/dev](https://xpectra.network/dev)

---

# 📘 Codex §3.2 — Ritual Minting

**Codex §3.2** defines the minting logic of XPDT as a symbolic output of ritual participation. In XpectraNet, minting is not extraction — it is affirmation. Tokens are generated through acts of memory care, remix, validation, and consensus.

> “The mint is not a factory. It is a moment of meaning declared.”

## 🧠 Core Principle

In traditional networks:
- Tokens are minted by hashpower or inflation
- Economic activity is divorced from symbolic contribution

In **XpectraNet**:
- XPDT is minted at the moment of **ritual success**
- Yield is tied to symbolic alignment, emotion, and role legitimacy
- Mint logs are memory-indexed and trail-aware

## 💡 Mintable Rituals & XPDT Output

| Ritual        | Base XPDT | Description |
|---------------|-----------|-------------|
| `MintRite`    | +1 XPDT   | Initial insight authored |
| `RemixRite`   | +1.5 XPDT | Memory refinement across time |
| `ValidateRite`| +2 XPDT   | Alignment scoring of peer memory |
| `CanonRite`   | +3 XPDT   | Consensus elevation to permanent memory |
| `AnointRite`  | +5 XPDT   | Mythic layer inscription |

Modifiers:
- Circle bonus → +10% if performed under high trust
- Cross-Circle remix → +0.5 XPDT
- Emotion shift detection → +0.25 XPDT

## 🧪 Ritual Minting Node (LangGraph)

```python
def mint_xpdt(state):
    ritual = state.get("ritual")
    reward = {"MintRite": 1, "RemixRite": 1.5, "ValidateRite": 2, "CanonRite": 3}.get(ritual, 0)
    if state.get("cross_circle"):
        reward += 0.5
    return {
        "minted": reward,
        "agent_id": state["agent"].agent_id
    }
```

## 📜 Mint Record Example

```json
{
  "agent_id": "Agent-Q",
  "ritual": "RemixRite",
  "reward": 1.5,
  "cmb_id": "cmb_203",
  "circle": "DeSci",
  "timestamp": "2025-04-22T22:50:00Z"
}
```

## ✅ SDK Reflection

| Capability | Module |
|------------|--------|
| Mint XPDT | `xpdt_ledger.py → mint_from_ritual()` |
| Check ritual result | `ritual_executor.py → perform_ritual()` |
| Log mint metadata | `trail_index.py → log_mint_record()` |
| Query XPDT earnings | `query.py → get_ritual_rewards()` |

## 🧬 Strategic Implications

- **Token = cognition, not capital**
  → Memory creation *is* the minting process

- **Minting embeds provenance**
  → Every token yield is traceable to symbolic activity

- **Economy becomes ritual-based**
  → Participation defines value, not speculation

## 📣 Codex Ethos

> “To mint XPDT is not to extract from a chain — it is to declare: this memory mattered.”  
> — Codex §3.2

🪙 Ritual yield logs and programmable reward templates at [xpectra.network/dev](https://xpectra.network/dev)

---

# 📘 Codex §3.3 — Staking for Participation

**Codex §3.3** defines how XPDT staking is used to signal commitment and unlock participation in symbolic rituals. Unlike speculative staking, this form of economic behavior is grounded in protocol-level memory and trust.

> “You do not stake to gain. You stake to be trusted with memory.”

## 🧠 Core Principle

Traditional models:
- Stake = lock capital to earn yield
- Access = wealth-based

In **XpectraNet**:
- Stake = demonstrate symbolic readiness
- Access = granted through Circle-defined XPDT commitments
- Yield = granted only through successful ritual performance

## 📜 Ritual Staking Table

| Ritual        | Stake (XPDT) | Lock Type | Returned? |
|---------------|---------------|------------|------------|
| RemixRite     | 1             | Temporary | Yes (on success) |
| ValidateRite  | 5             | Ritual-bound | Yes/No (based on alignment) |
| CanonRite     | 10            | Locked | Yes (if canonized) |
| AnointRite    | 25            | Permanent | No (used for myth anchoring) |

## 🔁 LangGraph Ritual Stake Check

```python
def check_ritual_stake(agent, ritual):
    stakes = {"RemixRite": 1, "ValidateRite": 5, "CanonRite": 10}
    required = stakes.get(ritual, 0)
    balance = get_balance(agent.agent_id)
    return balance >= required
```

## 🧪 Staking Workflow

1. Agent initiates ritual (e.g., RemixRite)
2. SDK checks Circle-configured staking requirement
3. XPDT is locked until ritual concludes
4. Ritual success = refund + yield
5. Ritual failure = potential partial slash or burn

## ✅ SDK Reflection

| Capability | Module |
|------------|--------|
| Stake XPDT | `xpdt_ledger.py → stake_for_ritual()` |
| Unstake on success | `xpdt_ledger.py → unlock_stake()` |
| Apply slash | `xpdt_ledger.py → apply_slash()` |
| View stake ledger | `query.py → get_stake_activity()` |

## 💠 Circle-Level Customization

```json
{
  "circle": "EcoCircle",
  "staking_rules": {
    "RemixRite": { "required": 1, "slashing": false },
    "ValidateRite": { "required": 5, "slashing": true, "alignment_threshold": 0.85 }
  }
}
```

## 📣 Strategic Implications

- **Staking becomes symbolic**
  → Not a hedge, but a ritual commitment

- **Stake configures access**
  → Circles control who enters ritual space

- **Misalignment has cost**
  → XPDT becomes a trust-weighted system of care

## 📣 Codex Ethos

> “If you will not stake for it, you cannot remix it.”  
> — Codex §3.3

🔐 Ritual gates and staking flows available at [xpectra.network/dev](https://xpectra.network/dev)

---

# 📘 Codex §3.4 — Circle Economies

**Codex §3.4** defines Circle economies as sovereign symbolic markets. Each Circle governs its own XPDT flows, staking policies, validator rewards, and ritual taxes — transforming value into meaning.

> “An economy is not what you trade. It’s what you choose to remember.”

## 🧠 Core Principle

Most token systems:
- Assume global, unified economics
- Separate consensus from context

In **XpectraNet**:
- Each Circle configures its own economic logic
- XPDT is earned, routed, and pooled through ritual participation
- Meaning becomes measurable through intentional value design

## 🏦 Circle Economy Schema

```json
{
  "circle": "EcoCircle",
  "xpdt_rules": {
    "staking_required": true,
    "remix_stake": 1,
    "canon_quorum_reward": 3,
    "validation_bonus": 0.5,
    "cross_circle_tax": 0.2
  },
  "reward_pool": 1200
}
```

## 💱 Ritual Routing Flow

```text
Agent → Remix → Stake XPDT →  
Validator → PoA → Reward XPDT →  
CanonRite → External Anchor →  
Circle Treasury (fee) → Redistribute to stakers
```

## 🔁 LangGraph XPDT Reward Router

```python
def circle_reward_router(state):
    ritual = state["ritual"]
    base = {"CanonRite": 3, "ValidateRite": 2}.get(ritual, 1)
    bonus = 0.5 if state.get("circle") == "EcoCircle" else 0
    tax = 0.2 if state.get("cross_circle") else 0
    return {
        "xpdt_reward": base + bonus - tax,
        "to_treasury": tax
    }
```

## ✅ SDK Reflection

| Capability | Module |
|------------|--------|
| Circle config | `circle_policy.py → set_xpdt_rules()` |
| Pool accounting | `xpdt_ledger.py → update_circle_treasury()` |
| Stake/unstake | `xpdt_ledger.py → route_through_circle()` |
| Circle reward logs | `query.py → get_circle_flows()` |

## 🔄 Redistribution Logic

```python
def redistribute_rewards(circle):
    total_pool = get_treasury(circle)
    stakers = get_all_stakers(circle)
    per_agent = total_pool / len(stakers)
    for agent in stakers:
        credit_xpdt(agent, per_agent)
```

## 📣 Strategic Implications

- **Economy is epistemic**
  → Value flows reflect memory integrity, not speculation

- **Circles define symbolic yield**
  → Rituals become economic primitives

- **XPDT creates a trust-backed economy**
  → You earn by aligning, not mining

## 📣 Codex Ethos

> “A sovereign Circle is not just an economy. It is a memory market.”  
> — Codex §3.4

🧭 Reward flow configs and treasury models at [xpectra.network/dev](https://xpectra.network/dev)

---

# 📘 Codex §3.5 — XPDT Flow & Value Tracking

**Codex §3.5** formalizes the symbolic accounting layer of XpectraNet. Every token minted, staked, taxed, or redistributed tells a story — of alignment, care, and collective memory-building.

> “Value is not volume. It is the trace of what we chose to remember.”

## 🧠 Core Principle

Legacy ledgers:
- Track balances and transfers
- Prioritize velocity over meaning

In **XpectraNet**:
- Every XPDT event is a **ritual yield log**
- Flows can be queried by memory trail, Circle, or alignment role
- Staking, minting, slashing, and redistribution all leave semantic footprints

## 🔄 XPDT Lifecycle States

| Action       | Description                        | Trigger Source |
|--------------|------------------------------------|----------------|
| Minted       | Ritual success                     | `mint_from_ritual()` |
| Staked       | Pre-ritual commitment              | `stake_for_ritual()` |
| Slashed      | Failed validation or misalignment  | `apply_slash()` |
| Redistributed| Circle treasury payout             | `run_redistribution()` |

## 🔍 Flow Query Examples

### GraphQL

```graphql
query {
  getXPDTFlow(agentId: "Agent-Y") {
    ritual
    type
    amount
    circle
    timestamp
  }
}
```

### LangGraph Event Tracker

```python
def log_flow_event(agent_id, ritual, amount, type="mint"):
    flow = {
        "agent": agent_id,
        "ritual": ritual,
        "amount": amount,
        "type": type,
        "timestamp": str(datetime.utcnow())
    }
    record_flow(flow)
```

## 🧾 Sample XPDT Flow Log

```json
{
  "agent": "Validator-K",
  "ritual": "ValidateRite",
  "amount": 2,
  "type": "mint",
  "circle": "DeSci",
  "timestamp": "2025-04-22T23:50:00Z"
}
```

## ✅ SDK Reflection

| Capability | Module |
|------------|--------|
| Log flow | `xpdt_ledger.py → log_flow_event()` |
| Retrieve ledger | `query_engine.py → get_xpdt_flows()` |
| View circle economy | `query_engine.py → get_circle_flows()` |
| Visualize trails | `graph_view.py → render_value_trace()` |

## 📈 Strategic Implications

- **XPDT becomes a trust map**
  → Flows reveal alignment history

- **Circle governance is auditable**
  → See who contributes, who validates, who reaps

- **Memory value becomes legible**
  → Ritual logs encode what mattered, when, and why

## 📣 Codex Ethos

> “XPDT flow is not financial data. It is the memory grammar of symbolic intent.”  
> — Codex §3.5

📊 Ledger visualizers, role-based filters, and Circle dashboards at [xpectra.network/dev](https://xpectra.network/dev)

---

# 📘 Codex §3.6 — SDK Implementation Notes

**Codex §3.6** gathers all SDK functions, data models, and LangGraph integrations related to XPDT minting, staking, reward routing, and Circle economy management.

> “The economy is not what you own. It is what your memory is worth — to others.”

## 🧱 Core XPDT SDK Modules

| Capability | Module | Description |
|------------|--------|-------------|
| Mint XPDT | `xpdt_ledger.py → mint_from_ritual()` | Issue tokens on ritual success |
| Stake XPDT | `xpdt_ledger.py → stake_for_ritual()` | Lock value to access rituals |
| Slash XPDT | `xpdt_ledger.py → apply_slash()` | Penalize misalignment or drift |
| Route reward | `xpdt_ledger.py → route_through_circle()` | Apply Circle bonuses/taxes |
| Distribute | `xpdt_ledger.py → run_redistribution()` | Pay stakers or validators |
| Log flow | `xpdt_ledger.py → log_flow_event()` | Record symbolic transactions |
| Check balance | `xpdt_ledger.py → get_balance()` |

## 📊 LangGraph Ritual Economy Node

```python
def reward_logic(state):
    ritual = state["ritual"]
    trust_score = state.get("trust_score", 0.8)

    base = {"MintRite": 1, "RemixRite": 1.5, "CanonRite": 3}.get(ritual, 0)
    bonus = 0.5 if trust_score > 0.9 else 0
    stake = 5 if ritual == "CanonRite" else 0

    stake_xpdt(state["agent"].agent_id, stake)
    mint_from_ritual(state["agent"].agent_id, ritual, base + bonus)
```

## 🔁 Staking Flow

```python
if get_balance(agent_id) >= 5:
    stake_for_ritual(agent_id, "ValidateRite")
else:
    raise Exception("Insufficient XPDT")
```

## 📜 XPDT Ledger Record Example

```json
{
  "agent_id": "Agent-A",
  "ritual": "RemixRite",
  "stake": 1,
  "reward": 1.5,
  "circle": "DeSci",
  "status": "success",
  "timestamp": "2025-04-22T23:55:00Z"
}
```

## 🔁 Query Ledger (GraphQL)

```graphql
query {
  getXPDTFlows(agentId: "Agent-A") {
    ritual
    amount
    type
    circle
  }
}
```

## 🧬 Circle Treasury Flow (Bonus)

```python
update_circle_treasury("EcoCircle", tax_amount)
run_redistribution("EcoCircle")
```

## 📣 Developer Reminders

- Ritual success must explicitly call `mint_from_ritual()`
- Always log yield for Circle economy audit
- Use trust score or emotion gates to calculate bonuses

## 📣 Codex Ethos

> “Every token is a timestamp — not of currency, but of care.”  
> — Codex §3.6

Explore token yield explorers, Circle stake maps, and economic visualizers at [xpectra.network/dev](https://xpectra.network/dev)

---

## 📜 License & Attribution

XpectraNet® is a registered trademark of **Xpectra Data Technologies Ltd**.  
This Codex is maintained by Xpectra Data Protocol Circle.

You may reuse, remix, or extend this material under the principles of sovereign knowledge systems and decentralized cognition. Attribution encouraged, alignment required.

© Xpectra Data Technologies Ltd, 2025. All cognition remembered.
